---
title: "_InterlockedExchangeAdd, fonctions intrins&#232;ques | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedExchangeAdd64_nf"
  - "_InterlockedExchangeAdd64_rel"
  - "_InterlockedExchangeAdd16_rel"
  - "_InterlockedExchangeAdd_acq"
  - "_InterlockedExchangeAdd_nf"
  - "_InterlockedExchangeAdd_rel"
  - "_InterlockedExchangeAdd8_acq"
  - "_InterlockedExchangeAdd16_nf"
  - "_InterlockedExchangeAdd_acq_cpp"
  - "_InterlockedExchangeAdd64_acq_cpp"
  - "_InterlockedExchangeAdd16_acq"
  - "_InterlockedExchangeAdd_HLERelease"
  - "_InterlockedExchangeAdd64_cpp"
  - "_InterlockedExchangeAdd64_HLERelease"
  - "_InterlockedExchangeAdd64_acq"
  - "_InterlockedExchangeAdd8"
  - "_InterlockedExchangeAdd64"
  - "_InterlockedExchangeAdd8_nf"
  - "_InterlockedExchangeAdd16"
  - "_InterlockedExchangeAdd64_rel_cpp"
  - "_InterlockedExchangeAdd_cpp"
  - "_InterlockedExchangeAdd8_rel"
  - "_InterlockedExchangeAdd_HLEAcquire"
  - "_InterlockedExchangeAdd64_HLEAcquire"
  - "_InterlockedExchangeAdd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedExchangeAdd, intrinsèque"
  - "_InterlockedExchangeAdd_acq, intrinsèque"
  - "_InterlockedExchangeAdd_HLEAcquire, intrinsèque"
  - "_InterlockedExchangeAdd_HLERelease, intrinsèque"
  - "_InterlockedExchangeAdd_nf, intrinsèque"
  - "_InterlockedExchangeAdd_rel, intrinsèque"
  - "_InterlockedExchangeAdd16, intrinsèque"
  - "_InterlockedExchangeAdd16_acq, intrinsèque"
  - "_InterlockedExchangeAdd16_nf, intrinsèque"
  - "_InterlockedExchangeAdd16_rel, intrinsèque"
  - "_InterlockedExchangeAdd64, intrinsèque"
  - "_InterlockedExchangeAdd64_acq, intrinsèque"
  - "_InterlockedExchangeAdd64_HLEAcquire, intrinsèque"
  - "_InterlockedExchangeAdd64_HLERelease, intrinsèque"
  - "_InterlockedExchangeAdd64_nf, intrinsèque"
  - "_InterlockedExchangeAdd64_rel, intrinsèque"
  - "_InterlockedExchangeAdd8, intrinsèque"
  - "_InterlockedExchangeAdd8_acq, intrinsèque"
  - "_InterlockedExchangeAdd8_nf, intrinsèque"
  - "_InterlockedExchangeAdd8_rel, intrinsèque"
  - "InterlockedExchangeAdd, intrinsèque"
  - "InterlockedExchangeAdd_acq, intrinsèque"
  - "InterlockedExchangeAdd_rel, intrinsèque"
  - "InterlockedExchangeAdd64, intrinsèque"
  - "InterlockedExchangeAdd64_acq, intrinsèque"
  - "InterlockedExchangeAdd64_rel, intrinsèque"
ms.assetid: 25809e1f-9c60-4492-9f7c-0fb59c8d13d2
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _InterlockedExchangeAdd, fonctions intrins&#232;ques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Fournir la prise en charge intrinsèque du compilateur pour la fonction Win32 [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)] [\_InterlockedExchangeAdd Intrinsic Functions](../intrinsics/interlockedexchangeadd-intrinsic-functions.md).  
  
## Syntaxe  
  
