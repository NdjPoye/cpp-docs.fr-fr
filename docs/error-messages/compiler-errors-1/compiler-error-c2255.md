---
title: "Erreur du compilateur C2255 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2255"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2255"
ms.assetid: 67dc4cb0-de6b-4405-bd64-d47736367a93
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2255
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'element' : non autorisé en dehors d’une définition de classe  
  
 Par exemple, une fonction non\-membre est déclarée comme étant un `friend`.  
  
 L’exemple suivant génère l’erreur C2255 :  
  
```  
// C2255.cpp // compile with: /c class A { private: void func1(); friend void func2(); }; friend void func1() {}   // C2255 void func2(){}  
```