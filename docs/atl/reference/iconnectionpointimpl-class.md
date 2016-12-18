---
title: "IConnectionPointImpl Class | Microsoft Docs"
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
  - "ATL.IConnectionPointImpl"
  - "IConnectionPointImpl"
  - "ATL::IConnectionPointImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "points de connexion (C++), implémenter"
  - "IConnectionPointImpl class"
ms.assetid: 27992115-3b86-45dd-bc9e-54f32876c557
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IConnectionPointImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente un point de connexion.  
  
## Syntaxe  
  
```  
  
      template<  
   class T,  
   const IID* piid,  
   class CDV = CComDynamicUnkArray   
>  
class ATL_NO_VTABLE IConnectionPointImpl :  
   public _ICPLocator< piid >  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IConnectionPointImpl`.  
  
 `piid`  
 Pointeur vers l'IID de l'interface représentée par l'objet de point de connexion.  
  
 `CDV`  
 Une classe qui gère les connexions.  La valeur par défaut est [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), qui autorise les connexions illimitées.  Vous pouvez également utiliser [CComUnkArray](../../atl/reference/ccomunkarray-class.md), qui spécifie un nombre fixe de connexions.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IConnectionPointImpl::Advise](../Topic/IConnectionPointImpl::Advise.md)|Établit une connexion entre le point de connexion et un récepteur.|  
|[IConnectionPointImpl::EnumConnections](../Topic/IConnectionPointImpl::EnumConnections.md)|Crée un énumérateur pour itérer au sein de les plug\-ins pour le point de connexion.|  
|[IConnectionPointImpl::GetConnectionInterface](../Topic/IConnectionPointImpl::GetConnectionInterface.md)|Extrait l'IID de l'interface représentée par le point de connexion.|  
|[IConnectionPointImpl::GetConnectionPointContainer](../Topic/IConnectionPointImpl::GetConnectionPointContainer.md)|Extrait un pointeur d'interface vers l'objet connectable.|  
|[IConnectionPointImpl::Unadvise](../Topic/IConnectionPointImpl::Unadvise.md)|Termine une connexion créée précédemment dans `Advise`.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IConnectionPointImpl::m\_vec](../Topic/IConnectionPointImpl::m_vec.md)|Gère les plug\-ins pour le point de connexion.|  
  
## Notes  
 `IConnectionPointImpl` implémente un point de connexion, qui permet à un objet d'exposer une interface sortante vers le client.  Le client implémente cette interface sur un objet appelé un récepteur.  
  
 ATL utilise [IConnectionPointContainerImpl](../../atl/reference/iconnectionpointcontainerimpl-class.md) pour implémenter l'objet connectable.  Chaque point de connexion dans l'objet connectable représente une interface sortante, identifiée par `piid`.  La classe *CDV* gère les connexions entre le point de connexion et un récepteur.  Chaque connexion est identifiée par un cookie « . »  
  
 Pour plus d'informations sur l'utilisation de points de connexion dans ATL, consultez l'article [points de connexion](../../atl/atl-connection-points.md).  
  
## Hiérarchie d'héritage  
 `_ICPLocator`  
  
 `IConnectionPointImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318)   
 [Class Overview](../../atl/atl-class-overview.md)