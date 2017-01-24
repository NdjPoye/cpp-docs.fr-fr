---
title: "_expand | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_expand"
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
  - "_bexpand"
  - "fexpand"
  - "expand"
  - "nexpand"
  - "_fexpand"
  - "_nexpand"
  - "bexpand"
  - "_expand"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_expand (fonction)"
  - "expand (fonction)"
  - "blocs de mémoire, modifier la taille"
ms.assetid: 4ac55410-39c8-45c7-bccd-3f1042ae2ed3
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _expand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Modifie la taille d'un bloc de mémoire.  
  
## Syntaxe  
  
```  
void *_expand(   
   void *memblock,  
   size_t size   
);  
```  
  
#### Paramètres  
 `memblock`  
 Pointeur vers un bloc de mémoire précédemment allouée.  
  
 `size`  
 Nouvelle taille en octets.  
  
## Valeur de retour  
 `_expand` retourne un pointeur void le bloc de mémoire réaffecté.  `_expand`, contrairement à `realloc`, ne peut pas déplacer un bloc pour modifier sa taille.  Par conséquent, s'il y a suffisamment de mémoire disponible pour étendre le bloc sans le déplacer, le paramètre `memblock` de `_expand` est identique à la valeur de retour.  
  
 `_expand` retourne `NULL` lorsqu'une erreur est détectée durant l'opération.  Par exemple, si `_expand` permet de réduire un bloc de mémoire, il peut détecter l'altération dans les petits segments ou un pointeur de block invalide et retourne `NULL`.  
  
 En cas de mémoire indisponible pour étendre le bloc à la taille spécifiée sans le déplacer, la fonction retourne `NULL`.  `_expand` ne retourne jamais un bloc étendu une taille inférieure à la demande.  Si une défaillance se produit, `errno` indique la nature de l'erreur.  Pour plus d'informations sur `errno`, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Les valeur de retour pointent vers un espace de stockage, qui est garanti d'etre aligné correctement pour le stockage de n'importe quel types d'objet.  Pour activer la nouvelle taille de l'élément, utilisez `_msize`.  Pour obtenir un pointeur sur un type autre qu'un `void`, utilisez un cast de type sur la valeur de retour.  
  
## Notes  
 La fonction `_expand` change la taille d'un bloc de mémoire déjà allouée en essayant de d'étendre ou de réduire de manière interactive le bloc sans le déplacer dans le segment.  Le paramètre`memblock` pointe vers le début du block.  Le paramètre `size` présente la nouvelle taille du bloc, en octets.  Le contenu du bloc n'est pas affecté sur l'espace de la plus courte taille, entre la nouvelle et l'ancienne.  `memblock` ne doit pas être un bloc qui a été débloqué.  
  
> [!NOTE]
>  Sur les plateformes 64 bits, `_expand` ne peut pas réduire le bloc si la nouvelle taille est inférieure à la taille actuelle ; en particulier, si le bloc est plus petit que 16k et a par conséquent été alloué dans le segment de fragmentation, `_expand` laisse inchangée le bloc et retourne `memblock`.  
  
 Lorsque l'application est liée à une version debug des bibliothèques Runtime C, `_expand` est résolu en [\_expand\_dbg](../../c-runtime-library/reference/expand-dbg.md).  Pour plus d'informations sur la gestion du tas pendant le processus de débogage, consultez [The CRT Debug Heap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Cette fonction valide ses paramètres.  Si `memblock` est un pointeur null, cette fonction appelle un gestionnaire de paramètres invalides comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini à `EINVAL` et la fonction retourne `NULL`.  Si `size` est supérieur à `_HEAP_MAXREQ`, `errno` prend la valeur `ENOMEM` et la fonction retourne `NULL`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_expand`|\<malloc.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_expand.c  
  
#include <stdio.h>  
#include <malloc.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char *bufchar;  
   printf( "Allocate a 512 element buffer\n" );  
   if( (bufchar = (char *)calloc( 512, sizeof( char ) )) == NULL )  
      exit( 1 );  
   printf( "Allocated %d bytes at %Fp\n",   
         _msize( bufchar ), (void *)bufchar );  
   if( (bufchar = (char *)_expand( bufchar, 1024 )) == NULL )  
      printf( "Can't expand" );  
   else  
      printf( "Expanded block to %d bytes at %Fp\n",   
            _msize( bufchar ), (void *)bufchar );  
   // Free memory   
   free( bufchar );  
   exit( 0 );  
}  
```  
  
  **Alloue une mémoire tampon de 512 éléments**  
**Alloué 512 octets à 002C12BC**  
**Bloc étendu à 1024 octets en 002C12BC**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_msize](../../c-runtime-library/reference/msize.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)