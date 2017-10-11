---
title: Erreur du compilateur C3255 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3255
dev_langs:
- C++
helpviewer_keywords:
- C3255
ms.assetid: 877ffca2-fd92-44b6-9060-6091b928b1c1
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 86052e8ffa7e9ba9627a290318dbe6115af3d36c
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3255"></a>Erreur du compilateur C3255
'type valeur' : Impossible d’allouer dynamiquement cet objet de type valeur sur un tas natif  
  
 Les instances d’un type valeur (voir [les Classes et Structs](../../windows/classes-and-structs-cpp-component-extensions.md)) qui contient des membres managés peuvent être créées sur la pile, mais pas sur le tas.  
  
 L’exemple suivant génère l’erreur C3255 :  
  
```  
// C3255.cpp  
// compile with: /clr  
using namespace System;  
value struct V {  
   Object^ o;  
};  
  
value struct V2 {  
   int i;  
};  
  
int main() {  
   V* pv = new V;   // C3255  
   V2* pv2 = new V2;  
   V v2;  
}  
```  

