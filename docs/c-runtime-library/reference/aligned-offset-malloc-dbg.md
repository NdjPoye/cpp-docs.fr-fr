---
title: "_aligned_offset_malloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_aligned_offset_malloc_dbg"
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
  - "_aligned_offset_malloc_dbg"
  - "aligned_offset_malloc_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_offset_malloc_dbg (fonction)"
  - "aligned_offset_malloc_dbg (fonction)"
ms.assetid: 6c242307-c59e-4d63-aae5-d8cbec8e021c
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# _aligned_offset_malloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Alloue de la mémoire sur une limite d'alignement spécifiée \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
void * _aligned_offset_malloc_dbg(  
   size_t size,   
   size_t alignment,   
   size_t offset,  
   const char *filename,  
   int linenumber   
);  
```  
  
#### Paramètres  
 \[in\] `size`  
 La taille de l'allocation de mémoire demandée.  
  
 \[in\] `alignment`  
 La valeur d'alignement, qui doit être une puissance entière de 2.  
  
 \[in\] `offset`  
 L'offset dans l'allocation de mémoire pour forcer l'alignement.  
  
 \[in\] `filename`  
 Le pointeur du nom du fichier source qui a demandé l'opération d'allocation ou NULL.  
  
 \[in\] `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou NULL.  
  
## Valeur de retour  
 Un pointeur vers le bloc de mémoire alloué ou `NULL` si l'opération a échoué.  
  
## Notes  
 `_aligned_offset_malloc_dbg` est une version Debug de la fonction [\_aligned\_offset\_malloc](../../c-runtime-library/reference/aligned-offset-malloc.md).  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, chaque appel à `_aligned_offset_malloc_dbg` est réduit à un appel à `_aligned_offset_malloc`.  A la fois `_aligned_offset_malloc` et `_aligned_offset_malloc_dbg` redimensionnent un bloc de mémoire dans la pile de base, mais `_aligned_offset_malloc_dbg` offre plusieurs fonctionnalités de débogage : mémoires tampons de chaque côté de la partie utilisateur du bloc à pour détecter les fuites, un paramètre de type de bloc pour suivre des types spécifiques d'allocation, et `filename`\/`linenumber` pour déterminer l'origine des demandes d'allocation.  
  
 `_aligned_offset_malloc_dbg` alloue le bloc de mémoire avec légèrement plus d'espace que `size`demandé.  L'espace supplémentaire est utilisé par le gestionnaire du tas de débogage pour lier les blocs de mémoire de débogage, pour fournir à l'application les informations d'en\-tête du débogage et pour remplacer des mémoires tampons.  Lorsque le bloc est alloué, la partie utilisateur du bloc est remplie avec la valeur 0xCD et chacune des mémoires tampons de remplacement est remplie avec 0xFD.  
  
 `_aligned_offset_malloc_dbg` est utile dans les cas où il est nécessaire dans un élément imbriqué ; par exemple, si un alignement est nécessaire dans une classe imbriquée.  
  
 `_aligned_offset_malloc_dbg` est basé sur `malloc`; pour plus d'informations, consultez [malloc](../../c-runtime-library/reference/malloc.md).  
  
 Cette fonction alloue à `errno` la valeur `ENOMEM` si l'allocation de mémoire a échoué ou si la taille demandée est supérieure à `_HEAP_MAXREQ`.  Pour plus d'informations sur `errno`, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  Aussi, `_aligned_offset_malloc` valide ses paramètres.  Si `alignment` n'est pas une puissance de 2 ou si `offset` est supérieur ou égal à `size` et une valeur différente de zéro, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoie `NULL` et définit `errno` avec la valeur `EINVAL`.  
  
 Pour obtenir des informations sur la façon dont les blocs de mémoire sont alloués, initialisés, et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Pour obtenir des informations sur les types de bloc d'allocation et leur utilisation, consultez [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_aligned_offset_malloc_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)