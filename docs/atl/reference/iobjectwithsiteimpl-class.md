---
title: "IObjectWithSiteImpl Class | Microsoft Docs"
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
  - "ATL::IObjectWithSiteImpl"
  - "ATL.IObjectWithSiteImpl<T>"
  - "IObjectWithSiteImpl"
  - "ATL.IObjectWithSiteImpl"
  - "ATL::IObjectWithSiteImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IObjectWithSiteImpl class"
ms.assetid: 4e1f774f-bc3d-45ee-9a1c-c3533a511588
caps.latest.revision: 18
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IObjectWithSiteImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes permettant à un objet pour communiquer avec son site.  
  
## Syntaxe  
  
```  
  
      template<  
   class T   
>  
class ATL_NO_VTABLE IObjectWithSiteImpl :  
   public IObjectWithSite  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IObjectWithSiteImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IObjectWithSiteImpl::GetSite](../Topic/IObjectWithSiteImpl::GetSite.md)|Interroge le site pour un pointeur d'interface.|  
|[IObjectWithSiteImpl::SetChildSite](../Topic/IObjectWithSiteImpl::SetChildSite.md)|Fournit à l'objet le pointeur d' **IUnknown** du site.|  
|[IObjectWithSiteImpl::SetSite](../Topic/IObjectWithSiteImpl::SetSite.md)|Fournit à l'objet le pointeur d' **IUnknown** du site.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IObjectWithSiteImpl::m\_spUnkSite](../Topic/IObjectWithSiteImpl::m_spUnkSite.md)|Gère le pointeur d' **IUnknown** du site.|  
  
## Notes  
 l'interface d' [IObjectWithSite](http://msdn.microsoft.com/library/windows/desktop/ms693765) permet à un objet pour communiquer avec son site.  La classe `IObjectWithSiteImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
 `IObjectWithSiteImpl` spécifie deux méthodes.  Cliente appelle `SetSite`d'abord, en passant le pointeur d' **IUnknown** du site.  Ce pointeur est stocké dans l'objet, et peut ensuite être récupéré via un appel à `GetSite`.  
  
 En général, vous dérivez votre classe d' `IObjectWithSiteImpl` lorsque vous créez un objet qui n'est pas un contrôle.  Pour les contrôles, dérivez votre classe d' [IOleObjectImpl](../../atl/reference/ioleobjectimpl-class.md), qui fournit également un pointeur de site.  Ne dérivent pas de votre classe d' `IObjectWithSiteImpl` et d' `IOleObjectImpl`.  
  
## Hiérarchie d'héritage  
 `IObjectWithSite`  
  
 `IObjectWithSiteImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)