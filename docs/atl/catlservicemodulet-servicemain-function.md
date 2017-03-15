---
title: "CAtlServiceModuleT::ServiceMain Function | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ServiceMain"
  - "CServiceModule::ServiceMain"
  - "CServiceModule.ServiceMain"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ServiceMain method"
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CAtlServiceModuleT::ServiceMain Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le gestionnaire de contrôle des services \(SCM\) appelle `ServiceMain` lorsque vous ouvrez l'application du panneau de configuration des services, sélectionnez le service, puis cliquez sur **Démarrer**.  
  
 Une fois le SCM appelle `ServiceMain`, un service doit donner au SCM une fonction gestionnaire.  Cette fonction permet d'obtenir SCM le mode de service et passer des instructions spécifiques \(telles que suspendre ou arrêter\).  SCM Le reçoit cette fonction lorsqu'il passe **\_Handler** à la fonction de l'API Win32, [RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054)de service.  \(**\_Handler** est une fonction membre statique qui appelle la fonction [Gestionnaire](../atl/catlservicemodulet-handler-function.md)de membre non statique.\)  
  
 Au démarrage, un service doit également informer le SCM de son état actuel.  Il le fait en passant **SERVICE\_START\_PENDING** à la fonction de l'API Win32, [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241).  
  
 `ServiceMain` appelle ensuite `CAtlExeModuleT::InitializeCom`, qui appelle la fonction [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279)API Win32.  Par défaut, `InitializeCom` passe la balise de **COINIT\_MULTITHREADED** à la fonction.  Cet indicateur indique que le programme doit être un serveur libre de threads.  
  
 Maintenant, `CAtlServiceModuleT::Run` est appelé pour effectuer le travail principaux du service.  **Run** continue à s'exécuter jusqu'à ce que le service est arrêté.  
  
## Voir aussi  
 [Services](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../Topic/CAtlServiceModuleT::ServiceMain.md)