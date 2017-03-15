---
title: "Vue d&#39;ensemble des instructions C | Microsoft Docs"
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
  - "point-virgule"
  - "point-virgule, dans les instructions C"
  - "instructions, à propos des instructions"
  - "instructions, C"
  - "Visual C, instructions"
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Vue d&#39;ensemble des instructions C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les instructions C se composent de jetons, d'expressions et d'autres instructions.  Une instruction qui forme un composant d'une autre instruction est qualifiée de « corps » de l'instruction englobante.  Chaque type d'instruction donné par la syntaxe suivante est décrit dans cette section.  
  
## Syntaxe  
 *statement*:  
 [labeled\-statement](../c-language/goto-and-labeled-statements-c.md)  
  
 [compound\-statement](../c-language/compound-statement-c.md)  
  
 [expression\-statement](../c-language/expression-statement-c.md)  
  
 [selection\-statement](../c-language/if-statement-c.md)  
  
 [iteration\-statement](../c-language/do-while-statement-c.md)  
  
 [jump\-statement](../c-language/break-statement-c.md)  
  
 [try\-except\-statement](../c-language/try-except-statement-c.md)  
  
 \/\* Spécifique à Microsoft \*\/[try\-finally\-statement](../c-language/try-finally-statement-c.md) \/\* Spécifique à Microsoft \*\/  
  
 Souvent, le corps de l'instruction est une « instruction composée ». Une instruction composée se compose d'autres instructions qui peuvent inclure des mots clés.  L'instruction composée est délimitée par des accolades \(**{ }**\).  Toutes les autres instructions C se terminent par un point\-virgule \(**;**\).  Le point\-virgule est une marque de fin d'instruction.  
  
 Une instruction d'expression contient une expression C qui peut contenir les opérateurs arithmétiques ou logiques présentés dans [Expressions et assignations](../c-language/expressions-and-assignments.md).  L'instruction null est une instruction vide.  
  
 Toute instruction C peut commencer par une étiquette d'identification composée d'un nom et d'un signe deux\-points.  Comme seule l'instruction `goto` identifie des étiquettes d'instruction, les étiquettes d'instruction sont présentées avec `goto`.  Consultez [Instructions goto et étiquetées](../c-language/goto-and-labeled-statements-c.md) pour plus d'informations.  
  
## Voir aussi  
 [Instructions](../c-language/statements-c.md)