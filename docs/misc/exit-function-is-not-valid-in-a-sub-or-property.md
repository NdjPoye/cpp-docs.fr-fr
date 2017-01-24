---
title: "&#39;Exit Function&#39; n’est pas valide dans un Sub ni un Property | Microsoft Docs"
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
  - "vbc30067"
  - "bc30067"
helpviewer_keywords: 
  - "BC30067"
ms.assetid: 207fef65-4383-4120-9e5a-e0e14d168a72
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Exit Function&#39; n’est pas valide dans un Sub ni un Property
`Exit Function` apparaît dans une procédure `Sub` ou `Property`. Une instruction `Exit` doit correspondre au bloc dans lequel elle apparaît.  
  
 **ID d’erreur :** BC30067  
  
### Pour corriger cette erreur  
  
-   Remplacez `Exit Function` par l’instruction `Exit Sub` ou `Exit Property` selon les besoins.  
  
## Voir aussi  
 [Sub Procedures](../Topic/Sub%20Procedures%20\(Visual%20Basic\).md)   
 [Function, procédures](../Topic/Function%20Procedures%20\(Visual%20Basic\).md)   
 [Procédures de propriété](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)