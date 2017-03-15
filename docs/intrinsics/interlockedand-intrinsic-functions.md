---
title: "_InterlockedAnd, fonctions intrins&#232;ques | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedAnd_rel"
  - "_InterlockedAnd_cpp"
  - "_InterlockedAnd8_nf"
  - "_InterlockedAnd"
  - "_InterlockedAnd_HLERelease"
  - "_InterlockedAnd8_np"
  - "_InterlockedAnd16_rel"
  - "_InterlockedAnd64_np"
  - "_InterlockedAnd_np"
  - "_InterlockedAnd64_HLERelease"
  - "_InterlockedAnd64"
  - "_InterlockedAnd64_nf"
  - "_InterlockedAnd64_HLEAcquire"
  - "_InterlockedAnd16"
  - "_InterlockedAnd16_nf"
  - "_InterlockedAnd8"
  - "_InterlockedAnd_HLEAcquire"
  - "_InterlockedAnd_acq"
  - "_InterlockedAnd16_np"
  - "_InterlockedAnd64_cpp"
  - "_InterlockedAnd64_acq"
  - "_InterlockedAnd16_acq"
  - "_InterlockedAnd8_acq"
  - "_InterlockedAnd64_rel"
  - "_InterlockedAnd_nf"
  - "_InterlockedAnd8_rel"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedAnd, intrinsèque"
  - "_InterlockedAnd_acq, intrinsèque"
  - "_InterlockedAnd_HLEAcquire, intrinsèque"
  - "_InterlockedAnd_HLERelease, intrinsèque"
  - "_InterlockedAnd_nf, intrinsèque"
  - "_InterlockedAnd_np, intrinsèque"
  - "_InterlockedAnd_rel, intrinsèque"
  - "_InterlockedAnd16, intrinsèque"
  - "_InterlockedAnd16_acq, intrinsèque"
  - "_InterlockedAnd16_nf, intrinsèque"
  - "_InterlockedAnd16_np, intrinsèque"
  - "_InterlockedAnd16_rel, intrinsèque"
  - "_InterlockedAnd64, intrinsèque"
  - "_InterlockedAnd64_acq, intrinsèque"
  - "_InterlockedAnd64_HLEAcquire, intrinsèque"
  - "_InterlockedAnd64_HLERelease, intrinsèque"
  - "_InterlockedAnd64_nf, intrinsèque"
  - "_InterlockedAnd64_np, intrinsèque"
  - "_InterlockedAnd64_rel, intrinsèque"
  - "_InterlockedAnd8, intrinsèque"
  - "_InterlockedAnd8_acq, intrinsèque"
  - "_InterlockedAnd8_nf, intrinsèque"
  - "_InterlockedAnd8_np, intrinsèque"
  - "_InterlockedAnd8_rel, intrinsèque"
  - "InterlockedAnd, intrinsèque"
  - "InterlockedAnd64, intrinsèque"
ms.assetid: ad271dc3-42cd-47d0-9f65-30d5cfeb66fc
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _InterlockedAnd, fonctions intrins&#232;ques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Sert à exécuter une opération AND atomique au niveau du bit sur une variable partagée par plusieurs threads.  
  
## Syntaxe  
  
```  
long _InterlockedAnd(    long volatile * value,    long mask ); long _InterlockedAnd_acq(    long volatile * value,    long mask ); long _InterlockedAnd_HLEAcquire(    long volatile * value,    long mask ); long _InterlockedAnd_HLERelease(    long volatile * value,    long mask ); long _InterlockedAnd_nf(    long volatile * value,    long mask ); long _InterlockedAnd_np(    long volatile * value,    long mask ); long _InterlockedAnd_rel(    long volatile * value,    long mask ); char _InterlockedAnd8(    char volatile * value,    char mask ); char _InterlockedAnd8_acq(    char volatile * value,    char mask ); char _InterlockedAnd8_nf(    char volatile * value,    char mask ); char _InterlockedAnd8_np(    char volatile * value,    char mask ); char _InterlockedAnd8_rel(    char volatile * value,    char mask ); short _InterlockedAnd16(    short volatile * value,    short mask ); short _InterlockedAnd16_acq(    short volatile * value,    short mask ); short _InterlockedAnd16_nf(    short volatile * value,    short mask ); short _InterlockedAnd16_np(    short volatile * value,    short mask ); short _InterlockedAnd16_rel(    short volatile * value,    short mask ); __int64 _InterlockedAnd64(    __int64 volatile* value,    __int64 mask ); __int64 _InterlockedAnd64_acq(    __int64 volatile* value,    __int64 mask );  __int64 _InterlockedAnd64_HLEAcquire(    __int64 volatile* value,    __int64 mask ); __int64 _InterlockedAnd64_HLERelease(    __int64 volatile* value,    __int64 mask ); __int64 _InterlockedAnd64_nf(    __int64 volatile* value,    __int64 mask ); __int64 _InterlockedAnd64_np(    __int64 volatile* value,    __int64 mask ); __int64 _InterlockedAnd64_rel(    __int64 volatile* value,    __int64 mask );  
```  
  
#### Paramètres  
 \[in, out\] `value`  
 Pointeur vers le premier opérande, à remplacer par le résultat.  
  
 \[in\] `mask`  
 Deuxième opérande.  
  
## Valeur de retour  
 Valeur d'origine du premier opérande.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|Header|  
|-----------------|------------------|------------|  
|`_InterlockedAnd`, `_InterlockedAnd8`, `_InterlockedAnd16`, `_InterlockedAnd64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedAnd_acq`, `_InterlockedAnd_nf`, `_InterlockedAnd_rel`, `_InterlockedAnd8_acq`, `_InterlockedAnd8_nf`, `_InterlockedAnd8_rel`, `_InterlockedAnd16_acq`, `_InterlockedAnd16_nf`, `_InterlockedAnd16_rel`, `_InterlockedAnd64_acq`, `_InterlockedAnd64_nf`, `_InterlockedAnd64_rel`|ARM|\<intrin.h\>|  
|`_InterlockedAnd_np`, `_InterlockedAnd8_np`, `_InterlockedAnd16_np`, `_InterlockedAnd64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedAnd_HLEAcquire`, `_InterlockedAnd_HLERelease`, `_InterlockedAnd64_HLEAcquire`, `_InterlockedAnd64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Notes  
 Le nombre dans le nom de chaque fonction spécifie la taille en bits des arguments.  
  
 Sur les plateformes ARM, utilisez les intrinsèques avec les suffixes `_acq` et `_rel` pour la sémantique Acquire et Release, comme au début et à la fin d'une section critique.  Les fonctions intrinsèques avec un suffixe `_nf` \(pour « no fence », « pas de délimitation »\) n'agissent pas comme une barrière mémoire.  
  
 Les fonctions intrinsèques avec un suffixe `_np` \(pour « no prefetch », « pas de prérécupération »\) empêchent l'insertion par le compilateur d'une possible opération de prérécupération.  
  
 Sur les plateformes Intel qui prennent en charge les instructions HLE \(Hardware Lock Elision\), les fonctions intrinsèques avec les suffixes `_HLEAcquire` et `_HLERelease` comprennent une indication pour le processeur qui peut accélérer les performances en éliminant une étape d'écriture de verrou dans le matériel.  Si ces fonctions intrinsèques sont appelées sur des plateformes qui ne prennent pas en charge HLE, l'indication est ignorée.  
  
## Exemple  
  
```  
// InterlockedAnd.cpp  
// Compile with: /Oi  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedAnd)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedAnd(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
  **0xff00 0xffff00 0xff00ff00**   
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)