---
title: "EXTERNDEF | Microsoft Docs"
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
  - "EXTERNDEF"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EXTERNDEF directive"
ms.assetid: 95a10de6-c345-4428-a2f2-90f7d411dc86
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# EXTERNDEF
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit une ou plusieurs variables, noms, ou symboles externes appelés *le nom* dont le type est `type`.  
  
## Syntaxe  
  
```  
  
EXTERNDEF [[langtype]] name:type [[, [[langtype]] name:type]]...  
```  
  
## Notes  
 Si *le nom* est défini dans le module, il est traité comme un [PUBLIC](../../assembler/masm/public-masm.md).  Si *le nom* est référencé dans le module, il est traité comme un [EXTERN](../../assembler/masm/extern-masm.md).  si le *nom* n'est pas référencé, il est ignoré.  `type` peut être [ABS](../../assembler/masm/operator-abs.md), qui importe le *nom* comme constante.  Normalement utilisé dans les fichiers Include.  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)