---
title: "&#39;Exit Sub&#39; n’est pas valide dans un Function ni un Property | Microsoft Docs"
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
  - "bc30065"
  - "vbc30065"
helpviewer_keywords: 
  - "BC30065"
ms.assetid: d6426861-ba64-4dca-9100-262c6c058bd9
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Exit Sub&#39; n’est pas valide dans un Function ni un Property
`Exit Sub` s’affiche dans une procédure `Function` ou `Property`. Une instruction `Exit` doit correspondre au bloc dans lequel elle apparaît.  
  
 **ID d’erreur :** BC30065  
  
### Pour corriger cette erreur  
  
-   Remplacez le `Exit Sub` par l’instruction `Exit Function` ou `Exit Property` comme il convient.  
  
## Voir aussi  
 [Sub Procedures](../Topic/Sub%20Procedures%20\(Visual%20Basic\).md)   
 [Function, procédures](../Topic/Function%20Procedures%20\(Visual%20Basic\).md)   
 [Procédures de propriété](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)