---
title: "calloc | Microsoft Docs"
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
  - "calloc"
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
  - "calloc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "allocation de mémoire, tableaux"
  - "calloc (fonction)"
ms.assetid: 17bb79a1-98cf-4096-90cb-1f9365cd6829
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# calloc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Alloue un tableau en mémoire avec les éléments initialisés à 0.  
  
## Syntaxe  
  
```  
void *calloc(   
   size_t num,  
   size_t size   
);  
```  
  
#### Paramètres  
 `num`  
 Nombre d'éléments  
  
 `size`  
 Longueur en octets de chaque élément.  
  
## Valeur de retour  
 `calloc` retourne un pointeur vers l'espace alloué.  Les valeur de retour pointent vers un espace de stockage, qui est garanti d'être aligné correctement pour le stockage de n'importe quel type d'objet.  Pour obtenir un pointeur sur un type autre qu'un `void`, utilisez un cast de type sur la valeur de retour.  
  
## Notes  
 La fonction `calloc` alloue de l'espace de stockage pour un tableau d'éléments de `num`, chacune `size` d'octets de longueur.  Chaque élément est initialisée à 0.  
  
 `calloc` affecte à `errno` la valeur `ENOMEM` si une allocation de mémoire échoue ou si la quantité de mémoire demandée dépasse `_HEAP_MAXREQ`.  Pour plus d'informations sur ceci et sur les codes d'erreurs, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `calloc` appelle  `malloc`[\_set\_new\_mode](../../c-runtime-library/reference/set-new-mode.md) pour utiliser la fonction C\+\+ pour définir le nouveau mode gestionnaire.  Le nouveau mode de gestionnaire indique si, en cas de échec, `malloc` doit appeler la nouvelle routine du gestionnaire comme définit par [\_set\_new\_handler](../../c-runtime-library/reference/set-new-handler.md).  Par défaut, `malloc` n'appelle pas la nouvelle routine de gestionnaire en cas de défaillance pour allouer de la mémoire.  Vous pouvez substituer ce comportement par défaut afin que, lorsque `calloc` ne réussit pas à allouer la mémoire, `malloc` appelle la nouvelle routine de gestionnaire de la même manière que l'opérateur `new` lorsqu'il échoue pour la même raison.  Pour substituer la valeur par défaut, appelez  
  
```  
_set_new_mode(1)  
```  
  
 tôt dans votre programme, ou créez un lien avec NEWMODE.OBJ \(consultez [Options de lien](../../c-runtime-library/link-options.md)\).  
  
 Lorsque l'application est liée à une version debug des bibliothèques Runtime C, `calloc` est résolu en [\_calloc\_dbg](../../c-runtime-library/reference/calloc-dbg.md).  Pour plus d'informations sur la gestion du tas pendant le processus de débogage, consultez [The CRT Debug Heap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `calloc` est marqué `__declspec(noalias)` et `__declspec(restrict)` ; cela signifie que la fonction ne modifiera pas de variables globales et que le pointeur retourné n'est pas sous la forme d'un alias.  Pour plus d'informations, consultez [noalias](../../cpp/noalias.md) et [restrict](../../cpp/restrict.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`calloc`|\<stdlib.h\> et \<malloc.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_calloc.c  
// This program uses calloc to allocate space for  
// 40 long integers. It initializes each element to zero.  
  
#include <stdio.h>  
#include <malloc.h>  
  
int main( void )  
{  
   long *buffer;  
  
   buffer = (long *)calloc( 40, sizeof( long ) );  
   if( buffer != NULL )  
      printf( "Allocated 40 long integers\n" );  
   else  
      printf( "Can't allocate memory\n" );  
   free( buffer );  
}  
```  
  
  **Alloué 40 entiers longs**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)