---
title: Erreur du compilateur C3185 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3185
dev_langs:
- C++
helpviewer_keywords:
- C3185
ms.assetid: 5bf96279-043c-4981-9d02-b4550071b192
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 10b25fa08693e4fc6c4e495c84944d79ab6e73ae
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3185"></a>Erreur du compilateur C3185
'typeid' : utilisé avec le type managé ou WinRT 'type' ; utilisez 'opérateur' à la place  
  
 Vous ne pouvez pas appliquer le [typeid](../../cpp/typeid-operator.md) opérateur managé ou WinRT type ; utilisez [typeid](../../windows/typeid-cpp-component-extensions.md) à la place.  
  
 L'exemple suivant génère l'erreur C3185 et montre comment la corriger :  
  
```  
// C3185a.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
  
int main() {  
   Derived ^ pd = gcnew Derived;  
   Base ^pb = pd;  
   const type_info & t1 = typeid(pb);   // C3185  
   System::Type ^ MyType = Base::typeid;   // OK  
};  
```  

