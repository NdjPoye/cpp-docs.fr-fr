---
title: "Connection Points Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.connection"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes (C++), points de connexion"
  - "connection points classes"
ms.assetid: 076365fa-299a-4dce-84c3-a5dff0e0da1f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Connection Points Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes suivantes fournissent la prise en charge des points de connexion :  
  
-   [IConnectionPointContainerImpl](../atl/reference/iconnectionpointcontainerimpl-class.md) implémente un conteneur de point de connexion.  
  
-   [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) implémente un point de connexion.  
  
-   [IPropertyNotifySinkCP](../atl/reference/ipropertynotifysinkcp-class.md) implémente un point de connexion qui représente l'interface d' [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) .  
  
-   [CComDynamicUnkArray](../atl/reference/ccomdynamicunkarray-class.md) gère les connexions restreinte entre un point de connexion et les récepteurs.  
  
-   [CComUnkArray](../atl/reference/ccomunkarray-class.md) gère un nombre fixe de connexions entre un point de connexion et les récepteurs.  
  
-   [CFirePropNotifyEvent](../atl/reference/cfirepropnotifyevent-class.md) informe le récepteur d'un client qu'une propriété de l'objet a changé ou est sur le point de modifier.  
  
-   [IDispEventImpl](../atl/reference/idispeventimpl-class.md) fournit la prise en charge des points de connexion pour un objet ATL COM.  Ces points de connexion sont mappés à une table de récepteurs d'événements, qui est fournie par l'objet COM.  
  
-   [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) fonctionne conjointement avec la table de récepteurs d'événements de votre classe pour router des événements à la fonction gestionnaire appropriée.  
  
## Articles connexes  
 [Points de connexion](../atl/atl-connection-points.md)  
  
 [Gestion des événements et ATL](../atl/event-handling-and-atl.md)  
  
## Voir aussi  
 [Class Overview](../atl/atl-class-overview.md)   
 [Connection Point Macros](../atl/reference/connection-point-macros.md)   
 [Connection Point Global Functions](../atl/reference/connection-point-global-functions.md)