---
title: "IPersistStreamInitImpl Class | Microsoft Docs"
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
  - "ATL::IPersistStreamInitImpl"
  - "ATL::IPersistStreamInitImpl<T>"
  - "ATL.IPersistStreamInitImpl<T>"
  - "IPersistStreamInitImpl"
  - "ATL.IPersistStreamInitImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IPersistStreamInit ATL implementation"
  - "IPersistStreamInitImpl class"
  - "flux, ATL"
ms.assetid: ef217c3c-020f-4cf8-871e-ef68e57865b8
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IPersistStreamInitImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** et fournit une implémentation par défaut de l'interface d' [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) .  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
## Syntaxe  
  
```  
  
      template<  
class T   
>  
class ATL_NO_VTABLE IPersistStreamInitImpl :  
public IPersistStreamInit  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IPersistStreamInitImpl`.  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[IPersistStreamInitImpl::GetClassID](../Topic/IPersistStreamInitImpl::GetClassID.md)|Récupère le CLSID de l'objet.|  
|[IPersistStreamInitImpl::GetSizeMax](../Topic/IPersistStreamInitImpl::GetSizeMax.md)|Extrait la taille du flux nécessaire pour enregistrer les données de l'objet.  L'implémentation ATL retourne **E\_NOTIMPL**.|  
|[IPersistStreamInitImpl::InitNew](../Topic/IPersistStreamInitImpl::InitNew.md)|Initialise un objet nouvellement créée.|  
|[IPersistStreamInitImpl::IsDirty](../Topic/IPersistStreamInitImpl::IsDirty.md)|Vérifie si les données de l'objet ont changé depuis qu'elles étaient pour la dernière fois enregistrées.|  
|[IPersistStreamInitImpl::Load](../Topic/IPersistStreamInitImpl::Load.md)|Charge les propriétés de l'objet de flux spécifié.|  
|[IPersistStreamInitImpl::Save](../Topic/IPersistStreamInitImpl::Save.md)|Enregistre les propriétés de l'objet dans le flux de données spécifié.|  
  
## Notes  
 L'interface d' [IPersistStreamInit](http://msdn.microsoft.com/library/windows/desktop/ms682273) permet à un client pour demander que votre objet charge et enregistre ses données persistantes dans un flux unique.  La classe `IPersistStreamInitImpl` fournit une implémentation par défaut de cette interface et implémente **IUnknown** en envoyant des informations à l'unité de vidage dans les versions debug.  
  
 **Articles connexes** [Didacticiel ATL](../../atl/active-template-library-atl-tutorial.md), [créer un projet ATL](../../atl/reference/creating-an-atl-project.md)  
  
## Hiérarchie d'héritage  
 `IPersistStreamInit`  
  
 `IPersistStreamInitImpl`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [Storages and Streams](http://msdn.microsoft.com/library/windows/desktop/aa380352)   
 [Class Overview](../../atl/atl-class-overview.md)