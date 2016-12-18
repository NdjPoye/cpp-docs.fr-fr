---
title: "La casse du nom de l’espace de noms &#39;&lt;nom_espace_noms1&gt;&#39; ne correspond pas &#224; la casse du nom de l’espace de noms &#39;&lt;nom_espace_noms2&gt;&#39; dans le fichier &#39;&lt;chemin_fichier&gt;&#39; | Microsoft Docs"
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
  - "vbc40055"
  - "bc40055"
helpviewer_keywords: 
  - "BC40055"
ms.assetid: adaac2fe-1513-4234-afe7-633a76089f36
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# La casse du nom de l’espace de noms &#39;&lt;nom_espace_noms1&gt;&#39; ne correspond pas &#224; la casse du nom de l’espace de noms &#39;&lt;nom_espace_noms2&gt;&#39; dans le fichier &#39;&lt;chemin_fichier&gt;&#39;
Un espace de noms apparaît plusieurs fois dans le projet, mais avec une casse différente.  
  
 La *casse* renvoie à l’utilisation de caractères majuscules et minuscules dans le nom d’un élément de programmation. Visual Basic n’est pas sensible à la casse, mais le common language runtime \(CLR\) l’est. Pour plus d’informations, consultez « Respect de la casse dans noms » dans [Declared Element Names](../Topic/Declared%20Element%20Names%20\(Visual%20Basic\).md).  
  
 Par défaut, ce message est un avertissement. Pour plus d’informations sur le masquage des avertissements ou leur traitement en tant qu’erreurs, consultez [Configuration d'avertissements en Visual Basic](../Topic/Configuring%20Warnings%20in%20Visual%20Basic.md).  
  
 **ID d’erreur :** BC40055  
  
### Pour corriger cette erreur  
  
-   Par précaution, utilisez toujours la même casse dans chaque référence à un espace de noms. Cela vous évitera peut\-être une mauvaise interprétation du common language runtime.  
  
## Voir aussi  
 [Namespace Statement](../Topic/Namespace%20Statement.md)   
 [Espaces de noms dans Visual Basic](../Topic/Namespaces%20in%20Visual%20Basic.md)   
 [Declared Element Names](../Topic/Declared%20Element%20Names%20\(Visual%20Basic\).md)   
 [Visual Basic Naming Conventions](../Topic/Visual%20Basic%20Naming%20Conventions.md)