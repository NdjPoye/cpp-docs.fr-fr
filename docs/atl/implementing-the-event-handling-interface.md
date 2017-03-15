---
title: "Implementing the Event Handling Interface | Microsoft Docs"
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
  - "ATL, gestion des événements"
  - "gestion des événements, ATL"
  - "interfaces, event and event sink"
ms.assetid: eb2a5b33-88dc-4ce3-bee0-c5c38ea050d7
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing the Event Handling Interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL vous aide à chacun des trois éléments requis pour gérer des événements : implémentant l'interface d'événement, informant la source d'événement, et unadvising la source d'événement.  Les dimensions exactes que vous devez prendre dépendent du type de l'interface d'événement et des spécifications de performances de votre application.  
  
 Les méthodes les plus courantes pour implémenter une interface à l'aide de ATL sont :  
  
-   Dérivation d'une interface personnalisée directement.  
  
-   Dérivation d' [IDispatchImpl](../atl/reference/idispatchimpl-class.md) pour les interfaces doubles décrites dans une bibliothèque de types.  
  
-   Dérivation d' [IDispEventImpl](../atl/reference/idispeventimpl-class.md) pour les dispinterfaces décrites dans une bibliothèque de types.  
  
-   Dérivation d' [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md) pour les dispinterfaces non décrites dans une bibliothèque de types ou lorsque vous souhaitez améliorer l'efficacité en chargeant ne pas les informations de type au moment de l'exécution.  
  
 Si vous implémentez un personnalisé ou une interface double, vous devez indiquer à la source de l'événement en appelant [AtlAdvise](../Topic/AtlAdvise.md) ou [CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md).  Vous devez stocker le cookie retourné par l'appel vous\-même.  Appel [AtlUnadvise](../Topic/AtlUnadvise.md) pour arrêter la connexion.  
  
 Si vous implémentez une dispinterface à l'aide de `IDispEventImpl` ou `IDispEventSimpleImpl`, vous devez indiquer à la source de l'événement en appelant [IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md).  Appel [IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md) pour arrêter la connexion.  
  
 Si vous utilisez `IDispEventImpl` comme classe de base d'un contrôle composite, les sources d'événements répertoriées dans le mappage de récepteur sont conseillées et imprudentes automatiquement à l'aide de [CComCompositeControl::AdviseSinkMap](../Topic/CComCompositeControl::AdviseSinkMap.md).  
  
 Les classes d' `IDispEventImpl` et d' `IDispEventSimpleImpl` gèrent le cookie pour vous.  
  
## Voir aussi  
 [Gestion des événements](../atl/event-handling-and-atl.md)