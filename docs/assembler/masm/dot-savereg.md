---
title: ".SAVEREG | Microsoft Docs"
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
  - ".SAVEREG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".SAVEREG directive"
ms.assetid: 1dbc2ef6-a197-40e7-9e55-fddcae8cef29
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .SAVEREG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Génère `UWOP_SAVE_NONVOL` ou une entrée de code de déroulement d' `UWOP_SAVE_NONVOL_FAR` pour le registre spécifié \(`reg`\) et l'offset \(`offset`\) à l'aide de l'offset actuel du prologue.  MASM choisira l'encodage le plus efficace.  
  
## Syntaxe  
  
```  
.SAVEREG reg, offset  
```  
  
## Notes  
 .SAVEREG Permet aux utilisateurs de ml64.exe pour spécifier comment une fonction de frame se déroule et n'est autorisée du prologue, qui s'étend de la déclaration de FRAME de [PROC](../../assembler/masm/proc.md) à la directive de [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) .  Ces directives ne génèrent pas de code ; ils génèrent uniquement `.xdata` et `.pdata`.  .SAVEREG Doit être précédé de l'instruction qui implémentent réellement les actions devant être déroulé.  Il est conseillé d'encapsuler les directives de déroulement et le code qu'ils sont censées les dérouler dans une macro pour garantir le contrat.  
  
 Pour plus d'informations, consultez [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)