---
title: "Erreur du compilateur C3612 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3612"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3612"
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3612
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : une classe sealed ne peut pas être abstraite  
  
 Les types définis avec `value` \(ou [\_\_value](../../misc/value.md)\) sont sealed par défaut et une classe est abstraite sauf si elle implémente toutes les méthodes de sa base.  Une classe sealed abstraite ne peut ni être une classe de base ni être instanciée.  
  
 Pour plus d'informations, consultez [Classes and Structs](../../windows/classes-and-structs-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3612 :  
  
```  
// C3612.cpp  
// compile with: /clr /c  
value struct V: public System::ICloneable {};   // C3612  
  
// OK  
value struct V2: public System::ICloneable {  
   Object^ Clone();  
};  
```