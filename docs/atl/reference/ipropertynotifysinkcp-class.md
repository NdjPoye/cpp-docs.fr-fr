---
title: "IPropertyNotifySinkCP Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPropertyNotifySinkCP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "points de connexion (C++), gérer"
  - "IPropertyNotifySinkCP class"
  - "sinks, notifying of changes"
ms.assetid: 1b41445e-bc88-4fa6-bb62-d68aacec2bd5
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# IPropertyNotifySinkCP Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe expose l'interface d' [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) comme interface sortante sur un objet connectable.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template< class   
      T  
      , class  
      CDV   
      = CComDynamicUnkArray >  
class IPropertyNotifySinkCP :   
public IConnectionPointImpl< T, &IID_IPropertyNotifySink, CDV>  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IPropertyNotifySinkCP`.  
  
 `CDV`  
 Une classe qui gère les connexions entre un point de connexion et les récepteurs.  La valeur par défaut est [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md), qui autorise les connexions illimitées.  Vous pouvez également utiliser [CComUnkArray](../../atl/reference/ccomunkarray-class.md), qui spécifie un nombre fixe de connexions.  
  
## Notes  
 `IPropertyNotifySinkCP` hérite de toutes les méthodes de sa classe de base, [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md).  
  
 L'interface d' [IPropertyNotifySink](http://msdn.microsoft.com/library/windows/desktop/ms692638) permet à un objet sink pour recevoir des notifications sur les modifications de propriété.  La classe expose `IPropertyNotifySinkCP` cette interface en tant qu'interface sortante sur un objet connectable.  Le client doit implémenter les méthodes d' `IPropertyNotifySink` sur le récepteur.  
  
 Dérivez votre classe d' `IPropertyNotifySinkCP` lorsque vous souhaitez créer un point de connexion qui représente l'interface d' `IPropertyNotifySink` .  
  
 Pour plus d'informations sur l'utilisation de points de connexion dans ATL, consultez l'article [points de connexion](../../atl/atl-connection-points.md).  
  
## Configuration requise  
 **Header:** atlctl.h  
  
## Voir aussi  
 [IConnectionPointImpl Class](../../atl/reference/iconnectionpointimpl-class.md)   
 [IConnectionPointContainerImpl Class](../../atl/reference/iconnectionpointcontainerimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)