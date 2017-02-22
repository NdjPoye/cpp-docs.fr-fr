---
title: "auto_handle::auto_handle | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "auto_handle::auto_handle"
  - "msclr.auto_handle.auto_handle"
  - "auto_handle.auto_handle"
  - "msclr::auto_handle::auto_handle"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle (méthode)"
ms.assetid: 0b68ab31-023c-4224-9601-9231412c4e13
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# auto_handle::auto_handle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Constructeur `auto_handle`.  
  
## Syntaxe  
  
```  
auto_handle();  
auto_handle(  
   _element_type ^ _ptr  
);  
auto_handle(  
   auto_handle<_element_type> % _right  
);  
template<typename _other_type>  
auto_handle(  
   auto_handle<_other_type> % _right  
);  
```  
  
#### Paramètres  
 `_ptr`  
 Objet à posséder.  
  
 `_right`  
 `auto_handle` existant.  
  
## Exemple  
  
```  
// msl_auto_handle_auto_handle.cpp  
// compile with: /clr  
#include "msclr\auto_handle.h"  
  
using namespace System;  
using namespace msclr;  
ref class RefClassA {  
protected:  
   String^ m_s;     
public:  
   RefClassA(String^ s) : m_s(s) {  
      Console::WriteLine( "in RefClassA constructor: " + m_s );  
   }  
   ~RefClassA() {  
      Console::WriteLine( "in RefClassA destructor: " + m_s );  
   }  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class RefClassB : RefClassA {  
public:     
   RefClassB( String^ s ) : RefClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
int main()  
{  
   {  
      auto_handle<RefClassA> a(gcnew RefClassA( "first" ) );  
      a->PrintHello();  
   }  
  
   {  
      auto_handle<RefClassB> b(gcnew RefClassB( "second" ) );  
      b->PrintHello();  
      auto_handle<RefClassA> a(b); //construct from derived type  
      a->PrintHello();  
      auto_handle<RefClassA> a2(a); //construct from same type  
      a2->PrintHello();  
   }  
  
   Console::WriteLine("done");  
}  
```  
  
  **dans le constructeur de RefClassA : premier**  
**Bonjour du premier A\!**  
**dans le destructeur de RefClassA : premier**  
**dans le constructeur de RefClassA : deuxième**  
**Bonjour du deuxième B \!**  
**Bonjour du deuxième A \!**  
**Bonjour du deuxième A \!**  
**dans le destructeur de RefClassA : deuxième**  
**done**   
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\auto\_handle.h\>  
  
 **Espace de noms** msclr  
  
## Voir aussi  
 [auto\_handle, membres](../dotnet/auto-handle-members.md)   
 [auto\_handle::operator\=](../dotnet/auto-handle-operator-assign.md)   
 [auto\_handle::~auto\_handle](../dotnet/auto-handle-tilde-auto-handle.md)