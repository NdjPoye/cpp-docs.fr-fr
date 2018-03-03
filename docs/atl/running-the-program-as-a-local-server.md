---
title: "Le programme en cours d’exécution en tant qu’un serveur Local | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- debugging [ATL], running services as local server
- ATL services, running as local servers
ms.assetid: eb9701e6-e2a8-4666-897f-0c893aec8ac7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3e398bfed0174e4ec2a262ea03076ed17881f900
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="running-the-program-as-a-local-server"></a>Le programme en cours d’exécution en tant qu’un serveur Local
Si le programme en cours d’exécution en tant que service n’est pas pratique, vous pouvez modifier temporairement le Registre afin que le programme est exécuté en tant qu’un fonctionnement normal du serveur local. Renommer simplement le `LocalService` valeur sous votre AppID à `_LocalService` et assurez-vous que le `LocalServer32` clé sous votre CLSID est définie correctement. (Notez que, à l’aide de DCOMCNFG pour spécifier que votre application doit être exécutée sur un ordinateur différent renomme votre `LocalServer32` clé à `_LocalServer32`.) Exécuter votre programme, comme un serveur local prend quelques secondes supplémentaires au démarrage, car l’appel à **StartServiceCtrlDispatcher** dans `CAtlServiceModuleT::Start` prend quelques secondes avant d’échouer.  
  
## <a name="see-also"></a>Voir aussi  
 [Conseils de débogage](../atl/debugging-tips.md)

