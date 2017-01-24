---
title: "MSBuild Error MSB1007 | Microsoft Docs"
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
  - "MSBuild.MissingLoggerError"
helpviewer_keywords: 
  - "MSB1007"
ms.assetid: bf45dbc3-50cd-488a-87df-9e647cd71f10
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild Error MSB1007
**Spécifiez un journal.**  
  
 Un journal doit être spécifié pour le commutateur **\/logger**.  
  
### Pour corriger cette erreur  
  
1.  Spécifiez un journal qui utilise à la fois la classe de journalisation et l'assembly de journalisation.  La syntaxe de `<logger>` est la suivante :  
  
     `<logger class>,<logger assembly>[;<logger parameters>]`  
  
     La syntaxe de `<logger class>` est la suivante :  
  
    ```  
    [<partial or full namespace>.]<logger class name>  
    ```  
  
     La syntaxe de `<logger assembly>` est la suivante :  
  
    ```  
    {<assembly name>[,<strong name>] | <assembly file>}  
    ```  
  
     Les paramètres `<logger parameters>` sont facultatifs et passés au journal exactement comme vous les avez tapés.  
  
     Voici quelques exemples du commutateur **\/logger** :  
  
     `/logger:XMLLogger,MyLogger,Version=1.0.2,Culture=neutral`  
  
     `/logger:XMLLogger,C:\Loggers\MyLogger.dll`  
  
     `/logger:XMLLogger,..  \Loggers\MyLogger.dll;OutputAsHTML`  
  
## Voir aussi  
 [Command\-Line Reference](../Topic/MSBuild%20Command-Line%20Reference.md)