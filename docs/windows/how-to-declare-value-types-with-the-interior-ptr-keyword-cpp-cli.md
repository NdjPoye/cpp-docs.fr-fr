---
title: "How to: Declare Value Types with the interior_ptr Keyword (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ptr keyword"
  - "value types, declaring"
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Declare Value Types with the interior_ptr Keyword (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un `interior_ptr` peut être utilisé avec un type de valeur.  
  
> [!IMPORTANT]
>  Cette fonctionnalité des langues est prise en charge par l'option du compilateur **\/clr**, mais pas par l'option du compilateur **\/ZW**.  
  
## Exemple  
  
### Description  
 L'exemple suivant [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)] montre comment utiliser `interior_ptr` avec un type de valeur.  
  
### Code  
  
```  
// interior_ptr_value_types.cpp  
// compile with: /clr  
value struct V {  
   V(int i) : data(i){}  
   int data;  
};  
  
int main() {  
   V v(1);  
   System::Console::WriteLine(v.data);  
  
   // pointing to a value type  
   interior_ptr<V> pv = &v;  
   pv->data = 2;  
  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
  
   // pointing into a value type  
   interior_ptr<int> pi = &v.data;  
   *pi = 3;  
   System::Console::WriteLine(*pi);  
   System::Console::WriteLine(v.data);  
   System::Console::WriteLine(pv->data);  
}  
```  
  
### Sortie  
  
```  
1  
2  
2  
3  
3  
3  
```  
  
## Exemple  
  
### Description  
 Dans un type de valeur, le pointeur `this` correspond à un interior\_ptr.  
  
 Le corps d'une fonction membre statique d'un type de valeur `V`, `this` est une expression de type `interior_ptr<V>` dont la valeur correspond à l'adresse de l'objet pour lequel la fonction est appelée.  
  
### Code  
  
```  
// interior_ptr_value_types_this.cpp  
// compile with: /clr /LD  
value struct V {  
   int data;  
   void f() {  
      interior_ptr<V> pv1 = this;  
      // V* pv2 = this;   error  
   }  
};  
```  
  
## Exemple  
  
### Description  
 L'exemple suivant montre comment utiliser l'opérateur d'adresse à des membres statiques.  
  
 L'adresse d'un membre de type Visual C\+\+ statiques génère un pointeur natif.  L'adresse d'un membre statique de type de valeur pointeur managé car le membre de type valeur est alloué sur le segment d'exécution et peut être déplacé par le garbage collector.  
  
### Code  
  
```  
// interior_ptr_value_static.cpp  
// compile with: /clr  
using namespace System;  
value struct V { int i; };  
  
ref struct G {  
   static V v = {22};   
   static int i = 23;   
   static String^ pS = "hello";   
};  
  
int main() {  
   interior_ptr<int> p1 = &G::v.i;  
   Console::WriteLine(*p1);  
  
   interior_ptr<int> p2 = &G::i;  
   Console::WriteLine(*p2);  
  
   interior_ptr<String^> p3 = &G::pS;  
   Console::WriteLine(*p3);  
}  
```  
  
### Sortie  
  
```  
22  
23  
hello  
```  
  
## Voir aussi  
 [interior\_ptr \(C\+\+\/CLI\)](../windows/interior-ptr-cpp-cli.md)