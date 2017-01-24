---
title: "Les instructions &#39;Declare&#39; ne sont pas autoris&#233;es dans les types g&#233;n&#233;riques ou les types contenus dans des types g&#233;n&#233;riques | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BC32075"
  - "vbc32075"
helpviewer_keywords: 
  - "BC32075"
ms.assetid: c620b67e-70f8-42ac-8292-e9ea484904c3
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Les instructions &#39;Declare&#39; ne sont pas autoris&#233;es dans les types g&#233;n&#233;riques ou les types contenus dans des types g&#233;n&#233;riques
Une instruction `Declare` apparaît dans le cadre d’une classe ou d’une structure générique, ou encore dans le cadre d’une classe ou d’une structure déclarée dans une classe ou une structure générique.  
  
 Visual Basic et .NET Framework ne prennent actuellement en charge aucune combinaison de références externes et de types génériques. Pour pouvoir l’appeler correctement, le compilateur nécessite tous les paramètres et le type de retour d’une procédure externe.  
  
 **ID d’erreur :** BC32075  
  
### Pour corriger cette erreur  
  
-   Déplacer l’instruction `Declare` hors de l’étendue de tout type générique ou supprimez\-le entièrement.  
  
## Voir aussi  
 [Declare Statement](../Topic/Declare%20Statement.md)   
 [Types génériques Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)