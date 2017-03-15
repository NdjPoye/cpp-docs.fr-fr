---
title: "C3421 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3421
dev_langs:
- C++
helpviewer_keywords:
- C3421
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
caps.latest.revision: 3
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: 8f7a25ee2cb8b36c8e56edf4edb2bf152d6bfd9e
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3421"></a>Erreur du compilateur C3421
'type' : vous ne pouvez pas appeler le finaliseur de cette classe, car il est soit inaccessible, soit inexistant  
  
 Un finaliseur est implicitement privé. Il ne peut donc pas être appelé en dehors de son type englobant.  
  
 Pour plus d’informations, consultez [destructeurs et finaliseurs dans Comment : définir et consommer des classes et structs (C + c++ / CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C3421.  
  
```  
// C3421.cpp  
// compile with: /clr  
ref class A {};  
  
ref class B {   
   !B() {}  
  
public:  
   ~B() {}  
};  
  
int main() {  
   A a;  
   a.!A();   // C3421  
  
   B b;  
   b.!B();   // C3421  
}  
```
