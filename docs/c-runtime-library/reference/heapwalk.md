---
title: "_heapwalk | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_heapwalk"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "heapwalk"
  - "_heapwalk"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_heapwalk (fonction)"
  - "déboguer (CRT), problèmes liés au tas"
  - "heapwalk (fonction)"
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _heapwalk
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Parcourt le tas et retourne des informations sur l'entrée suivante.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime sauf dans les builds de déboguage.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _heapwalk(   
   _HEAPINFO *entryinfo   
);  
```  
  
#### Paramètres  
 `entryinfo`  
 Mémoire tampon pour contenir les informations du tas.  
  
## Valeur de retour  
 `_heapwalk` retourne un des constantes de manifeste d'entiers suivantes définies dans Malloc.h.  
  
 `_HEAPBADBEGIN`  
 Les informations d'en\-tête initiales sont non valides ou introuvables.  
  
 `_HEAPBADNODE`  
 Tas endommagé ou nœud incorrect trouvé.  
  
 `_HEAPBADPTR`  
 Le champ`_pentry` de la structure `_HEAPINFO` ne contient pas un pointeur valide dans le tas ou `entryinfo` est un pointeur null.  
  
 `_HEAPEND`  
 Fin du tas atteint.  
  
 `_HEAPEMPTY`  
 Tas pas encore initialisé  
  
 `_HEAPOK`  
 Aucune erreur jusque\-là ; `entryinfo` est mis à jour avec des informations sur l'entrée suivante du tas.  
  
 En outre, si une erreur se produit, `_heapwalk` définit `errno` à `ENOSYS`.  
  
## Notes  
 La fonction `_heapwalk` aide au déboguage des problèmes liés au tas par dans les programmes.  La fonction traverse le tas, parcourant une entrée par appel, et retourne un pointeur vers une structure de type `_HEAPINFO` qui contient des informations sur l'entrée suivante du tas.  Le type `_HEAPINFO`, défini dans Malloc.h, contient les éléments suivants.  
  
 `int *_pentry`  
 Pointeur d'entrée du tas.  
  
 `size_t _size`  
 Taille de l'entrée de tas.  
  
 `int _useflag`  
 Indicateur qui détermine si le l'entrée du tas est en cours d'utilisation.  
  
 Un appel à `_heapwalk` qui retourne`_HEAPOK` enregistre la taille de l'entrée dans le champ `_size` et définit le champ `_useflag` soit à `_FREEENTRY` ou à `_USEDENTRY` \(les deux sont des constantes de Malloc.h\).  Pour obtenir ces informations sur la première entrée dans le tas, donnez à `_heapwalk` un pointeur vers une structure `_HEAPINFO` dont le membre `_pentry` est `NULL`.  Si le système d'exploitation ne prend pas en charge `_heapwalk`\(par exemple, Windows 98\), la fonction retourne `_HEAPEND` et affecte à `errno` la valeur `ENOSYS`.  
  
 Cette fonction valide son paramètre.  Si `entryinfo` est un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini comme `EINVAL` et la fonction retourne `_HEAPBADPTR`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_heapwalk`|\<malloc.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_heapwalk.c  
  
// This program "walks" the heap, starting  
// at the beginning (_pentry = NULL). It prints out each  
// heap entry's use, location, and size. It also prints  
// out information about the overall state of the heap as  
// soon as _heapwalk returns a value other than _HEAPOK  
// or if the loop has iterated 100 times.  
  
#include <stdio.h>  
#include <malloc.h>  
  
void heapdump(void);  
  
int main(void)  
{  
    char *buffer;  
  
    heapdump();  
    if((buffer = (char *)malloc(59)) != NULL)  
    {  
        heapdump();  
        free(buffer);  
    }  
    heapdump();  
}  
  
void heapdump(void)  
{  
    _HEAPINFO hinfo;  
    int heapstatus;  
    int numLoops;  
    hinfo._pentry = NULL;  
    numLoops = 0;  
    while((heapstatus = _heapwalk(&hinfo)) == _HEAPOK &&  
          numLoops < 100)  
    {  
        printf("%6s block at %Fp of size %4.4X\n",  
               (hinfo._useflag == _USEDENTRY ? "USED" : "FREE"),  
               hinfo._pentry, hinfo._size);  
        numLoops++;  
    }  
  
    switch(heapstatus)  
    {  
    case _HEAPEMPTY:  
        printf("OK - empty heap\n");  
        break;  
    case _HEAPEND:  
        printf("OK - end of heap\n");  
        break;  
    case _HEAPBADPTR:  
        printf("ERROR - bad pointer to heap\n");  
        break;  
    case _HEAPBADBEGIN:  
        printf("ERROR - bad start of heap\n");  
        break;  
    case _HEAPBADNODE:  
        printf("ERROR - bad node in heap\n");  
        break;  
    }  
}  
```  
  
  **Bloc UTILISÉ à 00310650 de taille 0100**  
 **Bloc UTILISÉ à 00310758 de taille 0800**  
 **Bloc UTILISÉ à 00310F60 de taille 0800**  
 **Bloc LIBRE à 00310FF0 de taille 0398**  
 **Bloc UTILISÉ à 00311390 de taille 0800**  
 **Bloc UTILISÉ à 003113A8 de taille 00B4**  
 **Bloc UTILISÉ à 00311468 de taille 0034**  
 **Bloc UTILISÉ à 003114A8 de taille 0039**  
**...**  
 **Bloc UTILISÉ à 00312228 de taille 0010**  
 **Bloc UTILISÉ à 00312240 de taille 1000**  
 **Bloc LIBRE à 00311390 de taille 0800**  
**OK \- fin du tas**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [\_heapadd](../../c-runtime-library/heapadd.md)   
 [\_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_heapset](../../c-runtime-library/heapset.md)