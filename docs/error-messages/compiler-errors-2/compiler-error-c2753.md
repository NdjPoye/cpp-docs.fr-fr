---
title: Erreur du compilateur C2753 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2753
dev_langs:
- C++
helpviewer_keywords:
- C2753
ms.assetid: 92bfeeac-524a-4a8e-9a4f-fb8269055826
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: bd852023fe4e8cf9b1845ed1a4d53f937b039211
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2753"></a>Erreur du compilateur C2753
'*modèle*' : une spécialisation partielle ne peuvent pas correspondre la liste d’arguments pour le modèle principal  
  
 Si la liste d’arguments template correspond à la liste de paramètres, le compilateur le traite comme le même modèle. Définition de deux fois le même modèle n’est pas autorisée.  
  
## <a name="example"></a>Exemple
 L’exemple suivant génère l’erreur C2753 et illustre une méthode pour résoudre ce problème :  
  
```cpp  
// C2753.cpp  
// compile with: cl /c C2753.cpp
template<class T>  
struct A {};  
  
template<class T>  
struct A<T> {};   // C2753  
// try the following line instead  
// struct A<int> {};  
  
template<class T, class U, class V, class W, class X>  
struct B {};  
```
