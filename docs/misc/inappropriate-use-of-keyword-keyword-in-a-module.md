---
title: "Utilisation inappropri&#233;e du mot cl&#233; &lt;mot_cl&#233;&gt; dans un module | Microsoft Docs"
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
  - "vbc42028"
  - "BC42028"
helpviewer_keywords: 
  - "BC42028"
ms.assetid: a9bc1e9d-ba2c-4a71-b147-0fb66f670316
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Utilisation inappropri&#233;e du mot cl&#233; &lt;mot_cl&#233;&gt; dans un module
Les modules n’ont pas d’instances, ne prennent pas en charge l’héritage et n’implémentent pas les interfaces. Les mots clés suivants ne s’appliquent donc pas à une déclaration de module :  
  
-   [MustInherit](../Topic/MustInherit%20\(Visual%20Basic\).md)  
  
-   [NotInheritable](../Topic/NotInheritable%20\(Visual%20Basic\).md)  
  
-   [Overloads](../Topic/Overloads%20\(Visual%20Basic\).md)  
  
-   [Private](../Topic/Private%20\(Visual%20Basic\).md)  
  
-   [Protected](../Topic/Protected%20\(Visual%20Basic\).md)  
  
-   [Shadows](../Topic/Shadows%20\(Visual%20Basic\).md)  
  
-   [Shared](../Topic/Shared%20\(Visual%20Basic\).md)  
  
-   [Static](../Topic/Static%20\(Visual%20Basic\).md)  
  
 Les seuls mots clés pris en charge dans une [Module Statement](../Topic/Module%20Statement.md) sont [Public](../Topic/Public%20\(Visual%20Basic\).md) et [Friend](../Topic/Friend%20\(Visual%20Basic\).md).  
  
 De plus, vous ne pouvez pas utiliser l’instruction [Implements](../Topic/Implements%20Clause%20\(Visual%20Basic\).md) ni l’instruction [Inherits Statement](../Topic/Inherits%20Statement.md) dans le bloc d’instructions du module.  
  
 Par défaut, ce message est un avertissement. Pour plus d’informations sur le masquage des avertissements ou le traitement des avertissements en tant qu’erreurs, consultez [Configuration d'avertissements en Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **ID d’erreur :** BC42028  
  
### Pour corriger cette erreur  
  
-   Si vous prévoyez d’utiliser cet élément de programmation en tant que module, utilisez uniquement le mot clé `Public` ou `Friend` dans sa déclaration. Par défaut, un module utilise `Friend` si vous ne spécifiez pas son niveau d’accès.  
  
-   Si vous envisagez de créer des instances de cet élément de programmation, déclarez\-le en tant que classe. Vous pouvez ensuite utiliser les mots clés qui s’appliquent à une déclaration de classe.  
  
## Voir aussi  
 [Class Statement](../Topic/Class%20Statement%20\(Visual%20Basic\).md)