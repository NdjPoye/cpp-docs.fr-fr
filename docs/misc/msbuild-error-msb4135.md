---
title: "Erreur MSBuild MSB4135 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSB4135"
ms.assetid: 9192f772-ad13-42f7-b53f-c5e31846fa5f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# Erreur MSBuild MSB4135
**MSB4135: Erreur lors de la lecture des informations relatives à l'ensemble d'outils à partir de la clé de Registre "' &lt ; clé &gt ;'" ou d'une sous\-clé. '  \<clé\>'**  
  
 Les informations relatives à l'ensemble d'outils personnalisées définies dans le Registre n'ont pas pu être lues.  
  
### Pour corriger cette erreur  
  
-   Si vous avez défini un ensemble d'outils personnalisé dans le Registre, assurez\-vous qu'il a un format de Registre valide ou, autrement dit, qu'il porte le nom `ToolsVersion` correct et la valeur `MSBuildBinPath` ou `MSBuildToolsPath` appropriée.  
  
## Voir aussi  
 [Standard and Custom Toolset Configurations](../Topic/Standard%20and%20Custom%20Toolset%20Configurations.md)   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [Additional Resources](../Topic/Additional%20MSBuild%20Resources.md)