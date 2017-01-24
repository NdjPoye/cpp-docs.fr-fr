---
title: "MSBuild Error MSB3179 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.ComImport"
helpviewer_keywords: 
  - "MSB3179"
ms.assetid: fa744f6c-e398-4e60-b4f7-455ace7e3bd2
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3179
**MSB3179 : Problème d'isolement de la référence COM '\<assembly\>' : '\<erreur\>'**  
  
 Ceci est un message d'erreur générique qui signale un problème avec la génération des entrées du composant COM sans inscription dans le manifeste d'application \(comme spécifié par le paramètre de tâche `IsolatedComReferences`\).  La dernière partie du message d'erreur contient des informations supplémentaires sur la nature du problème.  Cette erreur est peut\-être due au fait que les composants du composant COM sans inscription ne sont pas correctement enregistrés sur l'ordinateur de génération.  
  
### Pour corriger cette erreur  
  
-   Vérifiez que tous les composants COM sont enregistrés sur l'ordinateur de génération.  
  
## Voir aussi  
 [\<PackageFiles\>, élément](../Topic/%3CPackageFiles%3E%20Element%20\(Bootstrapper\).md)