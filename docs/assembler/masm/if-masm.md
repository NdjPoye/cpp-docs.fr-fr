---
title: "IF (MASM) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IF directive"
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# IF (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Accorde l'assembly *de ifstatements* si *expression1* est vraie \(une valeur différente de zéro\) ou *des elseifstatements* si *expression1* a la valeur false \(0\) et *expression2* est true.  
  
## Syntaxe  
  
```  
  
   IF expression1  
ifstatements  
[[ELSEIF expression2  
   elseifstatements]]  
[[ELSE  
   elsestatements]]  
ENDIF  
```  
  
## Notes  
 les directives suivantes peuvent être substituées pour [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI**, **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, et **ELSEIFNDEF**.  Éventuellement, assemble *des elsestatements* si l'expression ci\-dessus est false.  notez que les expressions sont évaluées au moment de l'assembly.  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)