---
title: "COM Map Macros | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces COM, COM map macros"
ms.assetid: 0f33656d-321f-4996-90cc-9a7f21ab73c3
caps.latest.revision: 16
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COM Map Macros
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ces macros définissent les mappages d'interface COM.  
  
|||  
|-|-|  
|[BEGIN\_COM\_MAP](../Topic/BEGIN_COM_MAP.md)|Marque le début des entrées de mappage d'interfaces COM.|  
|[COM\_INTERFACE\_ENTRY](../Topic/COM_INTERFACE_ENTRY%20Macros.md)|Écrit des interfaces dans le mappage d'interfaces COM.|  
|[COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md)|Utilisez cette macro pour supprimer l'ambiguïté deux branches d'héritage.|  
|[COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md)|Utilisez cette macro pour écrire l'interface dans le mappage COM et pour spécifier son IID.|  
|[COM\_INTERFACE\_ENTRY2\_IID](../Topic/COM_INTERFACE_ENTRY2_IID.md)|Mêmes que [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md), à moins que vous puissiez spécifier un IID différent.|  
|[COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md)|Lorsque l'interface identifiée par `iid` est interrogé pour, `COM_INTERFACE_ENTRY_AGGREGATE` transféré à `punk`.|  
|[COM\_INTERFACE\_ENTRY\_AGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AGGREGATE_BLIND.md)|Même que [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md), sauf que recherchant tout IID une en effectuant le suivi de la requête à `punk`.|  
|[COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE.md)|Mêmes que [COM\_INTERFACE\_ENTRY\_AGGREGATE](../Topic/COM_INTERFACE_ENTRY_AGGREGATE.md), sauf si `punk` est **NULL**, il crée automatiquement l'agrégat décrit par `clsid`.|  
|[COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE\_BLIND](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE_BLIND.md)|Même que [COM\_INTERFACE\_ENTRY\_AUTOAGGREGATE](../Topic/COM_INTERFACE_ENTRY_AUTOAGGREGATE.md), sauf que recherchant tout IID une en effectuant le suivi de la requête à `punk`, et si `punk` est **NULL**, créant automatiquement l'agrégat décrit par `clsid`.|  
|[COM\_INTERFACE\_ENTRY\_BREAK](../Topic/COM_INTERFACE_ENTRY_BREAK.md)|Faite pour appeler votre programme [DebugBreak](http://msdn.microsoft.com/library/windows/desktop/ms679297) lorsque l'interface spécifiée est interrogé pour.|  
|[COM\_INTERFACE\_ENTRY\_CACHED\_TEAR\_OFF](../Topic/COM_INTERFACE_ENTRY_CACHED_TEAR_OFF.md)|Enregistre les données d'interface spécifique pour chaque instance.|  
|[COM\_INTERFACE\_ENTRY\_TEAR\_OFF](../Topic/COM_INTERFACE_ENTRY_TEAR_OFF.md)|Expose les interfaces volantes.|  
|[COM\_INTERFACE\_ENTRY\_CHAIN](../Topic/COM_INTERFACE_ENTRY_CHAIN.md)|Traite le mappage COM de la classe de base lorsque le traitement atteint cette entrée dans le mappage COM.|  
|[COM\_INTERFACE\_ENTRY\_FUNC](../Topic/COM_INTERFACE_ENTRY_FUNC.md)|Un mécanisme général pour raccorder dans `QueryInterface` ATL la logique.|  
|[COM\_INTERFACE\_ENTRY\_FUNC\_BLIND](../Topic/COM_INTERFACE_ENTRY_FUNC_BLIND.md)|Mêmes que [COM\_INTERFACE\_ENTRY\_FUNC](../Topic/COM_INTERFACE_ENTRY_FUNC.md), sauf que recherchant tous résultats de l'IID dans un appel à `func`.|  
|[COM\_INTERFACE\_ENTRY\_NOINTERFACE](../Topic/COM_INTERFACE_ENTRY_NOINTERFACE.md)|Retourne **E\_NOINTERFACE** et se termine le mappage COM traitement lorsque l'interface spécifiée est interrogé pour.|  
|[END\_COM\_MAP](../Topic/END_COM_MAP.md)|Marque la fin des entrées de mappage d'interfaces COM.|  
  
## Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)   
 [COM Map Global Functions](../../atl/reference/com-map-global-functions.md)