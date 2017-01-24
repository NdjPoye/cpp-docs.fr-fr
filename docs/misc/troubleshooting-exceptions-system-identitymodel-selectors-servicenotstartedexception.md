---
title: "D&#233;pannage des exceptions&#160;: System.IdentityModel.Selectors.ServiceNotStartedException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "System.IdentityModel.Selectors.ServiceNotStartedException (exception)"
  - "ServiceNotStartedException (exception)"
ms.assetid: 6d34bab2-994a-4b0c-893d-19b5d7acf92d
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# D&#233;pannage des exceptions&#160;: System.IdentityModel.Selectors.ServiceNotStartedException
Une exception <xref:System.IdentityModel.Selectors.ServiceNotStartedException> est renvoyée lorsque CardSpace n'a pas été démarré sur l'ordinateur de l'utilisateur. Si CardSpace a tenté de démarrer en vain, pour quelque raison que ce soit, cette exception est renvoyée.  
  
 Vérifiez que le service CardSpace est installé et activé sur l'ordinateur. Essayez de démarrer manuellement le service CardSpace en utilisant la console MMC \(Microsoft Management Console\).  
  
 La version 1 de CardSpace ne prend pas en charge les systèmes de fichiers FAT. Sur les FAT, CardSpace ne démarrera pas et cette exception se produira.  
  
## Voir aussi  
 <xref:System.IdentityModel.Selectors.ServiceNotStartedException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)