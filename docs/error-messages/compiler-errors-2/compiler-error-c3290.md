---
title: Erreur du compilateur C3290 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3290
dev_langs:
- C++
helpviewer_keywords:
- C3290
ms.assetid: 0baf684b-1143-4953-ac99-a2fa267d8017
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: c3dceac5102936bbb86f5c103fb0c9240f5ee2d2
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3290"></a>Erreur du compilateur C3290
'type' : une propriété triviale ne peut pas avoir de type référence  
  
 Une propriété n’a pas été correctement déclarée. Quand vous déclarez une propriété triviale, le compilateur crée une variable que la propriété va mettre à jour et il n’est pas possible d’avoir une variable de référence de suivi dans une classe.  
  
 Consultez [propriété](../../windows/property-cpp-component-extensions.md) et [opérateur de référence de suivi](../../windows/tracking-reference-operator-cpp-component-extensions.md) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3290.  
  
```  
// C3290.cpp  
// compile with: /clr /c  
ref struct R {};  
  
ref struct X {  
   R^ mr;  
  
   property R % y;   // C3290  
   property R ^ x;   // OK  
  
   // OK  
   property R% prop {  
      R% get() {   
         return *mr;   
      }  
  
      void set(R%) {}  
   }  
};  
  
int main() {  
   X x;  
   R% xp = x.prop;  
}  
```
