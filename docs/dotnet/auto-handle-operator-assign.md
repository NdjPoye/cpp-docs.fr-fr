---
title: "auto_handle::operator= | Microsoft Docs"
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
  - "auto_handle::operator="
  - "msclr.auto_handle.operator="
  - "msclr::auto_handle::operator="
  - "auto_handle.operator="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_handle::operator="
ms.assetid: 503ca172-e766-4a78-af98-36fd48c931ee
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_handle::operator=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Opérateur d'assignation  
  
## Syntaxe  
  
```  
auto_handle<_element_type> % operator=(  
   auto_handle<_element_type> % _right  
);  
template<typename _other_type>  
auto_handle<_element_type> % operator=(  
   auto_handle<_other_type> % _right  
);  
```  
  
#### Paramètres  
 `_right`  
 Le `auto_handle` à affecter au `auto_handle`actuel.  
  
## Valeur de retour  
 L'actuel `auto_handle`, détenant maintenant `_right`.  
  
## Exemple  
  
```  
// msl_auto_handle_op_assign.cpp  
// compile with: /clr  
#include <msclr\auto_handle.h>  
  
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
   auto_handle<ClassA> a;  
   auto_handle<ClassA> a2(gcnew ClassA( "first" ) );  
   a = a2; // assign from same type  
   a->PrintHello();  
  
   auto_handle<ClassB> b(gcnew ClassB( "second" ) );     
   b->PrintHello();  
   a = b; // assign from derived type     
   a->PrintHello();  
  
   Console::WriteLine("done");  
}  
```  
  
  **dans le constructeur de ClassA: premier**  
**Bonjour du premier A\!**  
**Dans le constructeur de ClassA : deuxième**  
**Bonjour du deuxième B\!**  
**Dans le destructeur de ClassA : premier**  
**Bonjour du deuxième A\!**  
**done**  
**Dans destructeur de ClassA : deuxième**   
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\auto\_handle.h\>  
  
 **Espace de noms** msclr  
  
## Voir aussi  
 [auto\_handle, membres](../dotnet/auto-handle-members.md)