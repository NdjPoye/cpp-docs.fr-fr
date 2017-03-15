---
title: "ML Nonfatal Error A2006 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2006"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2006"
ms.assetid: b8a8f096-95df-42b5-85ed-d2530560a84c
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2006
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**symbole non défini : identificateur**  
  
 Une tentative a été faite pour utiliser un symbole non défini.  
  
 L'une des opérations suivantes a pu se produire :  
  
-   un symbole n'a pas été défini.  
  
-   Un champ n'est pas un membre de la structure spécifiée.  
  
-   Un symbole a été défini dans un fichier Include qui n'a pas été inclus.  
  
-   Un symbole externe est utilisé sans directive d' [EXTERN](../../assembler/masm/extern-masm.md) ou d' [EXTERNDEF](../../assembler/masm/externdef.md) .  
  
-   Un nom de symbole a été mal orthographié.  
  
-   Un nom de code local a été référencé en dehors de sa portée.  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)