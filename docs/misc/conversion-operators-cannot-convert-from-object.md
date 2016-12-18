---
title: "Les op&#233;rateurs de conversion ne peuvent pas convertir &#224; partir du type Object | Microsoft Docs"
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
  - "bc33032"
  - "vbc33032"
helpviewer_keywords: 
  - "BC33032"
ms.assetid: 877f626f-7aa1-41d8-b7ca-eb4337d012d1
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Les op&#233;rateurs de conversion ne peuvent pas convertir &#224; partir du type Object
Un opérateur de conversion est déclaré avec un paramètre de [Object Data Type](../Topic/Object%20Data%20Type.md).  
  
 Au moment de la compilation, [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)] considère qu’une conversion prédéfinie existe entre un type référence et un type quelconque de sa hiérarchie d’héritage, c’est\-à\-dire tout type dont il dérive ou qui en dérive.`Object` est le type de données universel dans [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)], si bien que chaque type dérive du type `Object`.  
  
 Étant donné que le compilateur considère cette conversion comme étant déjà définie, il ne vous permet pas de la redéfinir.  
  
 **ID d’erreur :** BC33032  
  
### Pour corriger cette erreur  
  
-   Supprimez entièrement la définition de cet opérateur. Il est déjà prédéfini.  
  
## Voir aussi  
 [Operator Procedures](../Topic/Operator%20Procedures%20\(Visual%20Basic\).md)   
 [Operator Statement](../Topic/Operator%20Statement.md)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)   
 [Object en tant que type de données universel \(Visual Basic\)](http://msdn.microsoft.com/fr-fr/5315bf21-2b22-45ab-98cd-5631dffbcb2f)