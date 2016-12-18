---
title: "Les op&#233;rateurs doivent &#234;tre d&#233;clar&#233;s &#39;Shared&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc33012"
  - "bc33012"
helpviewer_keywords: 
  - "BC33012"
ms.assetid: 5ad97616-4032-46cd-aaf7-517db5d1195f
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Les op&#233;rateurs doivent &#234;tre d&#233;clar&#233;s &#39;Shared&#39;
[Operator Statement](../Topic/Operator%20Statement.md) n’inclut pas le mot clé [Shared](../Topic/Shared%20\(Visual%20Basic\).md).  
  
 Une procédure `Operator` exige les deux mots clés [Public](../Topic/Public%20\(Visual%20Basic\).md) et `Shared`, et un opérateur de conversion nécessite également le mot clé [Widening](../Topic/Widening%20\(Visual%20Basic\).md) ou le mot clé [Narrowing](../Topic/Narrowing%20\(Visual%20Basic\).md).  
  
 **ID d’erreur :** BC33012  
  
### Pour corriger cette erreur  
  
-   Ajoutez le mot clé `Shared` à l’instruction `Operator`.  
  
## Voir aussi  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)