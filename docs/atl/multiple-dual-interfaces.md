---
title: "Multiple Dual Interfaces | Microsoft Docs"
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
  - "COM_INTERFACE_ENTRY_IID macro"
  - "COM_INTERFACE_ENTRY2 macro"
  - "interfaces doubles, exposing multiple"
  - "classe IDispatchImpl, multiple dual interfaces"
  - "multiple dual interfaces"
  - "multiple dual interfaces, exposing with ATL"
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Multiple Dual Interfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez combiner les avantages d'une interface double \(autrement dit, la flexibilité de vtable et la liaison tardive, de ce fait de la classe disponible pour les langages de script ainsi qu'à C\+\+\) avec les techniques de l'héritage multiple.  
  
 Bien qu'il soit possible d'exposer plusieurs interfaces doubles sur un seul objet COM, il n'est pas recommandé.  S'il existe plusieurs interfaces doubles, il doit y avoir qu'une interface d' `IDispatch` exposée.  Les techniques disponibles pour garantir que c'est le cas des présentent des pénalités telles que la perte de fonction ou de complexité accrue de code.  Le développeur alors cette approche devez peser attentivement les avantages et les inconvénients.  
  
## Exposer une seule interface IDispatch  
 Il est possible d'exposer plusieurs interfaces doubles sur un objet unique en dérivant de deux spécialisations ou plus d' `IDispatchImpl`.  Toutefois, si vous autorisez les clients à la requête pour l'interface d' `IDispatch` , vous devez utiliser la macro de [COM\_INTERFACE\_ENTRY2](../Topic/COM_INTERFACE_ENTRY2.md) \(ou [COM\_INTERFACE\_ENTRY\_IID](../Topic/COM_INTERFACE_ENTRY_IID.md)\) pour spécifier la classe de base à utiliser pour l'implémentation d' `IDispatch`.  
  
 [!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/CPP/multiple-dual-interfaces_1.h)]  
  
 Étant donné qu'une interface d' `IDispatch` est exposée, les clients qui peuvent uniquement accéder à vos objets via l'interface d' `IDispatch` ne pourront pas accéder aux méthodes ou les propriétés dans aucune autre interface.  
  
## Combiner plusieurs interfaces doubles à une implémentation unique IDispatch  
 ATL ne fournit pas d'assistance de combiner plusieurs interfaces doubles à une implémentation unique d' `IDispatch`.  Toutefois, il existe plusieurs approches à associer manuellement les interfaces, telles que la création d'une classe basée sur un modèle qui contient une union des interfaces distinctes d' `IDispatch` , créant un nouvel objet pour remplir la fonction d' `QueryInterface` , ou l'utilisation d'une implémentation typeinfo\- basée sur des objets imbriqués pour créer l'interface d' `IDispatch` .  
  
 Ces approches ont des problèmes avec des collisions potentielles de l'espace de noms, ainsi que le code de la complexité et la facilité de maintenance.  Il n'est pas recommandé de créer plusieurs interfaces doubles.  
  
## Voir aussi  
 [Dual Interfaces and ATL](../atl/dual-interfaces-and-atl.md)