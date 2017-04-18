---
title: Compilateur avertissement (niveau 1) C4145 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4145
dev_langs:
- C++
helpviewer_keywords:
- C4145
ms.assetid: 0440777a-cca2-4159-aff5-e67a254ad64a
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
ms.openlocfilehash: c3537ab02acf0b4eb1b7b78e159f9e12b90840ba
ms.lasthandoff: 04/12/2017

---
# <a name="compiler-warning-level-1-c4145"></a>Avertissement du compilateur (niveau 1) C4145
'expression1' : expression relationnelle comme expression de switch ; risque de confusion avec 'expression2'  
  
 Une instruction `switch` utilise une expression relationnelle comme son expression de contrôle, ce qui produit une valeur booléenne pour les instructions **case** . Voulez-vous utiliser *expression2*?  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’avertissement C4145 :  
  
```  
// C4145.cpp  
// compile with: /W1  
int main() {  
   int i = 0;  
   switch(i == 1) {   // C4145, use i instead of i == 1 to resolve  
      case 1:  
         break;  
      default:  
         break;  
   }  
}  
```
