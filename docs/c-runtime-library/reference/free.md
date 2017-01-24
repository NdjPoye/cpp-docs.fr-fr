---
title: "free | Microsoft Docs"
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
  - "free"
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
  - "free"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "blocs de mémoire, libérer"
  - "free (fonction)"
ms.assetid: 74ded9cf-1863-432e-9306-327a42080bb8
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# free
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Désalloue ou libère un bloc mémoire.  
  
## Syntaxe  
  
```  
void free(   
   void *memblock   
);  
```  
  
#### Paramètres  
 `memblock`  
 Bloc mémoire alloué précédemment pour être libéré.  
  
## Notes  
 La fonction `free` désalloue un bloc de mémoire \(`memblock`\) qui a été allouée précédemment par un appel à `calloc`, `malloc`, ou `realloc`.  Le nombre d'octets libérés est équivalent au nombre d'octets demandés lorsque le bloc a été alloué \(ou réaffecté, dans le cas de `realloc`\).  Si `memblock` est `NULL`, le pointeur est ignoré et `free` retourne immédiatement,  Tenter de libérer un pointeur invalide \(pointeur vers un bloc de mémoire qui n'a pas été alloué par `calloc`, `malloc`, ou `realloc`\) peut affecter les demandes d'allocation suivantes et provoquer des erreurs.  
  
 Si une erreur se produit en libérant la mémoire, `errno` est défini avec les informations du système d'exploitation sur la nature de l'échec.  Pour plus d'informations, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Lorsqu'un bloc de mémoire a été libéré, [\_heapmin](../../c-runtime-library/reference/heapmin.md) réduit la quantité de mémoire disponible sur le segment en fusionnant les régions inutilisées et en les libérant dans le système d'exploitation.  La mémoire libérée qui n'est pas libérée vers le système d'exploitation est restaurée au pool disponible et est de nouveau disponible pour l'allocation.  
  
 Lorsque l'application est liée à une version debug des bibliothèques Runtime C, `free` est résolu en [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md).  Pour plus d'informations sur la gestion du tas pendant le processus de débogage, consultez [Le tas de debug CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `free` est marqué comme `__declspec(noalias)`, ce qui signifie que la fonction est assurée de ne pas modifier les variables globales.  Pour plus d'informations, consultez [noalias](../../cpp/noalias.md).  
  
 Pour libérer de la mémoire allouée avec [\_malloca](../../c-runtime-library/reference/malloca.md), utilisez [\_freea](../../c-runtime-library/reference/freea.md).  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`free`|\<stdlib.h\> et \<malloc.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple de [malloc](../../c-runtime-library/reference/malloc.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [\_alloca](../../c-runtime-library/reference/alloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_freea](../../c-runtime-library/reference/freea.md)