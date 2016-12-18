---
title: "Instruction d&#39;expression | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "instructions d'expression"
  - "instructions, expression"
ms.assetid: 547d7f7a-58be-4ffc-a4b3-d64c7ae7538c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Instruction d&#39;expression
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les instructions d'expression entraînent des expressions à évaluer.  Aucun transfert de contrôle ou d'itération n'a lieu à la suite d'une instruction d'expression.  
  
 La syntaxe de l'instruction d'expression est simplement  
  
## Syntaxe  
  
```  
[expression ] ;  
```  
  
## Notes  
 Toutes les expressions appartenant à une instruction d'expression sont évaluées et tous les effets secondaires sont terminés avant l'exécution de l'instruction suivante.  Les instructions d'expression les plus courantes sont les assignations et les appels de fonction.  Étant donné que l'expression est facultative, seul un point\-virgule est considéré comme une instruction d'expression vide, connue sous le nom d'instruction [null](../cpp/null-statement.md).  
  
## Voir aussi  
 [Vue d'ensemble des instructions C\+\+](../cpp/overview-of-cpp-statements.md)