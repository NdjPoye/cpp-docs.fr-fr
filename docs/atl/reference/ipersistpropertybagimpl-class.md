---
title: "IPersistPropertyBagImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "IPersistPropertyBagImpl"
  - "ATL.IPersistPropertyBagImpl<T>"
  - "ATL::IPersistPropertyBagImpl"
  - "ATL::IPersistPropertyBagImpl<T>"
  - "ATL.IPersistPropertyBagImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistPropertyBagImpl class"
ms.assetid: 712af24d-99f8-40f2-9811-53b3ff6e5b19
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPersistPropertyBagImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** et permet à un objet pour enregistrer ses propriétés dans un conteneur des propriétés client fourni.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template <   
class T   
>  
class ATL_NO_VTABLE IPersistPropertyBagImpl :  
public IPersistPropertyBag  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IPersistPropertyBagImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IPersistPropertyBagImpl::GetClassID](../Topic/IPersistPropertyBagImpl::GetClassID.md)|Récupère le CLSID de l'objet.|  
|[IPersistPropertyBagImpl::InitNew](../Topic/IPersistPropertyBagImpl::InitNew.md)|Initialise un objet nouvellement créée.  L'implémentation ATL retourne `S_OK`.|  
|[IPersistPropertyBagImpl::Load](../Topic/IPersistPropertyBagImpl::Load.md)|Charge les propriétés de l'objet d'un conteneur de propriétés client fourni.|  
|[IPersistPropertyBagImpl::Save](../Topic/IPersistPropertyBagImpl::Save.md)|Enregistre les propriétés de l'objet dans un conteneur des propriétés client fourni.|  
  
## Notes  
 L'interface d' [IPersistPropertyBag](https://msdn.microsoft.com/en-us/library/aa768205.aspx) permet à un objet pour enregistrer ses propriétés dans un conteneur des propriétés client fourni.  La classe `IPersistPropertyBagImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
 **IPersistPropertyBag** fonctionne conjointement avec [IPropertyBag](https://msdn.microsoft.com/en-us/library/aa768196.aspx) et [IErrorLog](https://msdn.microsoft.com/en-us/library/aa768231.aspx).  Ces deux dernières interfaces doivent être implémentées par le client.  Par `IPropertyBag`, le client enregistre et charge les propriétés de l'objet.  Par **IErrorLog**, l'objet et le client peut signaler toutes les erreurs rencontrées.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IPersistPropertyBag`  
  
 `IPersistPropertyBagImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [BEGIN\_PROP\_MAP](../Topic/BEGIN_PROP_MAP.md)   
 [Class Overview](../../atl/atl-class-overview.md)