---
title: Erreur du compilateur C2683 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2683
dev_langs:
- C++
helpviewer_keywords:
- C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
caps.latest.revision: 10
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: b3e79c1a05ac0d1fab713e2dfa97c9da740088bb
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2683"></a>Erreur du compilateur C2683
'cast' : 'type' n’est pas un type polymorphe  
  
 Vous ne pouvez pas utiliser [dynamic_cast](../../cpp/dynamic-cast-operator.md) à convertir à partir d’une classe non polymorphe (une classe sans fonctions virtuelles).  
  
 Vous pouvez utiliser [static_cast](../../cpp/static-cast-operator.md) pour effectuer des conversions de types non polymorphes. Toutefois, `static_cast` n’effectue pas une vérification de l’exécution.  
  
 L’exemple suivant génère l’erreur C2683 :  
  
```  
// C2683.cpp  
// compile with: /c  
class B { };  
class D : public B { };  
  
void f(B* pb) {  
   D* pd1 = dynamic_cast<D*>(pb);  // C2683  
   D* pd1 = static_cast<D*>(pb);   // OK  
}  
```
