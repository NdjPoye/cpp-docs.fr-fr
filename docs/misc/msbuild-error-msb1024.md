---
title: "MSBuild Error MSB1024 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.MultipleSchemasError"
helpviewer_keywords: 
  - "MSB1024"
ms.assetid: dff30870-da1a-479f-998b-03d0f5e16088
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1024
**Un seul schéma peut être spécifié pour la validation du projet.**  
  
 Un seul schéma peut être spécifié pour le commutateur **\/validate**.  
  
### Pour corriger cette erreur  
  
1.  Spécifiez un seul schéma par rapport auquel valider le projet à l'aide du format `/validate:<schema>`, par exemple, `/validate:MyExtendedBuildSchema.xsd`  
  
## Voir aussi  
 [Command\-Line Reference](../Topic/MSBuild%20Command-Line%20Reference.md)