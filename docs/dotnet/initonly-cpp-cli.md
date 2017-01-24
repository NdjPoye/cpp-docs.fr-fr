---
title: "initonly (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "initonly_cpp"
  - "initonly"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "attribut initonly [C++]"
ms.assetid: f745d7fa-dc08-46f1-9b97-0977be58a008
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# initonly (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**initonly** est un mot clé contextuel qui indique cette attribution de variable peut se produire que lors de la déclaration ou dans un constructeur statique dans la même classe.  
  
 L'exemple suivant montre comment utiliser `initionly` :  
  
```  
// mcpp_initonly.cpp  
// compile with: /clr /c  
ref struct Y1 {  
   initonly  
   static int staticConst1;  
  
   initonly  
   static int staticConst2 = 0;  
  
   static Y1() {  
      staticConst1 = 0;  
   }  
};  
```  
  
## Voir aussi  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)