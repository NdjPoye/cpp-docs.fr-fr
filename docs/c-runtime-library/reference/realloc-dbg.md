---
title: "_realloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_realloc_dbg"
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
  - "_realloc_dbg"
  - "realloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "réallouer des blocs de mémoire"
  - "realloc_dbg (fonction)"
  - "blocs de mémoire, réallouer"
  - "mémoire, réallouer"
  - "_realloc_dbg (fonction)"
ms.assetid: 7c3cb780-51ed-4d9c-9929-cdde606d846a
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _realloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Réaffecte un bloc de mémoire spécifié dans le tas en déplaçant et\/ou en redimensionnant le bloc \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
void *_realloc_dbg(  
   void *userData,  
   size_t newSize,  
   int blockType,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### Paramètres  
 `userData`  
 Pointeur du bloc de mémoire précédemment allouée.  
  
 `newSize`  
 Nouvelle taille demandée pour le bloc réalloué \(en octets\).  
  
 `blockType`  
 Type demandé du bloc réaffecté : `_CLIENT_BLOCK` ou `_NORMAL_BLOCK`.  
  
 `filename`  
 Le pointeur du nom du fichier source qui a demandé l'opération `realloc` ou NULL.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération `realloc` ou NULL.  
  
 Les paramètres `filename` et `linenumber` sont uniquement disponibles si `_realloc_dbg` a été appelé explicitement ou si la constante de préprocesseur [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) a été définie.  
  
## Valeur de retour  
 Dans l'achèvement réussi, le retour de cette fonction ou un pointeur vers la partie utilisateur du bloc de mémoire réaffecté, appelle la fonction gestionnaire, ou renvoie NULL.  Pour une description complète du comportement de retour, consultez la section Notes suivante.  Pour plus d'informations sur la façon dont la nouvelle fonction gestionnaire est utilisée, consultez la fonction ["](../../c-runtime-library/reference/realloc.md).  
  
## Notes  
 `_realloc_dbg` est une version Debug de la fonction ["](../../c-runtime-library/reference/realloc.md).  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, chaque appel à `_realloc_dbg` est réduit à un appel à `realloc`.  A la fois `realloc` et `_realloc_dbg` redimensionnent un bloc de mémoire dans la pile de base, mais `_realloc_dbg` s'adapte à plusieurs fonctionnalités de débogage : mémoires tampons de chaque côté de la partie utilisateur du bloc à déterminer des fuites, un paramètre de type de bloc pour suivre des types spécifiques d'allocation, et `filename`\/`linenumber` pour déterminer l'origine des demandes d'allocation.  
  
 `_realloc_dbg` réalloue le bloc de mémoire spécifié avec légèrement plus d'espace que demandait `newSize`.  `newSize` peut être supérieure ou inférieure à la taille du bloc de mémoire initialement alloué.  L'espace supplémentaire est utilisé par le gestionnaire du tas de débogage pour lier les blocs de mémoire de débogage, pour fournir à l'application les informations d'en\-tête du débogage et pour remplacer des mémoires tampons.  Une redistribution peut avoir comme conséquence le déplacement du bloc mémoire d'origine vers un endroit de la pile, ainsi qu'en modifiant la taille du bloc de mémoire.  Si le bloc de mémoire est déplacé, le contenu du bloc d'origine est remplacée.  
  
 `_realloc_dbg` définit `errno` à `ENOMEM` si une allocation de mémoire échoue ou si la quantité de mémoire nécessaire \(charge mémoire y compris mentionnée précédemment\) dépasse `_HEAP_MAXREQ`.  Pour plus d'informations sur ces codes de retour et autres, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Pour obtenir des informations sur la façon dont les blocs de mémoire sont alloués, initialisés, et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Pour obtenir des informations sur les types de bloc d'allocation et leur utilisation, consultez [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Pour obtenir des informations sur les différences entre appeler une fonction standard du tas et sa version Debug dans une version debug d'une application, consultez [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_realloc_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Consultez l'exemple décrit dans la rubrique sous [\_msize\_dbg](../../c-runtime-library/reference/msize-dbg.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md)