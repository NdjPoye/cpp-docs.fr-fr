---
title: "CFirePropNotifyEvent Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFirePropNotifyEvent"
  - "ATL::CFirePropNotifyEvent"
  - "ATL.CFirePropNotifyEvent"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFirePropNotifyEvent class"
  - "points de connexion (C++), notifying of events"
  - "sinks, notifying of ATL events"
ms.assetid: eb7a563e-6bce-4cdf-8d20-8c6a5307781b
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CFirePropNotifyEvent Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes pour notifier le récepteur du conteneur concernant les modifications de propriété de contrôle.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
class CFirePropNotifyEvent  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFirePropNotifyEvent::FireOnChanged](../Topic/CFirePropNotifyEvent::FireOnChanged.md)|\(Statique\) informe le récepteur du conteneur qu'une propriété du contrôle a changé.|  
|[CFirePropNotifyEvent::FireOnRequestEdit](../Topic/CFirePropNotifyEvent::FireOnRequestEdit.md)|\(Statique\) informe le récepteur du conteneur qu'une propriété de contrôle est sur le point de modifier.|  
  
## Notes  
 `CFirePropNotifyEvent` a deux méthodes qui informent le récepteur du conteneur qu'une propriété du contrôle a changé ou est sur le point de modifier.  
  
 Si la classe implémentant votre contrôle est dérivée d' `IPropertyNotifySink`, les méthodes d' `CFirePropNotifyEvent` sont appelées lorsque vous appelez `FireOnRequestEdit` ou `FireOnChanged`.  Si votre classe de contrôle n'est pas dérivée d' `IPropertyNotifySink`, les appels à ces fonctions `S_OK`de retour.  
  
 Pour plus d'informations sur la création de contrôles, consultez [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md).  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)