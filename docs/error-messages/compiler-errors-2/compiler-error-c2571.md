---
title: Erreur du compilateur C2571 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2571
dev_langs:
- C++
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8bfb4f9af849efea2fa3aa8a84a57f1cfb4cd502
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c2571"></a>Erreur du compilateur C2571
'fonction' : fonction virtuelle ne peut pas figurer dans l’union 'union'  
  
 Une union est déclarée avec une fonction virtuelle. Vous pouvez déclarer une fonction virtuelle uniquement dans une classe ou structure.  Solutions possibles :  
  
1.  Modifiez l’union d’une classe ou une structure.  
  
2.  Rendez la fonction non virtuelle.  
  
 L’exemple suivant génère l’erreur C2571 :  
  
```  
// C2571.cpp  
// compile with: /c  
union A {  
   virtual void func1();   // C2571  
   void func2();   // OK  
};  
```
