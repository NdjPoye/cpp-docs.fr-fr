---
title: "CComAggObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComAggObject<contained>"
  - "ATL.CComAggObject"
  - "ATL.CComAggObject<contained>"
  - "CComAggObject"
  - "ATL::CComAggObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], dans ATL"
  - "aggregation [C++], objets ATL"
  - "CComAggObject class"
ms.assetid: 7aa90d69-d399-477b-880d-e2cdf0ef7881
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CComAggObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente l'interface d' [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) pour un objet regroupé en agrégats.  Par définition, un objet regroupé en agrégats est contenu dans un objet externe.  La classe d' `CComAggObject` est semblable à [CComObject Class](../../atl/reference/ccomobject-class.md), excepté qu'elle expose une interface qui est directement accessible aux clients externes.  
  
## Syntaxe  
  
```  
  
      template<  
   class contained  
>  
class CComAggObject :  
   public IUnknown, public CComObjectRootEx  
   < contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### Paramètres  
 `contained`  
 Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que de toutes les autres interfaces vous souhaitez prendre en charge sur l'objet.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComAggObject::CComAggObject](../Topic/CComAggObject::CComAggObject.md)|Constructeur.|  
|[CComAggObject::~CComAggObject](../Topic/CComAggObject::~CComAggObject.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComAggObject::AddRef](../Topic/CComAggObject::AddRef.md)|Incrémente le décompte de références sur l'objet regroupé en agrégats.|  
|[CComAggObject::CreateInstance](../Topic/CComAggObject::CreateInstance.md)|Cette fonction statique vous permet de créer un objet de **CComAggObject\<** `contained`**\>** sans la charge de [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComAggObject::FinalConstruct](../Topic/CComAggObject::FinalConstruct.md)|Exécute l'initialisation finale d' `m_contained`.|  
|[CComAggObject::FinalRelease](../Topic/CComAggObject::FinalRelease.md)|Exécute la destruction finale d' `m_contained`.|  
|[CComAggObject::QueryInterface](../Topic/CComAggObject::QueryInterface.md)|Extrait un pointeur vers l'interface demandée.|  
|[CComAggObject::Release](../Topic/CComAggObject::Release.md)|Décrémente le décompte de références sur l'objet regroupé en agrégats.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComAggObject::m\_contained](../Topic/CComAggObject::m_contained.md)|Appels d' `IUnknown` de délégués à l'inconnu externe.|  
  
## Notes  
 Implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) d'`CComAggObject` pour un objet regroupé en agrégats.  `CComAggObject` possède sa propre interface d' **IUnknown** , séparées de l'interface externe d' **IUnknown** de l'objet, et met à jour son propre décompte de références.  
  
 Pour plus d'informations sur le regroupement, consultez l'article [Notions de base des objets COM ATL](../../atl/fundamentals-of-atl-com-objects.md).  
  
## Hiérarchie d'héritage  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComAggObject`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)   
 [DECLARE\_ONLY\_AGGREGATABLE](../Topic/DECLARE_ONLY_AGGREGATABLE.md)   
 [DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)