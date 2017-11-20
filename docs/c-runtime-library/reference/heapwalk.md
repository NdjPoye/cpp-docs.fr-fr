---
title: _heapwalk | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _heapwalk
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- heapwalk
- _heapwalk
dev_langs: C++
helpviewer_keywords:
- debugging [CRT], heap-related problems
- heapwalk function
- _heapwalk function
ms.assetid: 2df67649-fb00-4570-a8b1-a4eca5738744
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: caed5b5fec9ff7854905542c093a0d265dee4db5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="heapwalk"></a>_heapwalk
Parcourt le tas et retourne des informations sur l’entrée suivante.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s’exécutent dans le Windows Runtime, sauf dans les builds de débogage. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _heapwalk(   
   _HEAPINFO *entryinfo   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `entryinfo`  
 Mémoire tampon destinée à contenir les informations relatives au tas.  
  
## <a name="return-value"></a>Valeur de retour  
 `_heapwalk` retourne une des constantes manifestes entières suivantes définies dans Malloc.h.  
  
 `_HEAPBADBEGIN`  
 Informations d’en-tête initiales non valides ou introuvables.  
  
 `_HEAPBADNODE`  
 Tas endommagé ou nœud incorrect trouvé.  
  
 `_HEAPBADPTR`  
 Le champ `_pentry` de la structure `_HEAPINFO` ne contient pas un pointeur valide vers le tas ou `entryinfo` est un pointeur Null.  
  
 `_HEAPEND`  
 Fin du tas atteinte avec succès.  
  
 `_HEAPEMPTY`  
 Tas non initialisé.  
  
 `_HEAPOK`  
 Aucune erreur jusqu’à présent ; `entryinfo` est mis à jour avec des informations sur l’entrée suivante du tas.  
  
 En outre, si une erreur se produit, `_heapwalk` définit `errno` sur `ENOSYS`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_heapwalk` permet de déboguer les problèmes liés au tas dans les programmes. La fonction parcourt le tas, à raison d’une entrée par appel, et retourne un pointeur désignant une structure de type `_HEAPINFO` qui contient des informations sur l’entrée suivante du tas. Le type `_HEAPINFO`, défini dans Malloc.h, contient les éléments suivants.  
  
 `int *_pentry`  
 Pointeur vers une entrée du tas.  
  
 `size_t _size`  
 Taille de l’entrée du tas.  
  
 `int _useflag`  
 Indicateur qui indique si l’entrée du tas est en cours d’utilisation.  
  
 Un appel à `_heapwalk` qui retourne `_HEAPOK` stocke la taille de l’entrée dans le champ `_size` et définit le champ `_useflag` sur `_FREEENTRY` ou `_USEDENTRY` (les deux sont des constantes définies dans Malloc.h). Pour obtenir ces informations sur la première entrée du tas, passez à `_heapwalk` un pointeur désignant une structure `_HEAPINFO` dont le membre `_pentry` a la valeur `NULL`. Si le système d’exploitation ne prend pas en charge `_heapwalk` (par exemple Windows 98), la fonction retourne `_HEAPEND` et définit `errno` sur `ENOSYS`.  
  
 Cette fonction valide son paramètre. Si `entryinfo` est un pointeur Null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL` et la fonction retourne une valeur `_HEAPBADPTR`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_heapwalk`|\<malloc.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
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
  
```Output  
  USED block at 00310650 of size 0100  
  USED block at 00310758 of size 0800  
  USED block at 00310F60 of size 0080  
  FREE block at 00310FF0 of size 0398  
  USED block at 00311390 of size 000D  
  USED block at 003113A8 of size 00B4  
  USED block at 00311468 of size 0034  
  USED block at 003114A8 of size 0039  
...  
  USED block at 00312228 of size 0010  
  USED block at 00312240 of size 1000  
  FREE block at 00313250 of size 1DB0  
OK - end of heap  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [_heapadd](../../c-runtime-library/heapadd.md)   
 [_heapchk](../../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [_heapset](../../c-runtime-library/heapset.md)