---
title: "_InterlockedAdd, fonctions intrins&#232;ques | Microsoft Docs"
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
  - "_InterlockedAdd64_acq_cpp"
  - "_InterlockedAdd64_acq"
  - "_InterlockedAdd_acq"
  - "_InterlockedAdd_nf"
  - "_InterlockedAdd64_rel"
  - "_InterlockedAdd64"
  - "_InterlockedAdd_cpp"
  - "_InterlockedAdd_rel_cpp"
  - "_InterlockedAdd_rel"
  - "_InterlockedAdd64_rel_cpp"
  - "_InterlockedAdd64_cpp"
  - "_InterlockedAdd_acq_cpp"
  - "_InterlockedAdd64_nf"
  - "_InterlockedAdd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_InterlockedAdd, intrinsèque"
  - "_InterlockedAdd_acq, intrinsèque"
  - "_InterlockedAdd_nf, intrinsèque"
  - "_InterlockedAdd_rel, intrinsèque"
  - "_InterlockedAdd64, intrinsèque"
  - "_InterlockedAdd64_acq, intrinsèque"
  - "_InterlockedAdd64_nf, intrinsèque"
  - "_InterlockedAdd64_rel, intrinsèque"
ms.assetid: 3d319603-ea9c-4fdd-ae61-e52430ccc3b1
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _InterlockedAdd, fonctions intrins&#232;ques
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 Effectuer une addition atomique, ce qui permet de s'assurer que l'opération se termine avec succès quand plusieurs threads ont accès à une variable partagée.  
  
## Syntaxe  
  
```  
long _InterlockedAdd(    long volatile * Addend,    long Value ); long _InterlockedAdd_acq(    long volatile * Addend,    long Value ); long _InterlockedAdd_nf(    long volatile * Addend,    long Value ); long _InterlockedAdd_rel(    long volatile * Addend,    long Value ); __int64 _InterlockedAdd64(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedAdd64_acq(    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedAdd64_nf (    __int64 volatile * Addend,    __int64 Value ); __int64 _InterlockedAdd64_rel(    __int64 volatile * Addend,    __int64 Value );  
```  
  
#### Paramètres  
 \[in, out\] `Addend`  
 Pointeur vers le nombre entier auquel il faut ajouter ; remplacé par le résultat de l'addition.  
  
 \[in\] `Value`  
 Valeur à ajouter.  
  
## Valeur de retour  
 Ces deux fonctions renvoient le résultat de l'addition.  
  
## Configuration requise  
  
|Intrinsèque|Architecture|  
|-----------------|------------------|  
|`_InterlockedAdd`|ARM|  
|`_InterlockedAdd_acq`|ARM|  
|`_InterlockedAdd_nf`|ARM|  
|`_InterlockedAdd_rel`|ARM|  
|`_InterlockedAdd64`|ARM|  
|`_InterlockedAdd64_acq`|ARM|  
|`_InterlockedAdd64_nf`|ARM|  
|`_InterlockedAdd64_rel`|ARM|  
  
 **Fichier d'en\-tête** \<intrin.h\>  
  
## Notes  
 Les versions de ces fonctions avec le suffixe `_acq` ou `_rel` effectuent une addition verrouillée respectant la sémantique acquire ou release.  La sémantique acquire signifie que le résultat de l'opération est rendu visible à tous les threads et les processeurs avant toute lecture ou écriture en mémoire ultérieure.  Elle est utile lors de l'entrée d'une section critique.  La sémantique release signifie que toutes les lectures et écritures en mémoire sont obligatoirement rendues visibles à tous les threads et les processeurs avant que le résultat de l'opération soit lui\-même rendu visible.  Elle est utile quand vous quittez une section critique.  Les fonctions intrinsèques avec un suffixe `_nf` \(pour « no fence », « pas de délimitation »\) n'agissent pas comme une barrière mémoire.  
  
 Ces routines sont disponibles seulement comme fonctions intrinsèques.  
  
## Exemple  
  
```  
// interlockedadd.cpp  
// Compile with: /Oi /EHsc  
// processor: ARM  
#include <stdio.h>  
#include <intrin.h>  
  
#pragma intrinsic(_InterlockedAdd)  
  
int main()  
{  
        long data1 = 0xFF00FF00;  
        long data2 = 0x00FF0000;  
        long retval;  
        retval = _InterlockedAdd(&data1, data2);  
        printf("0x%x 0x%x 0x%x", data1, data2, retval);  
}  
```  
  
## Sortie  
  
```  
0xffffff00 0xff0000 0xffffff00  
```  
  
## Exemple  
  
```  
// interlockedadd64.cpp  
// compile with: /Oi /EHsc  
// processor: ARM  
#include <iostream>  
#include <intrin.h>  
using namespace std;  
  
#pragma intrinsic(_InterlockedAdd64)  
  
int main()  
{  
        __int64 data1 = 0x0000FF0000000000;  
        __int64 data2 = 0x00FF0000FFFFFFFF;  
        __int64 retval;  
        cout << hex << data1 << " + " << data2 << " = " ;  
        retval = _InterlockedAdd64(&data1, data2);  
        cout << data1 << endl;  
        cout << "Return value: " << retval << endl;  
}  
```  
  
## Sortie  
  
```  
ff0000000000 + ff0000ffffffff = ffff00ffffffff  
Return value: ffff00ffffffff  
```  
  
### FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [compilateur, intrinsèques](../intrinsics/compiler-intrinsics.md)   
 [Conflits avec le compilateur x86](../build/conflicts-with-the-x86-compiler.md)