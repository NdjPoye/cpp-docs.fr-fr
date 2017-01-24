---
title: ".ALLOCSTACK | Microsoft Docs"
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
  - ".ALLOCSTACK"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".ALLOCSTACK directive"
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .ALLOCSTACK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Génère **UWOP\_ALLOC\_SMALL** ou **UWOP\_ALLOC\_LARGE** avec la taille spécifiée pour l'offset actif en prologue.  
  
## Syntaxe  
  
```  
.ALLOCSTACK size  
```  
  
## Notes  
 MASM choisit l'encodage le plus efficace pour une taille donnée.  
  
 .ALLOCSTACK Permet aux utilisateurs de ml64.exe pour spécifier comment une fonction de frame se déroule et n'est autorisée du prologue, qui s'étend de la déclaration de FRAME de [COMMENT](../../assembler/masm/proc.md) à la directive de [.ENDPROLOG](../../assembler/masm/dot-endprolog.md) .  Ces directives ne génèrent pas de code ; ils génèrent uniquement `.xdata` et `.pdata`.  .ALLOCSTACK Doit être précédé de l'instruction qui implémentent réellement les actions devant être déroulé.  Il est conseillé d'encapsuler les directives de déroulement et le code qu'ils sont censées les dérouler dans une macro pour garantir le contrat.  
  
 l'opérande d' `size` doit être un multiple de 8.  
  
 Pour plus d'informations, consultez [MASM for x64 \(ml64.exe\)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## Exemples  
 l'exemple suivant montre comment spécifier un déroulement\/gestionnaire d'exceptions :  
  
```  
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console  
text SEGMENT  
PUBLIC Example3  
PUBLIC Example3_UW  
Example3_UW PROC NEAR  
   ; exception/unwind handler body  
  
   ret 0  
  
Example3_UW ENDP  
  
Example3 PROC FRAME : Example3_UW  
  
   sub rsp, 16  
.allocstack 16  
  
.endprolog  
  
   ; function body  
    add rsp, 16  
   ret 0  
  
Example3 ENDP  
text ENDS  
END  
```  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)