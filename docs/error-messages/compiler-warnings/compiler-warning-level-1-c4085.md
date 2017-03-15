---
title: "Avertissement du compilateur (niveau&#160;1) C4085 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4085"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4085"
ms.assetid: 2bc6eb25-058f-4597-b351-fd69587b5170
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Avertissement du compilateur (niveau&#160;1) C4085
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le paramètre pragma attendu doit être 'on' ou 'off'  
  
 Le pragma exige un paramètre **on** ou **off**. Le pragma est ignoré.  
  
 L’exemple suivant génère l’avertissement C4085 :  
  
```  
// C4085.cpp // compile with: /W1 /LD #pragma optimize( "t", maybe )  // C4085  
```