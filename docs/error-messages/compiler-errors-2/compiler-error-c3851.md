---
title: Erreur du compilateur C3851 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3851
dev_langs:
- C++
helpviewer_keywords:
- C3851
ms.assetid: da30c21c-33aa-4439-8fb3-2f5021ea4985
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: ed2a62b859e37455041171c81bb6830db372c697
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3851"></a>Erreur du compilateur C3851
« char » : un nom de caractère universel ne peut pas désigner un caractère du jeu de caractères de base  
  
 Dans le code compilé en C++, vous ne pouvez pas utiliser un nom de caractère universel représentant un caractère dans le jeu de caractères source de base en dehors d’une chaîne ou d’un littéral de caractère. Pour plus d’informations, consultez [Character Sets](../../cpp/character-sets2.md). Dans le code compilé en tant que C, vous ne pouvez pas utiliser un nom de caractère universel pour les caractères dans la plage 0x20-0x7f, inclusivement, excepté pour 0x24 (« $ »), 0x40 (« @ ») ou 0x60 (« ` »).  
  
 Les exemples suivants génèrent C3851 et montrent comment résoudre le problème :  
  
```cpp  
// C3851.cpp  
int main()  
{  
   int test1_\u0041 = 0;   // C3851, \u0041 = 'A' in basic character set  
   int test2_A = 0;        // OK  
}  
```
