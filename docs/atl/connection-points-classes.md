---
title: Classes de Points de connexion (ATL) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.connection
dev_langs: C++
helpviewer_keywords:
- classes [C++], connection points
- connection points classes
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: e85194547b78e3d3fa3bba868be02c705fcf9a43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="connection-points-classes"></a>Classes de Points de connexion
Les classes suivantes fournissent la prise en charge des points de connexion :  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) implémente un conteneur de point de connexion.  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) implémente un point de connexion.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) implémente un point de connexion représentant la [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) interface.  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) gère un nombre illimité de connexions entre un point de connexion et ses récepteurs.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) gère un nombre fixe de connexions entre un point de connexion et ses récepteurs.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) notifie le récepteur d’un client qui a changé de propriété d’un objet ou va être modifiée.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) prend en charge les points de connexion pour un objet COM ATL. Ces points de connexion sont mappés avec une table de récepteur d’événements, qui est fournie par votre objet COM.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) fonctionne conjointement avec le récepteur d’événements mappe dans votre classe pour les événements d’itinéraire à la fonction gestionnaire approprié.  
  
## <a name="related-articles"></a>Articles connexes  
 [Points de connexion](../atl/atl-connection-points.md)  
  
 [Gestion des événements et ATL](../atl/event-handling-and-atl.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../atl/atl-class-overview.md)   
 [Macros de Point de connexion](../atl/reference/connection-point-macros.md)   
 [Fonctions globales de point de connexion](../atl/reference/connection-point-global-functions.md)

