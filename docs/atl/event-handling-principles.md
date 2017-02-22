---
title: "Event Handling Principles | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces doubles, event interfaces"
  - "gestion des événements, advising event sources"
  - "gestion des événements, dual event interfaces"
  - "gestion des événements, implémenter"
  - "interfaces, event and event sink"
ms.assetid: d17ca7cb-54f2-4658-ab8b-b721ac56801d
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Event Handling Principles
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Il existe trois étapes communes à toutes la gestion des événements.  Vous aurez besoin :  
  
-   Implémentez l'interface d'événements sur votre objet.  
  
-   Informez la source d'événements que votre objet souhaite recevoir des événements.  
  
-   Unadvise la source d'événements lorsque votre objet ne doit plus recevoir des événements.  
  
 La façon dont vous allez implémenter l'interface d'événement dépend de son type.  Une interface d'événement peut être vtable, double, ou une dispinterface.  Il appartient au concepteur de la source d'événements pour définir l'interface ; il vous appartient pour implémenter cette interface.  
  
> [!NOTE]
>  Bien qu'il n'y a aucune raison technique pour laquelle une interface d'événement ne peut pas être double, un certain nombre de bonnes raisons de conception pour éviter l'utilisation de conjugue.  Toutefois, il s'agit d'une décision prise par le concepteur\/implémenteur de la source d'événement.  Étant donné que vous travaillez du point de vue de l'événement `sink`, vous devez tenir compte de la possibilité que vous ne pouvez avoir aucun tableau mais implémenter une interface double d'événements.  Pour plus d'informations sur les interfaces doubles, consultez l' [interfaces doubles et ATL](../atl/dual-interfaces-and-atl.md).  
  
 Informer la source d'événements peut être divisé en trois étapes :  
  
-   Interrogez l'objet source pour [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857).  
  
-   Appelez [IConnectionPointContainer::FindConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms692476) passant l'IID de l'interface d'événement qui vous intéresse.  En cas de réussite, il retourne l'interface d' [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318) sur un objet de point de connexion.  
  
-   Appelez [IConnectionPoint::Advise](http://msdn.microsoft.com/library/windows/desktop/ms678815) passant **IUnknown** du récepteur d'événements.  En cas de réussite, il retourne un cookie d' `DWORD` représentant la connexion.  
  
 Une fois que vous avez correctement inscrit votre intérêt en recevant des événements, des méthodes sur l'interface d'événement de l'objet sont appelées en fonction de les événements déclenchés par l'objet source.  Lorsque vous n'avez plus besoin de recevoir des événements, vous pouvez passer le cookie au point de connexion via [IConnectionPoint::Unadvise](http://msdn.microsoft.com/library/windows/desktop/ms686608).  Cela conduirait à rompre la connexion entre la source et le récepteur.  
  
 Veillez à éviter des cycles de référence en gérant des événements.  
  
## Voir aussi  
 [Gestion des événements](../atl/event-handling-and-atl.md)