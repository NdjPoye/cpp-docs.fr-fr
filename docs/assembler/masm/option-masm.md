---
title: "OPTION (MASM) | Microsoft Docs"
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
  - "option"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OPTION directive"
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# OPTION (MASM)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vérifie et des fonctionnalités de désactive de l'assembly.  
  
## Syntaxe  
  
```  
  
OPTION   
optionlist  
  
```  
  
## Notes  
 Les options disponibles incluent :  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**ÉMULATEUR**|  
|**NOEMULATOR**|**ÉPILOGUE**|**EXPR16**|**EXPR32**|  
|**LANGAGE**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**OFFSET**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**COMMENT**|**PROLOGUE**|**READONLY**|**NOREADONLY**|  
|**SCOPED**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|  
  
 La syntaxe pour le LANGAGE est **LANGAGE D'OPTION :***X*, où *x* est un C, de SYSCALL, de STDCALL, de PASCAL, FORTRAN, ou de BASIC.  SYSCALL, PASCAL, FORTRAN, et BASIC ne sont pas pris en charge avec utilisé avec l'APPARTEMENT de [.MODEL](../../assembler/masm/dot-model.md) .  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)