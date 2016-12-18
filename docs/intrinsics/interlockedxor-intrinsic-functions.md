---
title: "_InterlockedXor, fonctions intrins&#232;ques | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedXor_nf"
  - "_InterlockedXor_np"
  - "_InterlockedXor64_HLERelease"
  - "_InterlockedXor8_acq"
  - "_InterlockedXor64_acq"
  - "_InterlockedXor64_rel"
  - "_InterlockedXor64_nf"
  - "_InterlockedXor_acq"
  - "_InterlockedXor16"
  - "_InterlockedXor64_np"
  - "_InterlockedXor64"
  - "_InterlockedXor_HLEAcquire"
  - "_InterlockedXor_HLERelease"
  - "_InterlockedXor_cpp"
  - "_InterlockedXor16_rel"
  - "_InterlockedXor8_rel"
  - "_InterlockedXor8"
  - "_InterlockedXor64_HLEAcquire"
  - "_InterlockedXor16_nf"
  - "_InterlockedXor16_acq"
  - "_InterlockedXor16_np"
  - "_InterlockedXor8_fn"
  - "_InterlockedXor8_np"
  - "_InterlockedXor64_cpp"
  - "_InterlockedXor_rel"
  - "_InterlockedXor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedXor, intrinsèque"
  - "_InterlockedXor64, intrinsèque"
  - "InterlockedXor, intrinsèque"
  - "InterlockedXor64, intrinsèque"
ms.assetid: faef1796-cb5a-4430-b1e2-9d5eaf9b4a91
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedXor, fonctions intrins&#232;ques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Effectuer une opération ou exclusif \(XOR\) atomique au niveau du bit sur une variable partagée par plusieurs threads.  
  
## Syntaxe  
  
```  
long _InterlockedXor(    long volatile * Value,    long Mask ); long _InterlockedXor_acq(    long volatile * Value,    long Mask ); long _InterlockedXor_HLEAcquire(    long volatile * Value,    long Mask ); long _InterlockedXor_HLERelease(    long volatile * Value,    long Mask ); long _InterlockedXor_nf(    long volatile * Value,    long Mask ); long _InterlockedXor_np(    long volatile * Value,    long Mask ); long _InterlockedXor_rel(    long volatile * Value,    long Mask ); char _InterlockedXor8(    char volatile * Value,    char Mask ); char _InterlockedXor8_acq(    char volatile * Value,    char Mask ); char _InterlockedXor8_nf(    char volatile * Value,    char Mask ); char _InterlockedXor8_np(    char volatile * Value,    char Mask ); char _InterlockedXor8_rel(    char volatile * Value,    char Mask ); short _InterlockedXor16(    short volatile * Value,    short Mask ); short _InterlockedXor16_acq(    short volatile * Value,    short Mask ); short _InterlockedXor16_nf (    short volatile * Value,    short Mask ); short _InterlockedXor16_np (    short volatile * Value,    short Mask ); short _InterlockedXor16_rel(    short volatile * Value,    short Mask ); __int64 _InterlockedXor64(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_acq(    __int64 volatile * Value,    __int64 Mask );  __int64 _InterlockedXor64_HLEAcquire(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_HLERelease(    __int64 volatile * Value,    __int64 Mask );  __int64 _InterlockedXor64_nf(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_np(    __int64 volatile * Value,    __int64 Mask ); __int64 _InterlockedXor64_rel(    __int64 volatile * Value,    __int64 Mask );  
```  
  
#### Paramètres  
 \[in, out\] `Value`  
 Pointeur vers le premier opérande, à remplacer par le résultat.  
  
 \[in\] `Mask`  
 Deuxième opérande.  
  
## Valeur de retour  
 Valeur d'origine du premier opérande.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|Header|  
|-----------------|------------------|------------|  
|`_InterlockedXor`, `_InterlockedXor8`, `_InterlockedXor16`, `_InterlockedXor64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedXor_acq`, `_InterlockedXor_nf`, `_InterlockedXor_rel`, `_InterlockedXor8_acq`, `_InterlockedXor8_nf`, `_InterlockedXor8_rel`, `_InterlockedXor16_acq`, `_InterlockedXor16_nf`, `_InterlockedXor16_rel`, `_InterlockedXor64_acq`, `_InterlockedXor64_nf`, `_InterlockedXor64_rel`,|ARM|\<intrin.h\>|  
|`_InterlockedXor_np`, `_InterlockedXor8_np`, `_InterlockedXor16_np`, `_InterlockedXor64_np`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedXor_HLEAcquire`, `_InterlockedXor_HLERelease`, `_InterlockedXor64_HLEAcquire`, `_InterlockedXor64_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Notes  
 Le nombre dans le nom de chaque fonction spécifie la taille en bits des arguments.  
  
 Sur les plateformes ARM, utilisez les fonctions intrinsèques avec des suffixes `_acq` et `_rel` si vous devez acquérir et libérer des éléments de la sémantique, comme le début et la fin d'une section critique.  Les fonctions intrinsèques ARM avec un suffixe `_nf` \(pour « no fence », « pas de délimitation »\) n'agissent pas comme une barrière mémoire.  
  
 Les fonctions intrinsèques avec un suffixe `_np` \(pour « no prefetch », « pas de prérécupération »\) empêchent l'insertion par le compilateur d'une possible opération de prérécupération.  
  
 Sur les plateformes Intel qui prennent en charge les instructions HLE \(Hardware Lock Elision\), les fonctions intrinsèques avec les suffixes `_HLEAcquire` et `_HLERelease` comprennent une indication pour le processeur qui peut accélérer les performances en éliminant une étape d'écriture de verrou dans le matériel.  Si ces fonctions intrinsèques sont appelées sur des plateformes qui ne prennent pas en charge HLE, l'indication est ignorée.  
  
## Exemple  
  
```  
// _InterLockedXor.cpp  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedXor)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FFFF00;  
        long retval;  
        retval = _InterlockedXor(&data1, data2);  
        printf_s("0x%x 0x%x 0x%x", data1, data2, retval);   
}  
```  
  
  **0xffff0000 0xffff00 0xff00ff00**   
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)