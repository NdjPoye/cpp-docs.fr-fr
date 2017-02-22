---
title: "Erreur du compilateur C2337 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C2337"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2337"
ms.assetid: eccc9178-a15e-42cd-bbd0-3cea7cf2d55b
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C2337
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute name' : attribut introuvable  
  
 Vous avez utilisé un attribut qui n’est pas pris en charge dans cette version de Visual C\+\+.  
  
 L’exemple suivant génère l’erreur C2337 :  
  
```  
// C2337.cpp // compile with: /c [emitidl]; [module(name="x")]; [grasshopper]   // C2337, not a supported attribute class a{};  
```