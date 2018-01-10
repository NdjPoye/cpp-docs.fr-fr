---
title: Erreur du compilateur C2683 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2683
dev_langs: C++
helpviewer_keywords: C2683
ms.assetid: db605e4f-601b-4d05-92a1-c43ca24de08d
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b02f157fbbb2e5b3e271f5df0803ece6ef0585a9
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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