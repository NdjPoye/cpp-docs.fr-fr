---
title: "DD | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "dd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DD directive"
ms.assetid: 0c238628-2fe2-437e-979d-a90bdae7b478
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# DD
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

alloue et initialise éventuellement un double mot \(4 octets\) du stockage pour chaque `initializer`.  `DD` est un synonyme de [valeur DWORD](../../assembler/masm/dword.md).  
  
## Syntaxe  
  
```  
[[name]] DD initializer [[, initializer]]...  
```  
  
## Notes  
 Peut également être utilisé comme un spécificateur de type partout où un type est conforme.  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)