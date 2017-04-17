---
title: "Comment&#160;: impl&#233;menter les mots cl&#233;s C# is et as (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "as (mot clé C#) (C++)"
  - "is (mot clé C#) (C++)"
ms.assetid: bc66c0d1-696b-480d-977c-5d9d1ad1ece6
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: impl&#233;menter les mots cl&#233;s C# is et as (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique indique comment implémenter les fonctionnalités des mots clés C\# `is` et `as` en Visual C\+\+.  
  
 Pour plus d’informations, consultez [is](../Topic/is%20\(C%23%20Reference\).md) et [as](../Topic/as%20\(C%23%20Reference\).md).  
  
## Exemple  
  
```  
// CS_is_as.cpp  
// compile with: /clr  
using namespace System;  
  
interface class I {  
public:  
   void F();  
};  
  
ref struct C : public I {  
   virtual void F( void ) { }  
};  
  
template < class T, class U >   
Boolean isinst(U u) {  
   return dynamic_cast< T >(u) != nullptr;  
}  
  
int main() {  
   C ^ c = gcnew C();  
   I ^ i = safe_cast< I ^ >(c);   // is (maps to castclass in IL)  
   I ^ ii = dynamic_cast< I ^ >(c);   // as (maps to isinst in IL)  
  
   // simulate 'as':  
   Object ^ o = "f";  
   if ( isinst< String ^ >(o) )  
      Console::WriteLine("o is a string");  
}  
```  
  
  **o is a string**   
## Voir aussi  
 [Interopérabilité avec d'autres langages .NET](../dotnet/interoperability-with-other-dotnet-languages-cpp-cli.md)