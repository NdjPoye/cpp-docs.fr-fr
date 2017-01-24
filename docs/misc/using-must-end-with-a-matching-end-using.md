---
title: "&#39;Using&#39; doit se terminer par un &#39;End Using&#39; correspondant | Microsoft Docs"
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
  - "vbc36008"
  - "bc36008"
helpviewer_keywords: 
  - "BC36008"
ms.assetid: 83269108-b169-40a6-bbcc-af1ac8fcfd67
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Using&#39; doit se terminer par un &#39;End Using&#39; correspondant
Une instruction `Using` se produit sans instruction `End Using` correspondante.  
  
 Vous devez utiliser une instruction `End Using` pour terminer le bloc `Using`.  
  
 **ID d’erreur :** BC36008  
  
### Pour corriger cette erreur  
  
1.  Si ce bloc `Using` fait partie d’un ensemble de blocs `Using` imbriqués, vérifiez que chaque bloc se termine correctement.  
  
2.  Ajoutez une instruction `End Using` à la fin du bloc `Using`.  
  
## Voir aussi  
 [Using Statement](../Topic/Using%20Statement%20\(Visual%20Basic\).md)   
 [How to: Dispose of a System Resource](../Topic/How%20to:%20Dispose%20of%20a%20System%20Resource%20\(Visual%20Basic\).md)