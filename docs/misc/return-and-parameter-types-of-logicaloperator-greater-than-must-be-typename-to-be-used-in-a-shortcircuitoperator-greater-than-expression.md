---
title: "Les types de retour et de param&#232;tres de &#39;&lt;op&#233;rateur_logique&gt;&#39; doivent &#234;tre &#39;&lt;nom_type&gt;&#39; pour &#234;tre utilis&#233;s dans une expression &#39;&lt;op&#233;rateur_court_circuit&gt;&#39; | Microsoft Docs"
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
  - "vbc33034"
  - "bc33034"
helpviewer_keywords: 
  - "BC33034"
ms.assetid: 94cd52dc-5d48-4673-b0b8-38a1954483c6
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Les types de retour et de param&#232;tres de &#39;&lt;op&#233;rateur_logique&gt;&#39; doivent &#234;tre &#39;&lt;nom_type&gt;&#39; pour &#234;tre utilis&#233;s dans une expression &#39;&lt;op&#233;rateur_court_circuit&gt;&#39;
Un opérateur `And` ou `Or` est déclaré avec des paramètres ou un type de retour inadéquats en vue d’une utilisation dans un [AndAlso Operator](../Topic/AndAlso%20Operator%20\(Visual%20Basic\).md) ou un [OrElse Operator](../Topic/OrElse%20Operator%20\(Visual%20Basic\).md).  
  
 Sachant que vous ne définissez pas directement un opérateur de court\-circuit \(`AndAlso` ou `OrElse`\), vous devez définir les opérateurs logiques et déterminants correspondants. Le tableau suivant présente les opérateurs obligatoires.  
  
|Opérateur de court\-circuit|Opérateur logique|Opérateur déterminant|  
|---------------------------------|-----------------------|---------------------------|  
|`AndAlso`|[And Operator](../Topic/And%20Operator%20\(Visual%20Basic\).md)|[IsFalse Operator](../Topic/IsFalse%20Operator%20\(Visual%20Basic\).md)|  
|`OrElse`|[Or Operator](../Topic/Or%20Operator%20\(Visual%20Basic\).md)|[IsTrue Operator](../Topic/IsTrue%20Operator%20\(Visual%20Basic\).md)|  
  
 [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] utilise ces opérateurs logiques et déterminants pour construire la logique de court\-circuit pour `AndAlso` ou `OrElse`. Pour que cela fonctionne correctement, les opérandes et la valeur de retour de votre définition de `And` ou `Or` doivent être du type conteneur, c’est\-à\-dire du type de la classe ou de la structure dans laquelle vous définissez `And` ou `Or`.  
  
 **ID d’erreur :** BC33034  
  
### Pour corriger cette erreur  
  
-   Remplacez le type des opérandes et de la valeur de retour par le type de la classe ou de la structure dans laquelle vous définissez cet opérateur.  
  
     ou  
  
-   N’utilisez pas l’opérateur de court\-circuit correspondant \(`AndAlso` ou `OrElse`\) avec des opérandes du type de la classe ou de la structure dans laquelle vous définissez cet opérateur `And` ou `Or`.  
  
## Voir aussi  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Logical and Bitwise Operators in Visual Basic](../Topic/Logical%20and%20Bitwise%20Operators%20in%20Visual%20Basic.md)