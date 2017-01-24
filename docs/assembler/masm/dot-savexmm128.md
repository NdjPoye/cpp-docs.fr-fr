---
title: ".SAVEXMM128 | Microsoft Docs"
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
  - ".SAVEXMM128"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SAVEXMM128 directive"
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SAVEXMM128
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Génère ou `UWOP_SAVE_XMM128` ou une entrée de code de déroulement d' `UWOP_SAVE_XMM128_FAR` pour le registre XMM spécifié et l'offset utilisation du prologue actuel décalés.  MASM choisira l'encodage le plus efficace.  
  
## Syntaxe  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## Notes  
 .SAVEXMM128 permet aux utilisateurs de ml64.exe pour spécifier comment une fonction de frame se déroule, et uniquement autorisé dans le prologue, qui s'étend de la déclaration de FRAME de [PROC](../../assembler/masm/proc.md) à la directive de [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) .  Ces directives ne génèrent pas de code ; ils génèrent uniquement `.xdata` et `.pdata`.  .SAVEXMM128 doit être précédé de l'instruction qui implémentent réellement les actions devant être déroulé.  Il est conseillé d'encapsuler les directives de déroulement et le code qu'ils sont censées les dérouler dans une macro pour garantir le contrat.  
  
 `offset` doit être un multiple de 16.  
  
 Pour plus d'informations, consultez [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)