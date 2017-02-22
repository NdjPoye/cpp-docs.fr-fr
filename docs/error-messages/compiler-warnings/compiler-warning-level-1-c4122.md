---
title: "Avertissement du compilateur (niveau&#160;1) C4122 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4122"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4122"
ms.assetid: 9a83eb0d-8708-42f7-988a-b0b6f2f646a0
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau&#160;1) C4122
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'function' : alloc\_text ne peut s’appliquer qu’aux fonctions avec liaison C  
  
 Le pragma **alloc\_text** s’applique uniquement aux fonctions déclarées avec **extern c**. Il ne peut pas être utilisé avec des fonctions C\+\+ externes.  
  
 Le pragma est ignoré.