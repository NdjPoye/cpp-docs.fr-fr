---
title: Erreur du compilateur C3634 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3634
dev_langs:
- C++
helpviewer_keywords:
- C3634
ms.assetid: fd09f10c-f863-483b-9756-71c16b760b02
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 0ab2285ef47f704defbcca8644dbf63b8507096a
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3634"></a>Erreur du compilateur C3634
'fonction' : Impossible de définir une méthode abstraite de géré ou WinRTclass  
  
 Une méthode abstraite peut être déclarée dans une classe managée ou WinRT, mais elle ne peut pas être définie.  
  
## <a name="example"></a>Exemple  
L'exemple suivant génère l'erreur C3634 :  
  
```  
// C3634.cpp  
// compile with: /clr  
ref class C {  
   virtual void f() = 0;  
};  
  
void C::f() {   // C3634 - don't define managed class' pure virtual method  
}  
```  

