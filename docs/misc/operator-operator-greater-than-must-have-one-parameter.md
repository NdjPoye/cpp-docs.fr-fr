---
title: "L’op&#233;rateur &#39;&lt;op&#233;rateur&gt;&#39; doit avoir un param&#232;tre | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc33014"
  - "vbc33014"
helpviewer_keywords: 
  - "BC33014"
ms.assetid: 512a5724-a6c5-4437-a608-7d6b10e68d49
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# L’op&#233;rateur &#39;&lt;op&#233;rateur&gt;&#39; doit avoir un param&#232;tre
Un opérateur unaire est défini sans aucun paramètre ou avec plus d’un paramètre.  
  
 Un opérateur unaire doit avoir un seul paramètre.  
  
 **ID d’erreur :** BC33014  
  
### Pour corriger cette erreur  
  
-   Modifiez la définition de façon à spécifier un seul paramètre.  
  
-   Si vous avez besoin de deux paramètres, vous devez définir un opérateur binaire.  
  
-   Si vous n’avez besoin d’aucun paramètre ou si vous en avez besoin de plus de deux, vous devez utiliser [Function Statement](../Topic/Function%20Statement%20\(Visual%20Basic\).md) pour définir une procédure `Function` au lieu d’un opérateur.  
  
## Voir aussi  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)