---
title: "_aligned_malloc_dbg | Microsoft Docs"
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
  - "_aligned_malloc_dbg"
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
  - "_aligned_malloc_dbg"
  - "aligned_malloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_malloc_dbg (fonction)"
  - "aligned_malloc_dbg (fonction)"
ms.assetid: fb0429c3-685d-4826-9075-2515c5bdc5c6
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_malloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Alloue de la mémoire sur une limite d'alignement spécifiée avec de l'espace supplémentaire pour un en\-tête de débogage et des mémoires tampons de remplacement \(version de débogage uniquement\).  
  
## Syntaxe  
  
```  
void * _aligned_malloc_dbg(     size_t size,      size_t alignment,    const char *filename,    int linenumber  );  
```  
  
#### Paramètres  
 \[in\] `size`  
 Taille de l'allocation de mémoire demandée.  
  
 \[in\] `alignment`  
 Valeur d'alignement, qui doit être un entier à puissance 2.  
  
 \[in\] `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou NULL.  
  
 \[in\] `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou NULL.  
  
## Valeur de retour  
 Pointeur vers le bloc de mémoire qui a été alloué ou `NULL` si l'opération a échoué.  
  
## Notes  
 `_aligned_malloc_dbg` est une version de débogage de la fonction [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md).  Quand [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, chaque appel à `_aligned_malloc_dbg` est réduit à un appel à `_aligned_malloc`.  `_aligned_malloc` et `_aligned_malloc_dbg` allouent toutes deux un bloc de mémoire dans le tas de base, mais `_aligned_malloc_dbg` propose plusieurs fonctionnalités de débogage : des mémoires tampons de chaque côté de la partie utilisateur du bloc pour vérifier la présence de fuites et des informations `filename`\/`linenumber` pour déterminer l'origine des demandes d'allocation.  
  
 `_aligned_malloc_dbg` alloue le bloc de mémoire avec un peu plus d'espace que la valeur `size` demandée.  L'espace supplémentaire est utilisé par le gestionnaire de tas de débogage pour lier les blocs de mémoire de débogage et pour fournir à l'application des informations sur les en\-têtes de débogage et les mémoires tampons de remplacement.  Quand le bloc est alloué, la partie utilisateur du bloc est renseignée avec la valeur 0xCD et chaque mémoire tampon de remplacement est renseignée avec la valeur 0xFD.  
  
 `_aligned_malloc_dbg` affecte la valeur `ENOMEM` à `errno` si une allocation de mémoire échoue ou si la quantité de mémoire nécessaire \(y compris la surcharge mentionnée précédemment\) dépasse `_HEAP_MAXREQ`.  Pour plus d'informations sur ce code d'erreur et d'autres, voir [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  De plus, `_aligned_malloc_dbg` valide ses paramètres.  Si `alignment` n'est pas une puissance de 2 ou `size` est égal à zéro, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction retourne `NULL` et affecte la valeur `EINVAL` à `errno`.  
  
 Pour plus d'informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, voir [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Pour plus d'informations sur les types de blocs d'allocation et sur leur utilisation, voir [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Pour plus d'informations sur les différences entre l'appel à une fonction de tas standard et sa version de débogage dans une build de débogage d'une application, voir [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_aligned_malloc_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)