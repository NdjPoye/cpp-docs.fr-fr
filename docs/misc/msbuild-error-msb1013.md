---
title: "MSBuild Error MSB1013 | Microsoft Docs"
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
  - "MSBuild.RepeatedResponseFileError"
helpviewer_keywords: 
  - "MSB1013"
ms.assetid: 3e85c710-99e6-4141-b058-63a144a06454
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1013
**Le fichier réponse a été spécifié deux fois.  Un fichier réponse ne peut être spécifié qu'une seule fois.**  
  
 La ligne de commande contient des références à plusieurs fichiers réponse.  Par exemple, `msbuild @response.rsp @response.rsp`.  
  
 Cette erreur peut également se produire si le fichier réponse spécifié contient une référence à un autre fichier réponse qui contient une référence au fichier réponse d'origine.  Un fichier réponse ne peut être spécifié qu'une seule fois pour chaque compilation.  
  
### Pour corriger cette erreur  
  
-   Supprimez la référence en double au fichier réponse.  Par exemple, utilisez `msbuild @response.rsp` au lieu de `msbuild @response.rsp @response.rsp`.  
  
-   Supprimez la référence au fichier réponse d'origine du fichier réponse qui contient la référence.  
  
## Voir aussi  
 [Command\-Line Reference](../Topic/MSBuild%20Command-Line%20Reference.md)