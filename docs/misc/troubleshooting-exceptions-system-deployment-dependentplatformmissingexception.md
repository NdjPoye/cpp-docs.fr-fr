---
title: "D&#233;pannage des exceptions&#160;: System.Deployment.DependentPlatformMissingException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "DependentPlatformMissingException (classe)"
ms.assetid: 2343eb4f-f23f-4b6c-a65c-1f93c3e6ea36
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.Deployment.DependentPlatformMissingException
Une exception `T:System.Deployment.DependentPlatformMissingException` est levée lors d'une tentative d'exécution d'une application sur un ordinateur non compatible. Cela peut se produire lorsque le système d'exploitation incorrect ou la version du .NET Framework incorrecte est installé sur l'ordinateur cible.  
  
## Conseils associés  
 **Assurez\-vous que tous les assemblys requis par l'application sont installés sur l'ordinateur cible.**  
 Chaque installation qui tente d'utiliser Windows Installer commence par vérifier si le programme d'installation est présent sur l'ordinateur de l'utilisateur, et, si ce n'est pas le cas, si l'ordinateur est prêt à installer Windows Installer.  
  
## Voir aussi  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)