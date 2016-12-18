---
title: "MSBuild Error MSB4134 | Microsoft Docs"
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
  - "MSB4134"
ms.assetid: 2e4e6beb-c0c9-40ef-b75c-1c16244eba10
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB4134
**MSB4134: DefaultToolsVersion ne peut pas être défini après qu'un projet a été chargé dans le moteur.**  
  
 Cette erreur se produit lorsque vous tentez de modifier la valeur `DefaultToolsVersion` alors que [!INCLUDE[vstecmsbuild](../build/includes/vstecmsbuild_md.md)] a déjà généré un projet.  
  
### Pour corriger cette erreur  
  
-   Modifiez la valeur de `DefaultToolsVersion` avant de générer un projet.  
  
## Voir aussi  
 <xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>   
 <xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>   
 [Project Element \(MSBuild\)](../Topic/Project%20Element%20\(MSBuild\).md)   
 [Additional Resources](../Topic/Additional%20MSBuild%20Resources.md)