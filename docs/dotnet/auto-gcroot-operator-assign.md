---
title: "auto_gcroot::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_gcroot.operator="
  - "msclr::auto_gcroot::operator="
  - "msclr.auto_gcroot.operator="
  - "auto_gcroot::operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "= (opérateur)"
ms.assetid: 99eba5eb-5a2c-4edf-b3d5-c903f818233d
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot::operator=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Opérateur d'assignation  
  
## Syntaxe  
  
```  
auto_gcroot<_element_type> & operator=(  
   _element_type _right  
);  
auto_gcroot<_element_type> & operator=(  
   auto_gcroot<_element_type> & _right  
);  
template<typename _other_type>  
auto_gcroot<_element_type> & operator=(  
   auto_gcroot<_other_type> & _right  
);  
```  
  
#### Paramètres  
 `_right`  
 L'objet ou `auto_gcroot` à affecter à `auto_gcroot`actuel.  
  
## Valeur de retour  
 L'actuel `auto_gcroot`, détenant maintenant `_right`.  
  
## Exemple  
  
```  
// msl_auto_gcroot_operator_equals.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:  
   String^ m_s;     
public:  
   ClassA(String^ s) : m_s(s) {  
      Console::WriteLine( "in ClassA constructor: " + m_s );  
   }  
   ~ClassA() {  
      Console::WriteLine( "in ClassA destructor: " + m_s );  
   }  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class ClassB : ClassA {  
public:     
   ClassB( String^ s ) : ClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
int main()  
{  
   auto_gcroot<ClassA^> a;  
   auto_gcroot<ClassA^> a2(gcnew ClassA( "first" ) );  
   a = a2; // assign from same type  
   a->PrintHello();  
  
   ClassA^ ha = gcnew ClassA( "second" );  
   a = ha; // assign from raw handle  
  
   auto_gcroot<ClassB^> b(gcnew ClassB( "third" ) );     
   b->PrintHello();  
   a = b; // assign from derived type     
   a->PrintHello();  
  
   Console::WriteLine("done");  
}  
```  
  
  **dans le constructeur de ClassA: premier**  
**Bonjour du premier A\!**  
**Dans le constructeur de ClassA : deuxième**  
**Dans le destructeur de ClassA : premier**  
**Dans le constructeur de ClassA : troisième**  
**Bonjour de troisième B \!**  
**Dans destructeur de ClassA : deuxième**  
**Bonjour de troisième A \!**  
**done**  
**Dans le destructeur de ClassA : troisième**   
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\auto\_gcroot.h\>  
  
 **Espace de noms** msclr  
  
## Voir aussi  
 [auto\_gcroot, membres](../dotnet/auto-gcroot-members.md)   
 [auto\_gcroot::attach](../dotnet/auto-gcroot-attach.md)