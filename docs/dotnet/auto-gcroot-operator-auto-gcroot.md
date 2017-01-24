---
title: "auto_gcroot::operator auto_gcroot | Microsoft Docs"
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
  - "auto_gcroot.operator auto_gcroot"
  - "auto_gcroot::operator auto_gcroot"
  - "msclr.auto_gcroot.operator auto_gcroot"
  - "msclr::auto_gcroot::operator auto_gcroot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_gcroot (opérateur)"
ms.assetid: 43e3f27a-9f68-444f-9149-a9282a9b935a
caps.latest.revision: 12
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# auto_gcroot::operator auto_gcroot
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Opérateur de conversion de type entre `auto_gcroot` et les types compatibles.  
  
## Syntaxe  
  
```  
template<typename _other_type>  
operator auto_gcroot<_other_type>();  
```  
  
## Valeur de retour  
 Le `auto_gcroot` actuel converti en `auto_gcroot<_other_type>`.  
  
## Exemple  
  
```  
// msl_auto_gcroot_op_auto_gcroot.cpp  
// compile with: /clr  
#include <msclr\auto_gcroot.h>  
  
using namespace System;  
using namespace msclr;  
  
ref class ClassA {  
protected:     
   String^ m_s;  
public:  
   ClassA( String^ s ) : m_s( s ) {}  
  
   virtual void PrintHello() {  
      Console::WriteLine( "Hello from {0} A!", m_s );  
   }  
};  
  
ref class ClassB : ClassA {  
public:  
   ClassB( String ^ s) : ClassA( s ) {}  
   virtual void PrintHello() new {  
      Console::WriteLine( "Hello from {0} B!", m_s );  
   }  
};  
  
int main() {  
   auto_gcroot<ClassB^> b = gcnew ClassB("first");  
   b->PrintHello();  
   auto_gcroot<ClassA^> a = (auto_gcroot<ClassA^>)b;  
   a->PrintHello();  
}  
```  
  
  **Bonjour du premier B\!**  
**Bonjour du premier A\!**   
## Configuration requise  
 **Fichier d'en\-tête** \<msclr\\auto\_gcroot.h\>  
  
 **Espace de noms** msclr  
  
## Voir aussi  
 [auto\_gcroot, membres](../dotnet/auto-gcroot-members.md)