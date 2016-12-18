---
title: "D&#233;claration de variable sans clause &#39;As&#39;&#160;; type Object pris par d&#233;faut | Microsoft Docs"
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
  - "BC42020"
  - "vbc42020"
helpviewer_keywords: 
  - "BC42020"
ms.assetid: 9422b16d-39b5-4d49-b697-608226ccafea
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# D&#233;claration de variable sans clause &#39;As&#39;&#160;; type Object pris par d&#233;faut
Une déclaration de propriété ne spécifie pas de clause `As`.  
  
 Une clause `As` identifie un type de données à associer à un élément de programmation. Dans [Dim Statement](../Topic/Dim%20Statement%20\(Visual%20Basic\).md), elle spécifie le type de données de la variable ou des variables. Si vous n’incluez pas de clause `As` dans l’instruction `Dim`, le type de données par défaut de la variable est `Object`.  
  
 Par défaut, ce message est un avertissement. Pour plus d’informations sur le masquage des avertissements ou leur traitement en tant qu’erreurs, consultez [Configuration d'avertissements en Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **ID d’erreur :** BC42020  
  
### Pour corriger cette erreur  
  
-   Incluez une clause `As` dans l’instruction `Dim` pour spécifier le type de données de la variable.  
  
## Voir aussi  
 [Dim Statement](../Topic/Dim%20Statement%20\(Visual%20Basic\).md)   
 [Déclaration de variable](../Topic/Variable%20Declaration%20in%20Visual%20Basic.md)