---
title: "Erreur du compilateur C2499 | Microsoft Docs"
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
  - "C2499"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2499"
ms.assetid: b323ff4d-b3c1-4bfd-b052-ae7292d53222
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2499
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'classe' : une classe ne peut pas être sa propre classe de base  
  
 Vous avez tenté de spécifier la classe définie comme classe de base.  
  
 L'exemple suivant génère l'erreur C2499 :  
  
```  
// C2499.cpp  
// compile with: /c  
class CMyClass : public CMyClass {};   // C2499  
class CMyClass{};   // OK  
```