---
title: "Le type de param&#232;tre ou le type de retour de cet op&#233;rateur de conversion doit &#234;tre le type conteneur | Microsoft Docs"
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
  - "vbc33022"
  - "bc33022"
helpviewer_keywords: 
  - "BC33022"
ms.assetid: 55baff11-eb35-4c81-bc04-5006524ab450
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Le type de param&#232;tre ou le type de retour de cet op&#233;rateur de conversion doit &#234;tre le type conteneur
Une définition d’opérateur de conversion spécifie à la fois le paramètre et le type de retour avec des types autres que celui de la classe ou structure dans laquelle l’opérateur est défini.  
  
 Quand vous définissez un opérateur de conversion dans une classe ou structure, il doit effectuer la conversion vers ou depuis le type de cette classe ou structure.  
  
 **ID d’erreur :** BC33022  
  
### Pour corriger cette erreur  
  
-   Remplacez le type de paramètre ou le type de retour par le type de la classe ou structure dans laquelle l’opérateur est défini.  
  
## Voir aussi  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)