---
title: "_aligned_msize_dbg | Microsoft Docs"
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
  - "_aligned_msize_dbg"
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
  - "_aligned_msize_dbg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_msize_dbg"
ms.assetid: f1c44af0-3f66-4033-81d1-d71d3afecba0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_msize_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne la taille d'un bloc de mémoire alloué dans le tas \(version Debug uniquement\).  
  
## Syntaxe  
  
```  
size_t _aligned_msize_dbg(  
   void *memblock,  
   size_t alignment,  
   size_t offset  
);  
```  
  
#### Paramètres  
 \[in\] `memblock`  
 Pointeur du bloc de mémoire.  
  
 \[in\] `alignment`  
 La valeur d'alignement, qui doit être une puissance entière de 2.  
  
 \[in\] `offset`  
 L'offset dans l'allocation de mémoire pour forcer l'alignement.  
  
## Valeur de retour  
 Retourne la taille \(en octets\) en entier non signé.  
  
## Notes  
 Les valeurs de `alignment` et `offset` doivent être identiques aux valeurs passées à la fonction qui a alloué le bloc.  
  
 `_aligned_msize_dbg` est une version Debug de la fonction [\_aligned\_msize](../../c-runtime-library/reference/aligned-msize.md).  Lorsque [\_DEBUG](../../c-runtime-library/debug.md) n'est pas défini, chaque appel à `_aligned_msize_dbg` est réduit à un appel à `_aligned_msize`.  `_aligned_msize` et `_aligned_msize_dbg` calculent la taille d'un bloc de mémoire dans le tas de base, mais `_aligned_msize_dbg` ajoute une fonctionnalité de débogage : Elle inclut les mémoires tampons de chaque côté de la partie utilisateur du bloc de mémoire dans la taille retournée.  
  
 Cette fonction valide son paramètre.  Si `memblock` est un pointeur Null ou `alignment` n'est pas une puissance de 2, `_msize` appelle un gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'erreur est gérée, cette fonction affecte `errno` à `EINVAL` et retourne \-1.  
  
 Pour obtenir des informations sur la façon dont les blocs de mémoire sont alloués, initialisés, et gérés dans la version Debug du tas de base, consultez [Détails du tas de débogage CRT](../Topic/CRT%20Debug%20Heap%20Details.md).  Pour obtenir des informations sur les types de bloc d'allocation et leur utilisation, consultez [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  Pour obtenir des informations sur les différences entre appeler une fonction standard du tas et sa version Debug dans une version debug d'une application, consultez [Versions Debug des fonctions d'allocation du tas](../Topic/Debug%20Versions%20of%20Heap%20Allocation%20Functions.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_aligned_msize_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Seulement les versions debug des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)