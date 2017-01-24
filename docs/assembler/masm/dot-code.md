---
title: ".CODE | Microsoft Docs"
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
  - ".CODE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - ".CODE directive"
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# .CODE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

En cas de utilisation avec [.MODEL](../../assembler/masm/dot-model.md), indique le début d'un segment de code.  
  
## Syntaxe  
  
```  
.CODE [[name]]  
```  
  
#### Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`name`|paramètre optionnel qui spécifie le nom du segment de code.  le nom par défaut est \_TEXT pour [modèles](../../assembler/masm/dot-model.md)minuscule, petit, compact, et en deux dimensions.  le nom par défaut est \_TEXT de *modulename*pour d'autres modèles.|  
  
## Voir aussi  
 [Directives Reference](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)