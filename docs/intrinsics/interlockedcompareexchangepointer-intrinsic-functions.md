---
title: "_InterlockedCompareExchangePointer, fonctions intrins&#232;ques | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_InterlockedCompareExchangePointer_HLERelease"
  - "_InterlockedCompareExchangePointer_rel"
  - "_InterlockedCompareExchangePointer_acq_cpp"
  - "_InterlockedCompareExchangePointer"
  - "_InterlockedCompareExchangePointer_cpp"
  - "_InterlockedCompareExchangePointer_np"
  - "_InterlockedCompareExchangePointer_rel_cpp"
  - "_InterlockedCompareExchangePointer_HLEAcquire"
  - "_InterlockedCompareExchangePointer_acq"
  - "_InterlockedCompareExchangePointer_nf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedCompareExchangePointer, intrinsèque"
  - "_InterlockedCompareExchangePointer_acq, intrinsèque"
  - "_InterlockedCompareExchangePointer_HLEAcquire, intrinsèque"
  - "_InterlockedCompareExchangePointer_HLERelease, intrinsèque"
  - "_InterlockedCompareExchangePointer_nf, intrinsèque"
  - "_InterlockedCompareExchangePointer_np, intrinsèque"
  - "_InterlockedCompareExchangePointer_rel, intrinsèque"
  - "InterlockedCompareExchangePointer, intrinsèque"
  - "InterlockedCompareExchangePointer_acq, intrinsèque"
  - "InterlockedCompareExchangePointer_rel, intrinsèque"
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# _InterlockedCompareExchangePointer, fonctions intrins&#232;ques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Effectue une opération atomique qui stocke l'adresse `Exchange` dans l'adresse `Destination` si les adresses `Comparand` et `Destination` sont égales.  
  
## Syntaxe  
  
```  
void * _InterlockedCompareExchangePointer (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_acq (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_HLEAcquire (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_HLERelease (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_nf (    void * volatile * Destination,    void * Exchange,    void * Comparand ); void * _InterlockedCompareExchangePointer_np (    void * volatile * Destination,    void * Exchange,    void * Comparand ); long _InterlockedCompareExchangePointer_rel (    void * volatile * Destination,    void * Exchange,    void * Comparand );  
```  
  
#### Paramètres  
 \[in, out\] `Destination`  
 Pointeur vers un pointeur vers la valeur de destination.  Le signe est ignoré.  
  
 \[in\] `Exchange`  
 Pointeur d'échange.  Le signe est ignoré.  
  
 \[in\] `Comparand`  
 Pointeur à comparer à la destination.  Le signe est ignoré.  
  
## Valeur de retour  
 La valeur de retour est la valeur initiale de la destination.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|Header|  
|-----------------|------------------|------------|  
|`_InterlockedCompareExchangePointer`|x86, ARM, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<intrin.h\>|  
|`_InterlockedCompareExchangePointer_acq`, `_InterlockedCompareExchangePointer_nf`, `_InterlockedCompareExchangePointer_rel`|ARM|\<iiintrin.h\>|  
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86, [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)]|\<immintrin.h\>|  
  
## Notes  
 `_InterlockedCompareExchangePointer` effectue une comparaison atomique de l'adresse `Destination` à l'adresse `Comparand`.  Si l'adresse `Destination` est égale à l'adresse `Comparand`, l'adresse `Exchange` est stockée dans l'adresse spécifiée par `Destination`.  Dans le cas contraire, aucune opération n'est effectuée.  
  
 `_InterlockedCompareExchangePointer` fournit la prise en charge intrinsèque du compilateur pour la fonction Win32 [\_InterlockedCompareExchangePointer](http://msdn.microsoft.com/library/ff547863.aspx) du [!INCLUDE[winsdkshort](../atl/reference/includes/winsdkshort_md.md)].  
  
 Pour obtenir un exemple de l'utilisation de `_InterlockedCompareExchangePointer`, consultez [\_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).  
  
 Sur les plateformes ARM, utilisez les fonctions intrinsèques avec des suffixes `_acq` et `_rel` si vous devez acquérir et libérer des éléments de la sémantique, comme le début et la fin d'une section critique.  Les fonctions intrinsèques ARM avec un suffixe `_nf` \(pour « no fence », « pas de délimitation »\) n'agissent pas comme une barrière mémoire.  
  
 Les fonctions intrinsèques avec un suffixe `_np` \(pour « no prefetch », « pas de prérécupération »\) empêchent l'insertion par le compilateur d'une possible opération de prérécupération.  
  
 Sur les plateformes Intel qui prennent en charge les instructions HLE \(Hardware Lock Elision\), les fonctions intrinsèques avec les suffixes `_HLEAcquire` et `_HLERelease` comprennent une indication pour le processeur qui peut accélérer les performances en éliminant une étape d'écriture de verrou dans le matériel.  Si ces fonctions intrinsèques sont appelées sur des plateformes qui ne prennent pas en charge HLE, l'indication est ignorée.  
  
 Ces routines sont disponibles seulement comme fonctions intrinsèques.  
  
## FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)