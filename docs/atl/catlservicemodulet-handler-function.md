---
title: "CAtlServiceModuleT::Handler Function | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CServiceModule::Handler"
  - "CServiceModule.Handler"
  - "Handler"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Handler method"
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAtlServiceModuleT::Handler Function
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CAtlServiceModuleT::Handler` est la routine que le gestionnaire de contrôle des services \(SCM\) appelle pour récupérer l'état du service et pour lui donner à plusieurs instructions \(telles que l'arrêt ou suspendre\).  SCM Le passe un code opération à `Handler` pour indiquer que le service doit faire.  Un service ATL généré par défaut gère uniquement l'instruction stop.  Si le SCM passe l'instruction stop, le service indique au SCM que le programme est sur le point d'arrêt.  Le service appelle ensuite `PostThreadMessage` pour publier un message quitté à lui\-même.  Cela termine la boucle de message et le service se fermera finalement.  
  
 Pour gérer plus d'instructions, vous devez modifier la donnée membre d' `m_status` initialisé dans le constructeur d' `CAtlServiceModuleT` .  Cette donnée membre indique au SCM les boutons pour activer lorsque le service est sélectionné dans l'application du panneau de configuration des services.  
  
## Voir aussi  
 [Services](../atl/atl-services.md)   
 [CAtlServiceModuleT::Handler](../Topic/CAtlServiceModuleT::Handler.md)