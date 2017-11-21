---
title: Fonction CAtlServiceModuleT::Handler | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CServiceModule::Handler
- CServiceModule.Handler
- Handler
dev_langs: C++
helpviewer_keywords: Handler method
ms.assetid: 14db5f2a-be87-4774-a296-445cb6fc7b2e
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9f8c83db3f7834c79656adc3443fd3c8946a4176
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="catlservicemodulethandler-function"></a>Fonction CAtlServiceModuleT::Handler
`CAtlServiceModuleT::Handler`est la routine du Gestionnaire de contrôle des services (SCM) appelle pour récupérer l’état du service et lui donner différentes instructions (par exemple, arrêter ou suspendre). Le SCM passe un code d’opération à `Handler` pour indiquer comme le service. Un service de généré ATL par défaut gère uniquement l’instruction d’arrêt. Si le SCM passe l’instruction d’arrêt, le service indique au SCM que le programme est sur le point d’arrêt. Le service appelle ensuite `PostThreadMessage` pour publier un message à elle-même. Cela met fin à la boucle de messages et le service se ferme définitivement.  
  
 Pour gérer des instructions plus détaillées, vous devez modifier le `m_status` membre de données initialisé dans la `CAtlServiceModuleT` constructeur. Ce membre de données indique au SCM les boutons à activer lorsque le service est sélectionné dans l’application Services du panneau.  
  
## <a name="see-also"></a>Voir aussi  
 [Services](../atl/atl-services.md)   
 [CAtlServiceModuleT::Handler](../atl/reference/catlservicemodulet-class.md#handler)

