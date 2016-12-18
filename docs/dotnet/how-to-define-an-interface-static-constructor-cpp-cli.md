---
title: "Comment&#160;: d&#233;finir un constructeur d&#39;interface statique (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "constructeurs [C++]"
  - "constructeur d'interface statique"
  - "constructeurs statiques, interface"
ms.assetid: 1f031cb2-e94f-43dc-819b-44cf2faaaa49
caps.latest.revision: 10
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: d&#233;finir un constructeur d&#39;interface statique (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une interface peut avoir un constructeur statique, qui peut être utilisé pour initialiser des membres de données statiques.  Un constructeur statique est appelé au plus une fois, puis sera appelé avant la première fois qu'on accède à un membre statique d'interface.  
  
 Pour plus d'informations sur les constructeurs classiques, consultez [Comment : définir des constructeur statiques dans une classe ou un struct](../misc/how-to-define-static-constructors-in-a-class-or-struct.md).  
  
## Exemple  
  
```  
// mcppv2_interface_class2.cpp  
// compile with: /clr  
using namespace System;  
  
interface struct MyInterface {  
   static int i;  
   static void Test() {  
      Console::WriteLine(i);  
   }  
  
   static MyInterface() {   
      Console::WriteLine("in MyInterface static constructor");  
      i = 99;  
   }  
};  
  
ref class MyClass : public MyInterface {};  
  
int main() {  
   MyInterface::Test();  
   MyClass::MyInterface::Test();  
  
   MyInterface ^ mi = gcnew MyClass;  
   mi->Test();  
}  
```  
  
  **dans le constructeur statique MyInterface**  
**99**  
**99**  
**99**   
## Voir aussi  
 [interface class](../windows/interface-class-cpp-component-extensions.md)