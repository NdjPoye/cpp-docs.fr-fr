---
title: Erreur du compilateur C3374 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3374
dev_langs:
- C++
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 16c857cf431462abd2acc21cf7444ec0aad2d075
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3374"></a>Erreur du compilateur C3374
impossible de récupérer l'adresse de 'function' à moins de créer une instance de délégué  
  
 L'adresse d'une fonction a été récupérée dans un autre contexte que la création d'une instance de délégué.  
  
 L'exemple suivant génère l'erreur C3374 :  
  
```  
// C3374.cpp  
// compile with: /clr  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      System::Console::WriteLine("in func1 {0}", i);  
   }  
};  
  
int main() {  
   &A::func1;   // C3374  
  
   // OK  
   A ^ a = gcnew A;  
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Guide pratique pour définir et utiliser des délégués (C++-CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)
