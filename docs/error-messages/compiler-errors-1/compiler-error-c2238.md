---
title: "Erreur du compilateur C2238 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2238"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2238"
ms.assetid: 3d53060c-d6b7-4603-b9cf-d7c65eb64cd2
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2238
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

jetons inattendus avant 'token'  
  
 Un jeton incorrect a été détecté.  
  
 L’exemple suivant génère l’erreur C2238 :  
  
```  
// C2238.cpp // compile with: /c class v { virtual: int vvv;   // C2238 };  
```