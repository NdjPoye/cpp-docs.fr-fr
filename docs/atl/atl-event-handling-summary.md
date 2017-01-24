---
title: "ATL Event Handling Summary | Microsoft Docs"
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
  - "gestion des événements, implémenter"
ms.assetid: e8b47ef0-0bdc-47ff-9dd6-34df11dde9a2
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Event Handling Summary
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Gérer en général des événements COM est un processus relativement simple.  Il existe trois étapes principales :  
  
-   Implémentez l'interface d'événements sur votre objet.  
  
-   Informez la source d'événements que votre objet souhaite recevoir des événements.  
  
-   Unadvise la source d'événements lorsque votre objet ne doit plus recevoir des événements.  
  
## Implémentation de l'interface  
 Il existe quatre manières principales d'implémenter une interface à l'aide de ATL.  
  
|Dériver de|Approprié pour le type d'interface|Requiert que vous utilisiez implémenter tout le methods\*|Requiert une bibliothèque de types au moment de l'exécution|  
|----------------|----------------------------------------|---------------------------------------------------------------|-----------------------------------------------------------------|  
|l'interface|Vtable|Oui|Non|  
|[IDispatchImpl](../atl/reference/idispatchimpl-class.md)|Double|Oui|Oui|  
|[IDispEventImpl](../atl/reference/idispeventimpl-class.md)|Dispinterface|Non|Oui|  
|[IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Dispinterface|Non|Non|  
  
 \* Lors de l'utilisation de la prise en charge ATL classe, vous n'avez jamais tenus d'implémenter les méthodes d' **IUnknown** ou d' `IDispatch` manuellement.  
  
## Notifier et Unadvising la source d'événements  
 Il existe trois méthodes principales de notifier et d'unadvising une source d'événements à l'aide de ATL.  
  
|Informez la fonction|Fonction d'Unadvise|Le plus approprié pour l'utiliser avec|Requiert soit nécessaire de maintenir un cookie ?|Commentaires|  
|--------------------------|-------------------------|--------------------------------------------|-------------------------------------------------------|------------------|  
|[AtlAdvise](../Topic/AtlAdvise.md), [CComPtrBase::Advise](../Topic/CComPtrBase::Advise.md)|[AtlUnadvise](../Topic/AtlUnadvise.md)|Vtable ou une interface double|Oui|`AtlAdvise` est une fonction globale ATL.  `CComPtrBase::Advise` est utilisé par [CComPtr](../atl/reference/ccomptr-class.md) et [CComQIPtr](../atl/reference/ccomqiptr-class.md).|  
|[IDispEventSimpleImpl::DispEventAdvise](../Topic/IDispEventSimpleImpl::DispEventAdvise.md)|[IDispEventSimpleImpl::DispEventUnadvise](../Topic/IDispEventSimpleImpl::DispEventUnadvise.md)|[IDispEventImpl](../atl/reference/idispeventimpl-class.md) ou [IDispEventSimpleImpl](../atl/reference/idispeventsimpleimpl-class.md)|Non|Moins de paramètres qu' `AtlAdvise` étant donné que la classe de base exécute un travail.|  
|[CComCompositeControl::AdviseSinkMap \(TRUE\)](../Topic/CComCompositeControl::AdviseSinkMap.md)|[CComCompositeControl::AdviseSinkMap FALSE \(\)](../Topic/CComCompositeControl::AdviseSinkMap.md)|Contrôles ActiveX dans des contrôles composites|Non|`CComCompositeControl::AdviseSinkMap` signale toutes le mappage de récepteur d'entrées dans le.  Les mêmes s'exécutent des unadvises les entrées.  Cette méthode est appelée automatiquement par la classe d' `CComCompositeControl` .|  
|[CAxDialogImpl::AdviseSinkMap \(TRUE\)](../Topic/CAxDialogImpl::AdviseSinkMap.md)|[CAxDialogImpl::AdviseSinkMap FALSE \(\)](../Topic/CAxDialogImpl::AdviseSinkMap.md)|Contrôles ActiveX dans une boîte de dialogue|Non|`CAxDialogImpl::AdviseSinkMap` avertit et des unadvises tous les contrôles ActiveX dans la ressource de boîte de dialogue.  Cela se fait automatiquement pour vous.|  
  
## Voir aussi  
 [Gestion des événements](../atl/event-handling-and-atl.md)   
 [Supporting IDispEventImpl](../atl/supporting-idispeventimpl.md)