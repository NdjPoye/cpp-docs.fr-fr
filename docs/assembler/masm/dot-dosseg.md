---
title: ".DOSSEG | Microsoft Docs"
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
  - ".DOSSEG"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".DOSSEG directive"
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .DOSSEG
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Classe les segments d'après la convention de segment de commande MS\-DOS : CODEZ d'abord, sur un des segments ensuite pas dans DGROUP, puis segments de DGROUP.  
  
## Syntaxe  
  
```  
  
.DOSSEG  
  
```  
  
## Notes  
 Les segments de DGROUP suivent cette commande : segments pas dans BSS ou PILE, puis segments de BSS, et enfin segments de pile.  Principalement utilisé pour assurer la prise en charge pour CodeView dans les programmes autonomes MASM.  mêmes que [DOSSEG](../../assembler/masm/dosseg.md).  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)