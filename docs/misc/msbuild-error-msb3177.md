---
title: "MSBuild Error MSB3177 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateManifest.AllowPartiallyTrustedCallers"
helpviewer_keywords: 
  - "MSB3177"
ms.assetid: 0b2417d5-3bc3-4169-b69c-a4a3cbf47882
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3177
**MSB3177 : La référence '\<référence\>' n'autorise pas les appelants dont le niveau de confiance n'est pas suffisant.**  
  
 Cet avertissement est généré pendant la génération du manifeste d'application lorsque l'application est une application d'un niveau de confiance partiel et si *reference* a été ajouté comme référence de projet, a un nom fort et ne contient pas l'attribut APTCA.  
  
### Pour corriger cette erreur  
  
-   Ajoutez l'attribut APTCA à l'assembly référencé, ou cessez de l'utiliser si la première solution n'est pas possible.  
  
## Voir aussi  
 [\<PackageFiles\>, élément](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)