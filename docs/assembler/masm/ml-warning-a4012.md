---
title: "ML Warning A4012 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A4012"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A4012"
ms.assetid: 842b1259-9679-4eeb-a02d-672a583a94e5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Warning A4012
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**les informations de numéro de ligne pour le segment sans CODE des classes »**  
  
 Il existait instruction dans un segment qui n'avait pas d'un nom de classe qui se termine par « CODE ». L'assembly n'a pas généré les informations CodeView pour cette instruction.  
  
 CodeView ne peut pas fonctionner sur des modules avec le code dans les segments avec les noms de classe qui ne se termine pas par « CODE ».  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)