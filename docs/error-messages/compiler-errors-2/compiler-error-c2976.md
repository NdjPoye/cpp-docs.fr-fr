---
title: Erreur du compilateur C2976 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2976
dev_langs:
- C++
helpviewer_keywords:
- C2976
ms.assetid: d9bf9836-325e-4f72-a7e3-a67cf19d32e7
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 49250abe3cef048b15f7af87f643002640fe6bf5
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2976"></a>Erreur du compilateur C2976
'identificateur' : les arguments de type insuffisants  
  
 Un générique ou modèle il manque un ou plusieurs arguments réels. Vérifiez la déclaration du générique ou du modèle pour connaître le nombre de paramètres approprié.  
  
 Cette erreur peut être dû à l’absence d’arguments template dans les composants de la bibliothèque C++ Standard.  
  
 L’exemple suivant génère l’erreur C2976 :  
  
```  
// C2976.cpp  
template <class T>   
struct TC {  
   T t;  
};  
int main() {  
   TC<>* t;   // C2976  
   TC<int>* t2;   // OK  
}  
```  
  
 L’erreur C2976 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2976b.cpp  
// compile with: /clr  
generic <class T>  
ref struct GC {  
   T t;  
};  
  
int main() {  
   GC<>^ g;   // C2976  
   GC<int>^ g2;   // OK  
}  
```
