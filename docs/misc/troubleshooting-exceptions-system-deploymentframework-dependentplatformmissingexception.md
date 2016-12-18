---
title: "D&#233;pannage des exceptions&#160;: System.DeploymentFramework.DependentPlatformMissingException | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "DependentPlatformMissingException (classe), dépannage"
ms.assetid: fee1ca1c-0f0b-483b-b8ab-3743dfdda038
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.DeploymentFramework.DependentPlatformMissingException
Une exception `T:System.DeploymentFramework.DependentPlatformMissingException` est levée lorsqu'une application dépend d'un élément qui n'est pas installé pas sur ce client. Les causes possibles incluent un système d'exploitation incorrect ou une version incorrecte du [!INCLUDE[dnprdnshort](../error-messages/tool-errors/includes/dnprdnshort_md.md)] sur l'ordinateur sur lequel l'application est déployée.  
  
## Conseils associés  
 **Assurez\-vous que tous les assemblys nécessaires à l'application sont installés sur l'ordinateur cible.**  
 Chaque installation qui tente d'utiliser Windows Installer commence par vérifier si le programme d'installation est présent sur l'ordinateur de l'utilisateur, et, si ce n'est pas le cas, si l'ordinateur est prêt à installer Windows Installer.  
  
## Voir aussi  
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)