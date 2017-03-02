---
title: Avertissement du compilateur C4867 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4867
dev_langs:
- C++
helpviewer_keywords:
- C4867
ms.assetid: 8a257d70-c3a7-462d-b285-e57c952a8bf7
caps.latest.revision: 16
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 84964b0a49b236bae056125de8155b18880eb378
ms.openlocfilehash: 86437fca7bfeef662bef9fe8311fb746a661264d
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-c4867"></a>Avertissement du compilateur C4867
'fonction' : appel de fonction pas de liste d’arguments ; Utilisez 'appel' pour créer un pointeur vers membre  
  
 Un pointeur vers une fonction membre a été correctement initialisé.  
  
 Cet avertissement peut être due à la mise en conformité du compilateur pour Visual C++ 2005 : conformité pointeur vers membre améliorée.  Le code compilé avant Visual C++ 2005 génère désormais C4867.  
  
 Cet avertissement est toujours émis en tant qu’erreur. Utilisez le [avertissement](../../preprocessor/warning.md) pragma pour désactiver cet avertissement. Pour plus d’informations sur l’erreur C4867 et MFC/ATL, consultez [_ATL_ENABLE_PTM_WARNING](http://msdn.microsoft.com/Library/00b9ff5c-9834-4c40-911e-ee88d512c4af).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur C4867.  
  
```  
// C4867.cpp  
// compile with: /c  
class A {  
public:  
   void f(int) {}  
  
   typedef void (A::*TAmtd)(int);  
  
   struct B {  
      TAmtd p;  
   };  
  
   void g() {  
      B b = {f};   // C4867  
      B b2 = {&A::f};   // OK  
   }  
};  
```
