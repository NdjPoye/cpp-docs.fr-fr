---
title: "Le modificateur d’acc&#232;s &#39;&lt;modificateur_acc&#232;s&gt;&#39; n’est pas valide | Microsoft Docs"
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
  - "bc31100"
  - "vbc31100"
helpviewer_keywords: 
  - "BC31100"
ms.assetid: 1cd71acc-0b54-4f64-8d61-75b272d293cb
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Le modificateur d’acc&#232;s &#39;&lt;modificateur_acc&#232;s&gt;&#39; n’est pas valide
[Get Statement](../Topic/Get%20Statement.md) ou [Set Statement](../Topic/Set%20Statement%20\(Visual%20Basic\).md) spécifie un niveau d’accès qui est moins restrictif que celui spécifié pour la propriété conteneur.  
  
 Vous pouvez toujours spécifier un niveau d’accès pour la propriété. De plus, vous pouvez spécifier un niveau d’accès différent pour l’une de ses procédures de propriété \(`Get` ou `Set`\), à condition qu’il soit plus restrictif que le niveau d’accès de la propriété. Par exemple, si la propriété a la valeur `Friend`, vous pouvez spécifier `Private` pour une procédure de propriété, mais pas `Public`. Vous ne pouvez pas spécifier de niveaux d’accès pour les deux procédures de propriété.  
  
 **ID d’erreur :** BC31100  
  
### Pour corriger cette erreur  
  
-   Définissez un niveau d’accès pour la procédure de propriété qui soit plus restrictif que celui de la propriété, ou supprimez l’intégralité du modificateur d’accès.  
  
-   Déclarez le niveau d’accès moins restrictif dans l’instruction [Property Statement](../Topic/Property%20Statement.md) et déclarez le niveau d’accès plus restrictif dans l’une des procédures de propriété.  
  
## Voir aussi  
 [Procédures de propriété](../Topic/Property%20Procedures%20\(Visual%20Basic\).md)   
 [How to: Declare a Property with Mixed Access Levels](../Topic/How%20to:%20Declare%20a%20Property%20with%20Mixed%20Access%20Levels%20\(Visual%20Basic\).md)