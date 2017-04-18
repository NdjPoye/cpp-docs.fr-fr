---
title: Compilateur avertissement (niveau 1) C4807 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4807
dev_langs:
- C++
helpviewer_keywords:
- C4807
ms.assetid: 089c9f87-fd81-402e-9826-66a8ef1ef1fe
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 0d9cbb01d1ad0f2ea65d59334cb88140ef18fce0
ms.openlocfilehash: 1548905fd242707c1cdf01c2cbc51b5c9e50cfce
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4807"></a>Avertissement du compilateur (niveau 1) C4807
'operation' : mélange risqué de type 'type' et champ de bits signé de type 'type'  
  
 Cet avertissement est généré lors de la comparaison d’un champ de bits signé à un bit avec une variable `bool` . Un champ de bits signé à un bit peut seulement contenir les valeurs -1 ou 0. Il est risqué de le comparer à `bool`. Aucun avertissement n’est généré sur la combinaison de `bool` et de champs de bits non signés à un bit, car ils sont identiques à `bool` et ne peuvent contenir que 0 ou 1.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4807 :  
  
```  
// C4807.cpp  
// compile with: /W1  
typedef struct bitfield {  
   signed mybit : 1;  
} mybitfield;  
  
int main() {  
   mybitfield bf;  
   bool b = true;  
  
   // try..  
   // int b = true;  
  
   bf.mybit = -1;  
   if (b == bf.mybit) {   // C4807  
      b = false;  
   }  
}  
```
