---
title: Erreur du compilateur C2296 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2296
dev_langs:
- C++
helpviewer_keywords:
- C2296
ms.assetid: 47d270f4-13ce-4c16-81e2-7d67c6c4a540
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c154073e0ea64527e444a7c46d13ba14ce05d63c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2296"></a>Erreur du compilateur C2296
'opérateur' : opérande gauche incorrect  
  
 L’opérande gauche utilisé avec `operator` n’est pas valide.  
  
 Par exemple, le compilateur peut afficher une déclaration endroit prévu pour un appel de fonction.  
  
 L’exemple suivant génère C2296 :  
  
```  
// C2296.cpp  
struct MyStruct {  
   struct Help {  
      Help(float f) : m_f(f) {}  
      float m_f;  
   };  
  
   MyStruct(const Help &h) : m_f(h.m_f) {}  
   MyStruct(float f) : m_f(f) {}  
   MyStruct operator*(const MyStruct &f1) const {   
      return MyStruct(m_f * f1.m_f);  
   }  
  
private:  
   float m_f;  
};  
  
int main() {  
   float f1 = 1.0f;  
  
   MyStruct m_MyStruct1 ( MyStruct::Help( f1 ) );  
   // try the following line instead  
   // MyStruct m_MyStruct1 = MyStruct::Help( f1 );  
  
   MyStruct m_MyStruct2 ( MyStruct::Help( f1 ) );  
   // try the following line instead  
   // MyStruct m_MyStruct2 = MyStruct::Help( f1 );  
  
   MyStruct m_MyStruct3 = m_MyStruct1 * m_MyStruct2;   // C2296  
}  
```