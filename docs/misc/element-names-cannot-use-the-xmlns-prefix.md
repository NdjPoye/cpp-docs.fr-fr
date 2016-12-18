---
title: "Les noms d’&#233;l&#233;ments ne peuvent pas utiliser le pr&#233;fixe &#39;xmlns&#39; | Microsoft Docs"
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
  - "vbc31189"
  - "bc31189"
helpviewer_keywords: 
  - "BC31189"
ms.assetid: 88716bb5-6766-4180-b2ed-1d1bee0ff7a6
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Les noms d’&#233;l&#233;ments ne peuvent pas utiliser le pr&#233;fixe &#39;xmlns&#39;
Vous avez spécifié un littéral d’élément XML avec un préfixe d’espace de noms XML `xmlns`. Exemple :  
  
```vb#  
Dim elem = <xmlns:ElementName>  
```  
  
 La spécification XML 1.0 identifie `xmlns` comme mot réservé.  
  
 **ID d’erreur :** BC31189  
  
### Pour corriger cette erreur  
  
-   Remplacez le préfixe d’espace de noms XML par une valeur valide ou supprimez le préfixe.  
  
## Voir aussi  
 [XML Literals](../Topic/XML%20Literals%20\(Visual%20Basic\).md)   
 [Imports Statement \(XML Namespace\)](../Topic/Imports%20Statement%20\(XML%20Namespace\).md)   
 [XML](../Topic/XML%20in%20Visual%20Basic.md)