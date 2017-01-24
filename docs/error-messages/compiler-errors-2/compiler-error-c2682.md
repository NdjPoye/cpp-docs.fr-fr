---
title: "Erreur du compilateur C2682 | Microsoft Docs"
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
  - "C2682"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2682"
ms.assetid: 30c6a7c4-f5f7-4fe8-81a8-c48938521ab4
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2682
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'utiliser 'opérateur\_casting' pour convertir 'type1' en 'type2'  
  
 Un opérateur de casting a essayé d'effectuer une conversion entre deux types incompatibles.  Vous ne pouvez pas, par exemple, utiliser l'opérateur [dynamic\_cast](../../cpp/dynamic-cast-operator.md) pour convertir un pointeur en une référence.  L'opérateur `dynamic_cast` ne peut pas être utilisé pour modifier le cast des qualificateurs.  Tous les qualificateurs des types doivent concorder.  
  
 Vous pouvez utiliser l'opérateur `const_cast` pour supprimer des attributs tels que `const`, `volatile` ou `__unaligned`.  
  
 L'exemple suivant génère l'erreur C2682 :  
  
```  
// C2682.cpp  
class A { virtual void f(); };  
class B: public A {};  
  
void g(A* pa) {  
    B& rb = dynamic_cast<B&>(pa); // C2682  
}  
```  
  
 L'exemple suivant génère l'erreur C2682 :  
  
```  
// C2682b.cpp  
// compile with: /clr  
ref struct R{};  
ref struct RR : public R{};  
ref struct H {  
   RR^ r ;  
   short s;  
   int i;  
};  
  
int main() {  
   H^ h = gcnew H();    
   interior_ptr<int>lr = &(h->i);  
   interior_ptr<short>ssr = safe_cast<interior_ptr<short> >(lr);   // C2682  
   interior_ptr<short>ssr = reinterpret_cast<interior_ptr<short> >(lr);   // OK  
}  
```