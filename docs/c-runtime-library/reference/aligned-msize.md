---
title: "_aligned_msize | Microsoft Docs"
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
  - "_aligned_msize"
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
  - "_aligned_msize"
  - "aligned_msize"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_aligned_msize (fonction)"
  - "aligned_msize (fonction)"
ms.assetid: 10995edc-2110-4212-9ca9-5e0220a464f4
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _aligned_msize
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne la taille d'un bloc de mémoire allouée dans le segment.  
  
## Syntaxe  
  
```  
size_t _msize(  
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
 La fonction `_aligned_msize` retourne la taille, en octets, du bloc de mémoire allouée par un appel à [\_aligned\_malloc](../../c-runtime-library/reference/aligned-malloc.md), ou [\_aligned\_realloc](../../c-runtime-library/reference/aligned-realloc.md) Les valeurs de `alignment` et `offset` doivent être identiques aux valeurs passées à la fonction qui a alloué le bloc.  
  
 Lorsque l'application est liée à une version debug des bibliothèques Runtime C, `_aligned_msize` résout [\_aligned\_msize\_dbg](../../c-runtime-library/reference/aligned-msize-dbg.md).  Pour plus d'informations sur la gestion du tas pendant le processus de débogage, consultez [The CRT Debug Heap](../Topic/CRT%20Debug%20Heap%20Details.md).  
  
 Cette fonction valide son paramètre.  Si `memblock` est un pointeur Null ou `alignment` n'est pas une puissance de 2, `_msize` appelle un gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'erreur est gérée, cette fonction affecte `errno` à `EINVAL` et retourne \-1.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_msize`|\<malloc.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)