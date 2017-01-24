---
title: "IPersistStorageImpl Class | Microsoft Docs"
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
  - "ATL::IPersistStorageImpl"
  - "ATL::IPersistStorageImpl<T>"
  - "ATL.IPersistStorageImpl<T>"
  - "IPersistStorageImpl"
  - "ATL.IPersistStorageImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistStorageImpl class"
  - "stockage, ATL"
ms.assetid: d652f02c-239c-47c7-9a50-3e9fc3014fff
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPersistStorageImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente l'interface d' [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template <  
class T  
>  
class ATL_NO_VTABLE IPersistStorageImpl :  
public IPersistStorage  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IPersistStorageImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IPersistStorageImpl::GetClassID](../Topic/IPersistStorageImpl::GetClassID.md)|Récupère le CLSID de l'objet.|  
|[IPersistStorageImpl::HandsOffStorage](../Topic/IPersistStorageImpl::HandsOffStorage.md)|Demande à l'objet pour libérer tous les objets de stockage et pour déplacer le mode de HandsOff.  L'implémentation ATL retourne `S_OK`.|  
|[IPersistStorageImpl::InitNew](../Topic/IPersistStorageImpl::InitNew.md)|Initialise une nouvelle mémoire.|  
|[IPersistStorageImpl::IsDirty](../Topic/IPersistStorageImpl::IsDirty.md)|Vérifie si les données de l'objet ont changé depuis qu'elles étaient pour la dernière fois enregistrées.|  
|[IPersistStorageImpl::Load](../Topic/IPersistStorageImpl::Load.md)|Charge les propriétés de l'objet de la mémoire spécifiée.|  
|[IPersistStorageImpl::Save](../Topic/IPersistStorageImpl::Save.md)|Enregistre les propriétés de l'objet à la mémoire spécifiée.|  
|[IPersistStorageImpl::SaveCompleted](../Topic/IPersistStorageImpl::SaveCompleted.md)|Avertit un objet qu'il peut revenir au mode normal pour écrire dans son objet de stockage.  L'implémentation ATL retourne `S_OK`.|  
  
## Notes  
 `IPersistStorageImpl` implémente l'interface d' [IPersistStorage](http://msdn.microsoft.com/library/windows/desktop/ms679731) , qui permet à un client pour demander que le chargement d'objet et enregistrer ses données persistantes dans un magasin.  
  
 L'implémentation de cette classe requiert une classe `T` de faire une implémentation de l'interface d' `IPersistStreamInit` disponible via `QueryInterface`.  En général cela signifie que la classe `T` doit dériver d' [IPersistStreamInitImpl](../../atl/reference/ipersiststreaminitimpl-class.md), fournir une entrée pour `IPersistStreamInit` dans [mappage COM](../Topic/BEGIN_COM_MAP.md), et utiliser [mappage de propriété](../Topic/BEGIN_PROP_MAP.md) pour décrire les données persistantes de la classe.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IPersistStorage`  
  
 `IPersistStorageImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [Storages and Streams](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [IPersistStreamInitImpl Class](../../atl/reference/ipersiststreaminitimpl-class.md)   
 [IPersistPropertyBagImpl Class](../../atl/reference/ipersistpropertybagimpl-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)