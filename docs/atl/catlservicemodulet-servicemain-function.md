---
title: Fonction CAtlServiceModuleT::ServiceMain | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ServiceMain
- CServiceModule::ServiceMain
- CServiceModule.ServiceMain
dev_langs: C++
helpviewer_keywords: ServiceMain method
ms.assetid: f21408c1-1919-4dec-88d8-bf5b39ac9808
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6abb297f6873c654cf359a63638338f288f45613
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="catlservicemoduletservicemain-function"></a>Fonction CAtlServiceModuleT::ServiceMain
Le Gestionnaire de contrôle des services (SCM) appelle `ServiceMain` lorsque vous ouvrez l’application Services du panneau, sélectionnez le service, puis cliquez sur **Démarrer**.  
  
 Après le SCM appelle `ServiceMain`, un service doit donner au SCM une fonction gestionnaire. Cette fonction permet au SCM obtenir l’état du service et de transférer des instructions spécifiques (par exemple, la mise en pause ou l’arrêt). Le SCM obtient cette fonction lorsque le service passe **_Handler** à la fonction API Win32, [RegisterServiceCtrlHandler](http://msdn.microsoft.com/library/windows/desktop/ms685054). (**_Handler** est une fonction membre statique qui appelle la fonction membre non statique [gestionnaire](../atl/reference/catlservicemodulet-class.md#handler).)  
  
 Au démarrage, un service doit également informer le SCM de son état actuel. Pour ce faire, il en passant **SERVICE_START_PENDING** à la fonction API Win32, [SetServiceStatus](http://msdn.microsoft.com/library/windows/desktop/ms686241).  
  
 `ServiceMain`appelle ensuite `CAtlExeModuleT::InitializeCom`, qui appelle la fonction API Win32 [CoInitializeEx](http://msdn.microsoft.com/library/windows/desktop/ms695279). Par défaut, `InitializeCom` transmet le **COINIT_MULTITHREADED** indicateur à la fonction. Cet indicateur indique que le programme doit être un serveur libre de threads.  
  
 Maintenant, `CAtlServiceModuleT::Run` est appelée pour effectuer le travail principal du service. **Exécutez** continue à s’exécuter jusqu'à ce que le service est arrêté.  
  
## <a name="see-also"></a>Voir aussi  
 [Services](../atl/atl-services.md)   
 [CAtlServiceModuleT::ServiceMain](../atl/reference/catlservicemodulet-class.md#servicemain)

