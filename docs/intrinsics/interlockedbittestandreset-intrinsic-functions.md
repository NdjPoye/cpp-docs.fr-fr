---
title: "_interlockedbittestandreset, fonctions intrins&#232;ques | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_interlockedbittestandreset_rel"
  - "_interlockedbittestandreset64"
  - "_interlockedbittestandreset64_HLERelease"
  - "_interlockedbittestandreset_HLERelease"
  - "_interlockedbittestandreset_HLEAcquire"
  - "_interlockedbittestandreset_acq"
  - "_interlockedbittestandreset_cpp"
  - "_interlockedbittestandreset_nf"
  - "_interlockedbittestandreset64_cpp"
  - "_interlockedbittestandreset64_HLEAcquire"
  - "_interlockedbittestandreset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_interlockedbittestandreset, intrinsèque"
  - "_interlockedbittestandreset64, intrinsèque"
  - "lock_btr, instruction"
ms.assetid: 9bbb1442-f2e9-4dc2-b0da-97f3de3493b9
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _interlockedbittestandreset, fonctions intrins&#232;ques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Génère une instruction qui affecte la valeur zéro au bit `b` de l'adresse `a` et retourne sa valeur d'origine.  
  
## Syntaxe  
  
```  
unsigned char _interlockedbittestandreset(    long *a,    long b ); unsigned char _interlockedbittestandreset_acq(    long *a,    long b ); unsigned char _interlockedbittestandreset_HLEAcquire(    long *a,    long b ); unsigned char _interlockedbittestandreset_HLERelease(    long *a,    long b ); unsigned char _interlockedbittestandreset_nf(    long *a,    long b ); unsigned char _interlockedbittestandreset_rel(    long *a,    long b );  unsigned char _interlockedbittestandreset64(    __int64 *a,    __int64 b );  unsigned char _interlockedbittestandreset64_HLEAcquire(    __int64 *a,    __int64 b ); unsigned char _interlockedbittestandreset64_HLERelease(    __int64 *a,    __int64 b );  
```  
  
#### Paramètres  
 \[in\] `a`  
 Pointeur vers la mémoire à examiner.  
  
 \[in\] `b`  
 Position du bit à tester.  
  
## Valeur de retour  
 Valeur d'origine du bit à la position spécifiée par `b`.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|Header|  
|-----------------|------------------|------------|  
|`_interlockedbittestandreset`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_interlockedbittestandreset_acq`, `_interlockedbittestandreset_nf`, `_interlockedbittestandreset_rel`|ARM|\<intrin.h\>|  
|`_interlockedbittestandreset_HLEAcquire`, `_interlockedbittestandreset_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
|`_interlockedbittestandreset64`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_interlockedbittestandreset64_HLEAcquire`, `_interlockedbittestandreset64_HLERelease`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Notes  
 Sur les processeurs x86 et [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)], ces fonctions intrinsèques utilisent l'instruction `lock btr`, qui lit et affecte la valeur zéro au bit spécifié lors d'une opération atomique.  
  
 Sur les processeurs ARM, utilisez les intrinsèques avec les suffixes `_acq` et `_rel` pour les sémantiques Acquire et Release, par exemple au début et à la fin d'une section critique.  Les fonctions intrinsèques ARM avec un suffixe `_nf` \(pour « no fence », « pas de délimitation »\) n'agissent pas comme une barrière mémoire.  
  
 Sur les processeurs Intel qui prennent en charge les instructions HLE \(Hardware Lock Elision\), les intrinsèques ayant les suffixes `_HLEAcquire` et `_HLERelease` incluent une indication pour le processeur. Celle\-ci permet d'accélérer les performances en éliminant une étape d'écriture de verrou dans le matériel.  Si ces intrinsèques sont appelés pour des processeurs qui ne prennent pas en charge les instructions HLE, l'indication est ignorée.  
  
 Ces routines sont disponibles seulement comme fonctions intrinsèques.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)