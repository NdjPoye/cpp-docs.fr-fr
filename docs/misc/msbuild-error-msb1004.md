---
title: "MSBuild Error MSB1004 | Microsoft Docs"
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
  - "MSBuild.MissingTargetError"
helpviewer_keywords: 
  - "MSB1004"
ms.assetid: aed36761-ab07-486c-b5eb-48ccb1c387dd
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1004
**Spécifiez le nom de la cible.**  
  
 Au moins une cible doit être spécifiée avec le commutateur **\/target**.  
  
### Pour corriger cette erreur  
  
1.  Spécifiez une ou plusieurs cibles.  Vous pouvez utiliser une virgule ou un point\-virgule pour séparer les cibles de la liste, par exemple, `/target:Clean;Compile`.  Ou bien, vous pouvez répéter le commutateur, par exemple, `/t:Clean /t:` `Compile`  
  
## Voir aussi  
 [Targets](../Topic/MSBuild%20Targets.md)   
 [Command\-Line Reference](../Topic/MSBuild%20Command-Line%20Reference.md)