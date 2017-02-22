---
title: "R&#233;f&#233;rences de segment dans un assembly inline | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "assembleur inline, registres"
  - "assembleur inline, références de segment"
  - "références, assembleur inline"
  - "registres"
  - "registres, assembleur inline"
  - "références de segment dans l'assembleur inline"
ms.assetid: c63e6bb4-49d9-4fa1-bb22-eea21b5cbc0f
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# R&#233;f&#233;rences de segment dans un assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Vous devez faire référence aux segments par registre plutôt que par nom \(le nom de segment `_TEXT` n'est pas valide, par exemple\).  Les substitutions de segments doivent utiliser le registre explicitement, comme dans ES:\[BX\].  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Utilisation du langage assembleur dans les blocs \_\_asm](../../assembler/inline/using-assembly-language-in-asm-blocks.md)