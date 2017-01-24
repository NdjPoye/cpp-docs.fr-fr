---
title: "Erreur du compilateur C2351 | Microsoft Docs"
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
  - "C2351"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2351"
ms.assetid: 5439ccf6-66f6-4859-964c-c73f5eddfc1b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2351
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

syntaxe obsolète d'initialisation d'un constructeur C\+\+  
  
 Dans une liste d'initialisation d'un nouveau style pour un constructeur, vous devez nommer explicitement chaque classe de base directe, même s'il s'agit de la seule classe de base.  
  
 L'exemple suivant génère l'erreur C2351 :  
  
```  
// C2351.cpp  
// compile with: /c  
class B {  
public:   
   B() : () {}   // C2351  
   B() {}   // OK  
};  
```