---
title: "CAtlServiceModuleT::Start Function | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule.Start"
  - "CServiceModule::Start"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Start (méthode)"
ms.assetid: b5193a23-41bc-42d2-8d55-3eb43dc62238
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# CAtlServiceModuleT::Start Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque le service est dirigée, **\_tWinMain** appelle **CAtlServiceModuleT::WinMain**, qui appelle ensuite `CAtlServiceModuleT::Start`.  
  
 `CAtlServiceModuleT::Start` d'un tableau de structures de **SERVICE\_TABLE\_ENTRY** qui mappent chaque service à sa fonction de démarrage.  Ce tableau est ensuite passée à la fonction de l'API Win32, [StartServiceCtrlDispatcher](http://msdn.microsoft.com/library/windows/desktop/ms686324).  En théorie, un EXÉCUTABLE peut gérer plusieurs services et tableau peut avoir plusieurs structures de **SERVICE\_TABLE\_ENTRY** .  Actuellement, toutefois, prend en charge après\-vente ATL générés un seul service par EXE.  Par conséquent, le tableau a une entrée unique qui contient le nom du service et **\_ServiceMain** lorsque la fonction de démarrage.  **\_ServiceMain** est une fonction membre statique d' `CAtlServiceModuleT` qui appelle la fonction membre non statique, `ServiceMain`.  
  
> [!NOTE]
>  Le manque de **StartServiceCtrlDispatcher** de se connecter au gestionnaire de contrôle des services \(SCM\) signifie peut\-être que le programme ne s'exécute pas comme un service.  Dans ce cas, le programme appelle `CAtlServiceModuleT::Run` directement afin que le programme puisse fonctionner comme un serveur local.  Pour plus d'informations sur l'exécution du programme en tant que serveur local, consultez [conseils de débogage](../atl/debugging-tips.md).  
  
## Voir aussi  
 [Services](../atl/atl-services.md)   
 [CAtlServiceModuleT::Start](../Topic/CAtlServiceModuleT::Start.md)