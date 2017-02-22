---
title: "_InterlockedExchangePointer, fonctions intrins&#232;ques | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedExchangePointer_cpp"
  - "_InterlockedExchangePointer_rel"
  - "_InterlockedExchangePointer_nf"
  - "_InterlockedExchangePointer_HLERelease"
  - "_InterlockedExchangePointer_acq"
  - "_InterlockedExchangePointer"
  - "_InterlockedExchangePointer_acq_cpp"
  - "_InterlockedExchangePointer_HLEAcquire"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedExchangePointer, intrinsèque"
  - "_InterlockedExchangePointer_acq, intrinsèque"
  - "_InterlockedExchangePointer_HLEAcquire, intrinsèque"
  - "_InterlockedExchangePointer_HLERelease, intrinsèque"
  - "_InterlockedExchangePointer_nf, intrinsèque"
  - "_InterlockedExchangePointer_rel, intrinsèque"
  - "InterlockedExchangePointer, intrinsèque"
  - "InterlockedExchangePointer_acq, intrinsèque"
ms.assetid: 0eaca0b0-d79e-406b-892d-b3b462c50bbb
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _InterlockedExchangePointer, fonctions intrins&#232;ques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Effectuer une opération d'échange atomique, qui copie l'adresse passée comme deuxième argument au premier et retourne l'adresse d'origine du premier.  
  
## Syntaxe  
  
```  
void * _InterlockedExchangePointer(    void * volatile * Target,    void * Value );  void * _InterlockedExchangePointer_acq(    void * volatile * Target,    void * Value );  void * _InterlockedExchangePointer_rel(    void * volatile * Target,    void * Value );  void * _InterlockedExchangePointer_nf(    void * volatile * Target,    void * Value );  void * _InterlockedExchangePointer_HLEAcquire(    void * volatile * Target,    void * Value );  void * _InterlockedExchangePointer_HLERelease(    void * volatile * Target,    void * Value );  
```  
  
#### Paramètres  
 \[in, out\] `Target`  
 Pointeur vers le pointeur vers la valeur à échanger.  La fonction définit la valeur sur `Value` et retourne sa valeur précédente.  
  
 \[in\] `Value`  
 Valeur à échanger avec la valeur pointée par `Target`.  
  
## Valeur de retour  
 La fonction renvoie la valeur initiale indiquée par `Target`.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|Header|  
|-----------------|------------------|------------|  
|`_InterlockedExchangePointer`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedExchangePointer_acq`, `_InterlockedExchangePointer_rel`, `_InterlockedExchangePointer_nf`|ARM|\<intrin.h\>|  
|`_InterlockedExchangePointer_HLEAcquire`, `_InterlockedExchangePointer_HLERelease`|[!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)] avec prise en charge HLE|\<immintrin.h\>|  
  
 Sur l'architecture x86, `_InterlockedExchangePointer` est une macro qui appelle `_InterlockedExchange`.  
  
## Notes  
 Sur un système 64 bits, les paramètres sont 64 bits et doivent être alignés sur les limites 64 bits ; dans le cas contraire, la fonction échoue.  Sur un système 32 bits, les paramètres sont 32 bits et doivent être alignés sur les limites 32 bits.  Pour plus d'informations, consultez [align](../cpp/align-cpp.md).  
  
 Sur les plateformes ARM, utilisez les fonctions intrinsèques avec des suffixes `_acq` et `_rel` si vous devez acquérir et libérer des éléments de la sémantique, comme le début et la fin d'une section critique.  La fonction intrinsèque avec un suffixe `_nf` \(pour « no fence », « pas de délimitation »\) n'agit pas comme une barrière mémoire.  
  
 Sur les plateformes Intel qui prennent en charge les instructions HLE \(Hardware Lock Elision\), les fonctions intrinsèques avec les suffixes `_HLEAcquire` et `_HLERelease` comprennent une indication pour le processeur qui peut accélérer les performances en éliminant une étape d'écriture de verrou dans le matériel.  Si ces fonctions intrinsèques sont appelées sur des plateformes qui ne prennent pas en charge HLE, l'indication est ignorée.  
  
 Ces routines sont disponibles seulement comme fonctions intrinsèques.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)