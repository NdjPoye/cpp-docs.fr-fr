---
title: "Héberger des contrôles ActiveX à l’aide d’ATL AXHost | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CAxWindow2T class
- Calendar control (ActiveX), hosting with ATL AXHost
- Calendar control (ActiveX)
- ActiveX controls [C++], hosting
- hosting ActiveX controls
- AXHost method
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2aac8a8b9cbf0b72378a286943faa6e36a8f3f74
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="hosting-activex-controls-using-atl-axhost"></a>Hébergement des contrôles ActiveX à l’aide d’ATL AXHost
L’exemple de cette rubrique montre comment créer AXHost et comment héberger un contrôle ActiveX à l’aide de différentes fonctions ATL. Il montre également comment accéder aux événements de contrôle et le récepteur (à l’aide de [IDispEventImpl](../atl/reference/idispeventimpl-class.md)) à partir du contrôle hébergé. L’exemple héberge le contrôle calendrier dans une fenêtre principale ou dans une fenêtre enfant.  
  
 Notez la définition de la `USE_METHOD` symbole. Vous pouvez modifier la valeur de ce symbole comprise entre 1 et 8. La valeur du symbole détermine comment le contrôle sera créé :  
  
-   Pour les paires de valeurs de `USE_METHOD`, l’appel de création de l’hôte sous-classe une fenêtre et le convertit en un hôte de contrôle. Pour les valeurs impaires, le code crée une fenêtre enfant qui agit comme un ordinateur hôte.  
  
-   Pour les valeurs de `USE_METHOD` compris entre 1 et 4, l’accès au contrôle et la réception des événements s’effectue dans l’appel qui crée également l’hôte. Valeurs comprises entre 5 et 8 interrogent l’hôte pour les interfaces et raccordent le récepteur.  
  
 Voici un résumé :  
  
|USE_METHOD|Hôte|Contrôler l’accès et la réception d’événements|Fonction démontrée|  
|-----------------|----------|--------------------------------------|---------------------------|  
|1|Fenêtre enfant|Une seule étape|CreateControlLicEx|  
|2|Fenêtre principale|Une seule étape|AtlAxCreateControlLicEx|  
|3|Fenêtre enfant|Une seule étape|CreateControlEx|  
|4|Fenêtre principale|Une seule étape|AtlAxCreateControlEx|  
|5|Fenêtre enfant|Plusieurs étapes|CreateControlLic|  
|6|Fenêtre principale|Plusieurs étapes|AtlAxCreateControlLic|  
|7|Fenêtre enfant|Plusieurs étapes|CreateControl|  
|8|Fenêtre principale|Plusieurs étapes|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/cpp/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Forum aux questions sur la contenance de contrôles](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](reference/composite-control-global-functions.md#atlaxcreatecontrol)   
 [AtlAxCreateControlEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [AtlAxCreateControlLic](reference/composite-control-global-functions.md#atlaxcreatecontrollic)   
 [AtlAxCreateControlLicEx](reference/composite-control-global-functions.md#atlaxcreatecontrolex)   
 [Classe de CAxWindow2T](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic, interface](../atl/reference/iaxwinhostwindowlic-interface.md)

