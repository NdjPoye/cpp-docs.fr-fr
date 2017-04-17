---
title: "C3367 d’erreur du compilateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C3367
dev_langs:
- C++
helpviewer_keywords:
- C3367
ms.assetid: e675d42b-f5b0-4d43-aab1-1f5024233102
caps.latest.revision: 7
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
ms.sourcegitcommit: 65e7a7bd56096fbeec61b651ab494d82edef9c90
ms.openlocfilehash: 8c7d1df695aa54e350902929ee8ea57be2101058
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c3367"></a>Erreur du compilateur C3367
'fonction_membre_statique' : impossible d’utiliser une fonction static pour créer un délégué indépendant  
  
Quand vous appelez un délégué indépendant, vous devez passer une instance d’un objet. Dans la mesure où une fonction membre statique est appelée par le nom de classe, vous ne pouvez instancier un délégué indépendant qu’avec une fonction membre d’instance.  
  
Pour plus d’informations sur les délégués indépendants, consultez [Comment : définir et utiliser délègue (C + c++ / CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md).  
  
## <a name="example"></a>Exemple  
L’exemple suivant génère l’erreur C3367.  
  
```cpp  
// C3367.cpp  
// compile with: /clr  
ref struct R {  
   void b() {}  
   static void f() {}  
};  
  
delegate void Del(R^);  
  
int main() {  
   Del ^ a = gcnew Del(&R::b);   // OK  
   Del ^ b = gcnew Del(&R::f);   // C3367  
}  
```