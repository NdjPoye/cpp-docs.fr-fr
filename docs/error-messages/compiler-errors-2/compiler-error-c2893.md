---
title: Erreur du compilateur C2893 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2893
dev_langs:
- C++
helpviewer_keywords:
- C2893
ms.assetid: ec0cbe43-005d-45da-8742-aaeb9b81d28e
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6ad558968720a13b95fecc6860df5826b47874aa
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2893"></a>Erreur du compilateur C2893
La spécialisation du modèle de fonction 'nom de modèle'  
  
 Le compilateur a échoué spécialiser un modèle de fonction. Il peut y avoir plusieurs causes pour cette erreur.  
  
 En règle générale, la pour résoudre une erreur C2893 consiste à examiner la signature de la fonction et assurez-vous que vous pouvez instancier chaque type.  
  
## <a name="example"></a>Exemple  
 Erreur C2893 se produit parce que `f`du paramètre de modèle `T` est déduit pour être `std::map<int,int>`, mais `std::map<int,int>` n’a aucun membre `data_type` (`T::data_type` ne peut pas être instancié avec `T = std::map<int,int>`.). L’exemple suivant génère l’erreur C2893.  
  
```  
// C2893.cpp  
// compile with: /c /EHsc  
#include<map>  
using namespace std;  
class MyClass {};  
  
template<class T>   
inline typename T::data_type  
// try the following line instead  
// inline typename  T::mapped_type  
f(T const& p1, MyClass const& p2);  
  
template<class T>  
void bar(T const& p1) {  
    MyClass r;  
    f(p1,r);   // C2893  
}  
  
int main() {  
   map<int,int> m;  
   bar(m);  
}  
```
