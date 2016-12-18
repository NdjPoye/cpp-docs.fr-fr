---
title: "Erreur du compilateur C2819 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2819"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2819"
ms.assetid: fcc7762d-cb82-4bb1-a715-0d82da832edf
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2819
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le type 'type' n'a pas de membre surchargé 'opérateur \-\>'  
  
 Vous devez définir `operator->()` pour utiliser cette opération de pointeur.  
  
 L'exemple suivant génère l'erreur C2819 :  
  
```  
// C2819.cpp  
// compile with: /c  
class A {  
   public:  
      int i;  
};  
  
class B {};  
  
void C(B j) {  
   j->i;   // C2819  
}  
  
class D {  
   A* pA;  
  
   public:  
      A* operator->() {  
         return pA;  
      }  
};  
  
void F(D j) {  
   j->i;  
}  
```  
  
 L'erreur C2819 peut également se produire lors de l'utilisation de [Sémantique de pile C\+\+ pour les types de référence](../../dotnet/cpp-stack-semantics-for-reference-types.md).  L'exemple suivant génère l'erreur C2819 :  
  
```  
// C2819_b.cpp  
// compile with: /clr  
ref struct R {  
   void Test() {}  
};  
  
int main() {  
   R r;  
   r->Test();   // C2819  
   r.Test();   // OK  
}  
```