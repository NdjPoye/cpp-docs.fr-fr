---
title: "MSBuild Error MSB3111 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.ConfigBindingRedirectsWithPartialTrust"
helpviewer_keywords: 
  - "MSB3111"
ms.assetid: f01286a1-ba27-4733-a431-35ffe9a31356
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3111
**MSB3111 : L'utilisation des redirections de liaison app.config requiert une confiance totale.**  
  
 Cet avertissement est généré lorsque le processus de génération détecte que l'application a essayé de rediriger certains de ses assemblys vers une autre version dans le fichier app.config.  Cela ne fonctionne pas pour les applications d'un niveau de confiance partiel.  
  
## Voir aussi  
 [Référence du schéma de produit et de package](../Topic/Product%20and%20Package%20Schema%20Reference.md)