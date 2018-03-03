---
title: Erreur du compilateur C2723 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2723
dev_langs:
- C++
helpviewer_keywords:
- C2723
ms.assetid: 86925601-2297-4cfd-94e2-2caf27c474c4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 587dd742a089a0eddc416e59563cd1e0707e662b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2723"></a>Erreur du compilateur C2723
'fonction' : spécificateur 'spécificateur' non conforme sur la définition d'une fonction  
  
 Le spécificateur ne peut pas apparaître avec une définition de fonction en dehors d'une déclaration de classe. Le spécificateur `virtual` peut être spécifié uniquement sur une déclaration de fonction membre dans une déclaration de classe.  
  
 L'exemple suivant génère l'erreur C2723 et montre comment la corriger :  
  
```  
// C2723.cpp  
struct X {  
   virtual void f();  
   virtual void g();  
};  
  
virtual void X::f() {}   // C2723  
  
// try the following line instead  
void X::g() {}  
```