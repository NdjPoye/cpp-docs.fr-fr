---
title: "IConnectionPointContainerImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::IConnectionPointContainerImpl"
  - "ATL.IConnectionPointContainerImpl"
  - "ATL.IConnectionPointContainerImpl<T>"
  - "IConnectionPointContainerImpl"
  - "ATL::IConnectionPointContainerImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "connectable objects"
  - "points de connexion (C++), container"
  - "IConnectionPointContainerImpl class"
ms.assetid: 10db5a8d-8be9-4d9d-8a82-8ab9ffe3e9d6
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IConnectionPointContainerImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente un conteneur de point de connexion pour gérer une collection d'objets [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) .  
  
## Syntaxe  
  
```  
  
      template<  
   class T   
>  
class ATL_NO_VTABLE IConnectionPointContainerImpl :   
   public IConnectionPointContainer  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IConnectionPointContainerImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IConnectionPointContainerImpl::EnumConnectionPoints](../Topic/IConnectionPointContainerImpl::EnumConnectionPoints.md)|Crée un énumérateur pour itérer au sein de les points de connexion pris en charge dans l'objet connectable.|  
|[IConnectionPointContainerImpl::FindConnectionPoint](../Topic/IConnectionPointContainerImpl::FindConnectionPoint.md)|Extrait un pointeur d'interface vers le point de connexion qui prend en charge l'IID spécifié.|  
  
## Notes  
 `IConnectionPointContainerImpl` implémente un conteneur de point de connexion pour gérer une collection d'objets [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) .  `IConnectionPointContainerImpl` fournit deux méthodes qu'un client peut appeler pour récupérer des informations supplémentaires sur un objet connectable :  
  
-   `EnumConnectionPoints` permet au client de déterminer les interfaces sortantes l'objet prend en charge.  
  
-   `FindConnectionPoint` permet au client de déterminer si l'objet prend en charge une interface sortante spécifique.  
  
 Pour plus d'informations sur l'utilisation de points de connexion dans ATL, consultez l'article [points de connexion](../../atl/atl-connection-points.md).  
  
## Hiérarchie d'héritage  
 `IConnectionPointContainer`  
  
 `IConnectionPointContainerImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857)   
 [Class Overview](../../atl/atl-class-overview.md)