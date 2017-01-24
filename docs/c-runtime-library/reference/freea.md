---
title: "_freea | Microsoft Docs"
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
  - "_freea"
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
apitype: "DLLExport"
f1_keywords: 
  - "freea"
  - "_freea"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_freea (fonction)"
  - "freea (fonction)"
  - "désallocation de mémoire"
ms.assetid: dcd30584-dd9d-443b-8c4c-13237a1cecac
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _freea
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Désalloue ou libère un bloc mémoire.  
  
## Syntaxe  
  
```  
void _freea(   
   void *memblock   
);  
```  
  
#### Paramètres  
 `memblock`  
 Bloc mémoire alloué précédemment pour etre libéré.  
  
## Valeur de retour  
 Aucun.  
  
## Notes  
 La fonction `_freea` desalloue un bloc de mémoire \(`memblock`\) qui a été allouée précedemment par un appel à [\_malloca](../../c-runtime-library/reference/malloca.md).  `_freea` vérifie si la mémoire a été allouée sur le segment ou la pile.  Si elle a été allouée dans la pile, `_freea` n'a aucun effet.  Si elle a été allouée sur le segment, le nombre d'octets libérés est équivalent au nombre d'octets demandés lorsque le bloc a été alloué.  Si `memblock` est `NULL`, le pointeur est ignoré et `_freea` retourne immédiatement,  Tenter de libérer un pointeur invalide \(pointeur vers un bloc de mémoire qui n'a pas été alloué par `_malloca`\) peut affecter les demandes d'allocation suivantes et provoquer des erreurs.  
  
 \_`freea` appelle `free` en interne s'il constate que la mémoire est allouée sur le segment.  Que la mémoire soit sur le segment ou que la pile soit determinée par un  marqueur placé en mémoire à l'adresse précédant immédiatement la mémoire allouée.  
  
 Si une erreur se produit en libérant la mémoire, `errno` est défini avec les informations du système d'exploitation sur la nature de l'échec.  Pour plus d'informations, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Lorsqu'un bloc de mémoire a été libéré, [\_heapmin](../../c-runtime-library/reference/heapmin.md) réduit la quantité de mémoire disponible sur le segment en fusionnant les régions inutilisées et en les libérant dans le système d'exploitation.  La mémoire libérée qui n'est pas libérée vers le système d'exploitation est restaurée au pool disponible et est de nouveau disponible pour l'allocation.  
  
 Un appel à `_freea` doit accompagner tous les appels à `_malloca`.  C'est également une erreur d'appeler `_freea` deux fois sur la même mémoire.  Lorsque l'application est liée à une version de débogage des bibliothèques runtime C, en particulier avec les fonctionnalités de [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md) activé en définissant `_CRTDBG_MAP_ALLOC`, il est plus facile de recherche les appels manquants ou dupliqués à `_freea`.  Pour plus d'informations sur la gestion du tas pendant le processus de débogage, consultez [The CRT Debug Heap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 `_freea` est marqué comme`__declspec(noalias)`, ce qui signifie que la fonction est assurée de ne pas modifier les variables globales.  Pour plus d'informations, consultez [noalias](../../cpp/noalias.md).  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_freea`|\<stdlib.h\> et \<malloc.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
 Consultez l'exemple pour [\_malloca](../../c-runtime-library/reference/malloca.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [\_malloca](../../c-runtime-library/reference/malloca.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [\_free\_dbg](../../c-runtime-library/reference/free-dbg.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)