```  
long _InterlockedExchangeAdd(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_acq(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_rel(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_nf(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_HLEAcquire(    long volatile * Addend,    long Value ); long _InterlockedExchangeAdd_HLERelease(    long volatile * Addend,    long Value ); char _InterlockedExchangeAdd8(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_acq(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_rel(    char volatile * Addend,    char Value ); char _InterlockedExchangeAdd8_nf(    char volatile * Addend,    char Value ); short _InterlockedExchangeAdd16(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_acq(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_rel(    short volatile * Addend,    short Value ); short _InterlockedExchangeAdd16_nf(    short volatile * Addend,    short Value ); __int64 _InterlockedExchangeAdd64(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_acq(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_rel(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_nf(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_HLEAcquire(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedExchangeAdd64_HLERelease(    __int64 volatile * Addend,    __int64 Value );   
```  
  
#### Paramètres  
 \[in, out\] `Addend`  
 Valeur à laquelle il faut ajouter ; remplacée par le résultat de l'addition.  
  
 \[in\] `Value`  
 Valeur à ajouter.  
  
## Valeur de retour  
 La valeur de retour est la valeur initiale de la variable vers laquelle pointe le paramètre `Addend`.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|Header|  
|-----------------|------------------|------------|  
|`_InterlockedExchangeAdd`, `_InterlockedExchangeAdd8`, `_InterlockedExchangeAdd16`, `_InterlockedExchangeAdd64`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedExchangeAdd_acq`, `_InterlockedExchangeAdd_rel`, `_InterlockedExchangeAdd_nf`, `_InterlockedExchangeAdd8_acq`, `_InterlockedExchangeAdd8_rel`, `_InterlockedExchangeAdd8_nf`,`_InterlockedExchangeAdd16_acq`, `_InterlockedExchangeAdd16_rel`, `_InterlockedExchangeAdd16_nf`, `_InterlockedExchangeAdd64_acq`, `_InterlockedExchangeAdd64_rel`, `_InterlockedExchangeAdd64_nf`|ARM|\<intrin.h\>|  
|`_InterlockedExchangeAdd_HLEAcquire`, `_InterlockedExchangeAdd_HLERelease`, `_InterlockedExchangeAdd64_HLEAcquire`, `_InterlockedExchangeAdd64_HLErelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Notes  
 Il existe plusieurs variantes de `_InterlockedExchangeAdd` qui varient selon les types de données qu'elles impliquent et l'utilisation d'une sémantique acquire ou release spécifique au processeur.  
  
 La fonction `_InterlockedExchangeAdd` opère sur les valeurs entières de 32 bits, `_InterlockedExchangeAdd8` sur les valeurs entières de 8 bits, `_InterlockedExchangeAdd16` sur les valeurs entières de 16 bits, et `_InterlockedExchangeAdd64` sur les valeurs entières de 64 bits.  
  
 Sur les plateformes ARM, utilisez les fonctions intrinsèques avec des suffixes `_acq` et `_rel` si vous devez acquérir et libérer des éléments de la sémantique, comme le début et la fin d'une section critique.  Les fonctions intrinsèques avec un suffixe `_nf` \(pour « no fence », « pas de délimitation »\) n'agissent pas comme une barrière mémoire.  
  
 Sur les plateformes Intel qui prennent en charge les instructions HLE \(Hardware Lock Elision\), les fonctions intrinsèques avec les suffixes `_HLEAcquire` et `_HLERelease` comprennent une indication pour le processeur qui peut accélérer les performances en éliminant une étape d'écriture de verrou dans le matériel.  Si ces fonctions intrinsèques sont appelées sur des plateformes qui ne prennent pas en charge HLE, l'indication est ignorée.  
  
 Ces routines sont disponibles seulement comme fonctions intrinsèques.  Par conséquent, elles sont intrinsèques que [\/Oi](../build/reference/oi-generate-intrinsic-functions.md) ou [\#pragma intrinsic](../preprocessor/intrinsic.md) soit utilisé ou non.  Vous ne pouvez pas utiliser [\#pragma function](../preprocessor/function-c-cpp.md) sur ces fonctions intrinsèques.  
  
## Exemple  
 Pour obtenir un exemple de l'utilisation de `_InterlockedExchangeAdd`, consultez [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)