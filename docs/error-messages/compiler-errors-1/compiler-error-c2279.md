---
title: "Erreur du compilateur C2279 | Microsoft Docs"
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
  - "C2279"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2279"
ms.assetid: 1b5c88ef-2336-49b8-9ddb-d61f97c73e14
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2279
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

la spécification de l'exception ne peut pas s'afficher dans une déclaration typedef  
  
 Sous **\/Za**, les [spécifications d'exceptions](../../cpp/exception-specifications-throw-cpp.md) ne sont pas autorisées dans une déclaration typedef.  
  
 L'exemple suivant génère l'erreur C2279 :  
  
```  
// C2279.cpp  
// compile with: /Za /c  
typedef int (*xy)() throw(...);   // C2279  
typedef int (*xyz)();   // OK  
```