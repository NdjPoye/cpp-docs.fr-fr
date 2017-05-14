---
title: "Du compilateur (niveau 4) d’avertissement C4463 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4463
dev_langs:
- C++
helpviewer_keywords:
- C4463
ms.assetid: a07ae70c-db4e-472b-8b58-9137d9997323
caps.latest.revision: 0
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 128bd124c2536d86c8b673b54abc4b5505526b41
ms.openlocfilehash: 63f9c9172daffe11f91c521f514f0e8e53331b22
ms.contentlocale: fr-fr
ms.lasthandoff: 05/10/2017

---
# <a name="compiler-warning-level-4-c4463"></a>Du compilateur (niveau 4) d’avertissement C4463  
  
> dépassement de capacité ; affectation *valeur* au champ de bits qui peut contenir uniquement des valeurs à partir de *low_value* à *high_value*  
  
Assigné *valeur* est en dehors de la plage de valeurs que le champ de bits peut contenir. Les types de champ de bits signés utilisent le poids de bits pour la connexion, par conséquent, si  *n*  est la taille de champ de bits, la plage pour les champs de bits signés est de -2<sup>n-1</sup> 2<sup>n-1</sup>-1, tandis que les champs de bits non signés ont une plage de 0 à 2<sup>n</sup>-1.  
  
## <a name="example"></a>Exemple  
  
Cet exemple génère C4463, car elle tente d’assigner une valeur de 3 à un champ de bits de type `int` avec une taille de 2, qui a une plage comprise entre -2 à 1.  
  
Pour résoudre ce problème, vous pouvez modifier la valeur assignée à un élément dans la plage autorisée. Si le champ de bits est destiné à contenir des valeurs non signées dans la plage de 0 à 3, vous pouvez modifier le type de déclaration pour `unsigned`. Si le champ est destiné à contenir des valeurs dans plage de -4 à 3, vous pouvez modifier la taille de champ de bits à 3.  
  
```cpp  
// C4463_overflow.cpp
// compile with: cl /W4 /EHsc C4463_overflow.cpp
struct S { 
    int x : 2; // int type treats high-order bit as sign
}; 

int main() { 
    S s; 
    s.x = 3; // warning C4463: overflow; assigning 3 
    // to bit-field that can only hold values from -2 to 1 
    // To fix, change assigned value to fit in range,
    // increase size of bitfield, and/or change base type 
    // to unsigned.
} 
```  

