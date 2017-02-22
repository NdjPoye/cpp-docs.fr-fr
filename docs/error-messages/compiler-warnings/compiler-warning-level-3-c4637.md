---
title: "Avertissement du compilateur (niveau&#160;3) C4637 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4637"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4637"
ms.assetid: 5fd347c1-2de9-408f-9136-1bf1ff273622
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Avertissement du compilateur (niveau&#160;3) C4637
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

commentaire de document XML cible : balise \<include\> ignorée.  raison  
  
 La syntaxe d’une balise [\<include\>](../../ide/include-visual-cpp.md) n’est pas correcte.  
  
 L’exemple suivant génère l’avertissement C4637 :  
  
```  
// C4637.cpp // compile with: /clr /doc /LD /W3 using namespace System; /// Text for class MyClass. public ref class MyClass { public: /// <include file="c:\davedata\jtest\xml_include.doc"/> // Try the following line instead: // /// <include file='xml_include.doc' path='MyDocs/MyMembers/*' /> void MyMethod() { } };   // C4637  
```