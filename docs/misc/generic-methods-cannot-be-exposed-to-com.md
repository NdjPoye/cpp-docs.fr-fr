---
title: "Les m&#233;thodes g&#233;n&#233;riques ne peuvent pas &#234;tre expos&#233;es &#224; COM | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30943"
  - "bc30943"
helpviewer_keywords: 
  - "BC30943"
ms.assetid: 0e3bff62-f187-4864-8520-70f6be22e869
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Les m&#233;thodes g&#233;n&#233;riques ne peuvent pas &#234;tre expos&#233;es &#224; COM
Un composant [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] contenant une ou plusieurs procédures génériques est exporté vers un composant COM.  
  
 Le modèle COM \(Component Object Model\) ne prend pas en charge les types génériques et ne peut pas interagir avec eux.  
  
 **ID d’erreur :** BC30943  
  
### Pour corriger cette erreur  
  
-   Supprimez les procédures génériques du composant [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)], ou ne les utilisez pas pour COM Interop.  
  
## Voir aussi  
 [Types génériques Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)   
 [COM Interop](../Topic/COM%20Interop%20\(Visual%20Basic\).md)