---
title: "Les accesseurs de propri&#233;t&#233; ne peuvent pas &#234;tre d&#233;clar&#233;s &#39;&lt;modificateur_acc&#232;s&gt;&#39; dans une propri&#233;t&#233; &#39;NotOverridable&#39; | Microsoft Docs"
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
  - "vbc31106"
  - "bc31106"
helpviewer_keywords: 
  - "BC31106"
ms.assetid: 84bcb157-9c33-4e4f-89a9-c5e6cb73028b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Les accesseurs de propri&#233;t&#233; ne peuvent pas &#234;tre d&#233;clar&#233;s &#39;&lt;modificateur_acc&#232;s&gt;&#39; dans une propri&#233;t&#233; &#39;NotOverridable&#39;
Une [Get Statement](../Topic/Get%20Statement.md) ou une [Set Statement](../Topic/Set%20Statement%20\(Visual%20Basic\).md) dans une propriété `NotOverridable` inclut le mot clé `Private`.  
  
 La ligne de raisonnement ci\-dessous explique la raison pour laquelle `NotOverridable` et `Private` ne peuvent pas être associés dans une [Property Statement](../Topic/Property%20Statement.md) :  
  
1.  Une propriété ou une procédure qui ne substitue pas de propriété ou de procédure de classe de base a le paramètre par défaut [NotOverridable](../Topic/NotOverridable%20\(Visual%20Basic\).md).  
  
2.  Toutefois, une propriété ou une procédure dans une classe dérivée qui substitue une propriété ou une procédure de classe de base a le paramètre par défaut [Overridable](../Topic/Overridable%20\(Visual%20Basic\).md). Pour mettre fin à la hiérarchie de substitution, vous pouvez la déclarer `NotOverridable`. Ce contexte est le seul dans lequel vous pouvez utiliser `NotOverridable`. En d’autres termes, vous pouvez utiliser `NotOverridable` uniquement en association avec [Overrides](../Topic/Overrides%20\(Visual%20Basic\).md).  
  
3.  Si une propriété ou une procédure de classe de base est déclarée [Private](../Topic/Private%20\(Visual%20Basic\).md), une classe dérivée ne peut pas substituer cette propriété ou procédure, car elle ne peut pas y accéder. C’est la raison pour laquelle vous ne pouvez pas utiliser `Private` en association avec `Overridable`.  
  
4.  Pour substituer une propriété ou une procédure, la propriété ou la procédure de substitution doit avoir la même signature, mais également le même niveau d’accès. Cela signifie qu’une propriété ou une procédure de substitution ne peut pas spécifier `Private`, car une propriété ou une procédure qui peut être substituée ne peut pas spécifier `Private`.  
  
5.  Étant donné que vous pouvez spécifier `NotOverridable` uniquement sur une propriété ou une procédure de substitution, vous ne pouvez pas l’associer à `Private`.  
  
 En suivant le même raisonnement, les procédures de propriété \(`Get` et `Set`\) d’une propriété de substitution ne peuvent pas avoir la valeur `Private`.  
  
 **ID d’erreur :** BC31106  
  
### Pour corriger cette erreur  
  
-   Supprimez le mot clé `Private` de l’instruction `Get` ou `Set`, ou supprimez les mots clés `Overrides` et `NotOverridable` de l’instruction `Property`.  
  
## Voir aussi  
 [Procédures de propriété](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)   
 [Differences Between Shadowing and Overriding](../Topic/Differences%20Between%20Shadowing%20and%20Overriding%20\(Visual%20Basic\).md)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)