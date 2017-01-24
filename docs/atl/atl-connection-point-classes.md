---
title: "ATL Connection Point Classes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, points de connexion"
  - "CComDynamicUnkArray class, connection point classes"
  - "CComUnkArray class, connection point classes"
  - "CFirePropNotifyEvent class"
  - "CFirePropNotifyEvent class, connection point classes"
  - "points de connexion (C++), ATL classes"
ms.assetid: 9582ba71-7ace-4df4-9c9b-1b0636953efc
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Connection Point Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL utilise les classes suivantes pour prendre en charge des points de connexion :  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) implémente un point de connexion.  L'IID de l'interface sortante qu'il représente est passé comme paramètre de modèle.  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) implémente le conteneur de point de connexion et gère la liste d'objets d' `IConnectionPointImpl` .  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) implémente un point de connexion qui représente l'interface d' [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) .  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) gère un nombre arbitraire de connexions entre le point de connexion et les récepteurs.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) gère un nombre prédéfini de plug\-ins comme spécifié par le paramètre de modèle.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) informe le récepteur d'un client qu'une propriété de l'objet a changé ou est sur le point de modifier.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) fournit la prise en charge des points de connexion pour un objet ATL COM.  Ces points de connexion sont mappés à une table de récepteurs d'événements, qui est fournie par l'objet COM.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) fonctionne conjointement avec la table de récepteurs d'événements de votre classe pour router des événements à la fonction gestionnaire appropriée.  
  
## Voir aussi  
 [point de connexion](../atl/atl-connection-points.md)