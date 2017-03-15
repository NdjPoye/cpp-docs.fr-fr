---
title: ".PUSHFRAME | Microsoft Docs"
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
  - ".PUSHFRAME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".PUSHFRAME directive"
ms.assetid: 17b123d0-4c6d-4fd2-85eb-798e8ad0a73c
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .PUSHFRAME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

génère une entrée de code de déroulement d' `UWOP_PUSH_MACHFRAME` .  Si `code` facultatif est spécifié, l'entrée de code de déroulement reçoit un modificateur de 1.  Sinon, le modificateur est 0.  
  
## Syntaxe  
  
```  
.PUSHFRAME [code]  
```  
  
## Notes  
 .PUSHFRAME Permet aux utilisateurs de ml64.exe pour spécifier comment une fonction de frame se déroule et n'est autorisée du prologue, qui s'étend de la déclaration de FRAME de [PROC](../../assembler/masm/proc.md) à la directive de [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) .  Ces directives ne génèrent pas de code ; ils génèrent uniquement `.xdata` et `.pdata`.  .PUSHFRAME Doit être précédé de l'instruction qui implémentent réellement les actions devant être déroulé.  Il est conseillé d'encapsuler les directives de déroulement et le code qu'ils sont censées les dérouler dans une macro pour garantir le contrat.  
  
 Pour plus d'informations, consultez [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)