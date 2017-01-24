---
title: "_malloc_dbg | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_malloc_dbg"
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
  - "malloc_dbg"
  - "_malloc_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_malloc_dbg (fonction)"
  - "malloc_dbg (fonction)"
  - "allocation de mémoire"
ms.assetid: c97eca51-140b-4461-8bd2-28965b49ecdb
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _malloc_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Alloue un bloc de mémoire dans le tas avec de l'espace supplémentaire pour un en\-tête de débogage et des mémoires tampons de remplacement \(version de débogage uniquement\).  
  
## Syntaxe  
  
```  
void *_malloc_dbg(    size_t size,    int blockType,    const char *filename,    int linenumber  );  
```  
  
#### Paramètres  
 `size`  
 Taille demandée du bloc de mémoire \(en octets\).  
  
 `blockType`  
 Type demandé du bloc de mémoire : `_CLIENT_BLOCK` ou `_NORMAL_BLOCK`.  
  
 `filename`  
 Pointeur vers le nom du fichier source qui a demandé l'opération d'allocation ou NULL.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source où l'opération d'allocation a été demandée ou NULL.  
  
 Les paramètres `filename` et `linenumber` sont disponibles uniquement quand `_malloc_dbg` a été appelée explicitement ou quand la constante du préprocesseur [\_CRTDBG\_MAP\_ALLOC](../../c-runtime-library/crtdbg-map-alloc.md) a été définie.  
  
## Valeur de retour  
 Une fois l'opération réussie, cette fonction retourne un pointeur vers la partie utilisateur du bloc de mémoire alloué, appelle la fonction du nouveau gestionnaire ou retourne Null.  Pour obtenir une description complète du comportement de retour, voir la section Notes suivante.  Pour plus d'informations sur l'utilisation de la fonction du nouveau gestionnaire, voir la fonction [malloc](../../c-runtime-library/reference/malloc.md).  
  
## Notes  
 `_malloc_dbg` est une version de débogage de la fonction [malloc](../../c-runtime-library/reference/malloc.md).  Quand [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, chaque appel à `_malloc_dbg` est réduit à un appel à `malloc`.  `malloc` et `_malloc_dbg` allouent toutes deux un bloc de mémoire dans le tas de base, mais `_malloc_dbg` propose plusieurs fonctionnalités de débogage : des mémoires tampons de chaque côté de la partie utilisateur du bloc pour vérifier la présence de fuites, un paramètre de type de bloc pour effectuer le suivi de types d'allocation spécifiques et des informations `filename`\/`linenumber` pour déterminer l'origine des demandes d'allocation.  
  
 `_malloc_dbg` alloue le bloc de mémoire avec un peu plus d'espace que la valeur `size` demandée.  L'espace supplémentaire est utilisé par le gestionnaire de tas de débogage pour lier les blocs de mémoire de débogage et pour fournir à l'application des informations sur les en\-têtes de débogage et les mémoires tampons de remplacement.  Quand le bloc est alloué, la partie utilisateur du bloc est renseignée avec la valeur 0xCD et chaque mémoire tampon de remplacement est renseignée avec la valeur 0xFD.  
  
 `_malloc_dbg` affecte la valeur `ENOMEM` à `errno` si une allocation de mémoire échoue ou si la quantité de mémoire nécessaire \(y compris la surcharge mentionnée précédemment\) dépasse `_HEAP_MAXREQ`.  Pour plus d'informations sur ce code d'erreur et d'autres, voir [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Pour plus d'informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, voir [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Pour plus d'informations sur les types de blocs d'allocation et sur leur utilisation, voir [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Pour plus d'informations sur les différences entre l'appel à une fonction de tas standard et sa version de débogage dans une build de débogage d'une application, voir [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_malloc_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
 Pour obtenir un exemple d'utilisation de `_malloc_dbg`, voir [crt\_dbg1](http://msdn.microsoft.com/fr-fr/17b4b20c-e849-48f5-8eb5-dca6509cbaf9).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, voir [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_calloc\_dbg](../../c-runtime-library/reference/calloc-dbg.md)   
 [\_calloc\_dbg](../../c-runtime-library/reference/calloc-dbg.md)