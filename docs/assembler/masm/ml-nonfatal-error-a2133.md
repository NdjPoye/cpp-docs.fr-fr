---
title: "ML Nonfatal Error A2133 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2133"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2133"
ms.assetid: 5ba50911-22c8-43b7-90e2-946fc612e05f
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2133
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**valeur de registre remplacée par INVOKE**  
  
 Un registre a été passé comme argument à une procédure, mais le code généré par [APPELEZ](../../assembler/masm/invoke.md) pour passer d'autres arguments est détruit le contenu du registre.  
  
 La HACHE, la génération, des registres OH, d'EAX, de DX, de DL, de CAD, et d'EDX peut être utilisée par l'assembly pour effectuer la conversion de données.  
  
 utilisez un registre différent.  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)