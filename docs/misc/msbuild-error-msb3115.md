---
title: "MSBuild Error MSB3115 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateManifest.InvalidEntryPoint"
helpviewer_keywords: 
  - "MSB3115"
ms.assetid: 7d9d4156-fd6a-455a-8a3d-b191485f1294
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB3115
**MSB3115 : Le fichier '\<fichier\>' n'est pas un point d'entrée valide.**  
  
 Cette erreur est générée lorsqu'un manifeste spécifie un point d'entrée qui n'est pas valide.  
  
### Pour corriger cette erreur  
  
-   Vérifiez que vous avez spécifié des points d'entrée valides dans vos manifestes.  Pour un manifeste d'application, un point d'entrée valide est un fichier .exe.  Pour un manifeste de déploiement, un point d'entrée valide est un manifeste d'application.