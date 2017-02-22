---
title: "Comment&#160;: utiliser gcnew pour cr&#233;er des types de valeur et utiliser un boxing implicite | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conversion boxing, implicites"
  - "gcnew (mot clé) (C++), créer des types valeur"
  - "types valeur, créer"
ms.assetid: ceb48841-d6bd-47be-a167-57f44c961603
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Comment&#160;: utiliser gcnew pour cr&#233;er des types de valeur et utiliser un boxing implicite
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'utilisation de [gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) sur un type de valeur crée un type de valeur boxed, qui peut ensuite être placé sur le tas du garbage\-collector managé.  
  
## Exemple  
  
```  
// vcmcppv2_explicit_boxing4.cpp  
// compile with: /clr  
public value class V {  
public:  
   int m_i;  
   V(int i) : m_i(i) {}  
};  
  
public ref struct TC {  
   void do_test(V^ v) {  
      if (v != nullptr)  
         ;  
      else  
         ;  
   }  
};  
  
int main() {  
   V^ v = gcnew V(42);  
   TC^ tc = gcnew TC;  
   tc->do_test(v);  
}  
```  
  
## Voir aussi  
 [Boxing](../windows/boxing-cpp-component-extensions.md)