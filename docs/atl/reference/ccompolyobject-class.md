---
title: "CComPolyObject Class | Microsoft Docs"
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
  - "CComPolyObject"
  - "ATL.CComPolyObject<contained>"
  - "ATL::CComPolyObject"
  - "ATL::CComPolyObject<contained>"
  - "ATL.CComPolyObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], dans ATL"
  - "aggregation [C++], objets ATL"
  - "CComPolyObject class"
ms.assetid: eaf67c18-e855-48ca-9b15-f1df3106121b
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComPolyObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** pour un objet de synthèse ou non regroupé en agrégats.  
  
## Syntaxe  
  
```  
  
      template<  
   class contained   
>  
class CComPolyObject : public IUnknown, public CComObjectRootEx  
   < contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### Paramètres  
 `contained`  
 Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que de toutes les autres interfaces vous souhaitez prendre en charge sur l'objet.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComPolyObject::CComPolyObject](../Topic/CComPolyObject::CComPolyObject.md)|Constructeur.|  
|[CComPolyObject::~CComPolyObject](../Topic/CComPolyObject::~CComPolyObject.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComPolyObject::AddRef](../Topic/CComPolyObject::AddRef.md)|Incrémente le décompte de références de l'objet.|  
|[CComPolyObject::CreateInstance](../Topic/CComPolyObject::CreateInstance.md)|\(Statique\) vous permet de créer un objet de **CComPolyObject\<** `contained`**\>** sans la charge de [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615).|  
|[CComPolyObject::FinalConstruct](../Topic/CComPolyObject::FinalConstruct.md)|Exécute l'initialisation finale d' `m_contained`.|  
|[CComPolyObject::FinalRelease](../Topic/CComPolyObject::FinalRelease.md)|Exécute la destruction finale d' `m_contained`.|  
|[CComPolyObject::QueryInterface](../Topic/CComPolyObject::QueryInterface.md)|Extrait un pointeur vers l'interface demandée.|  
|[CComPolyObject::Release](../Topic/CComPolyObject::Release.md)|Décrémente le décompte de références de l'objet.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComPolyObject::m\_contained](../Topic/CComPolyObject::m_contained.md)|Appels d' **IUnknown** de délégués à l'inconnu externe si l'objet est regroupé ou à **IUnknown** de l'objet si l'objet n'est pas regroupé.|  
  
## Notes  
 `CComPolyObject` implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) pour un objet de synthèse ou non regroupé en agrégats.  
  
 Lorsqu'une instance d' `CComPolyObject` est créée, la valeur de l'inconnu externe est activée.  Si c'est **NULL**, **IUnknown** est implémenté pour un objet non regroupé en agrégats.  Si l'inconnu externe n'est pas **NULL**, **IUnknown** est implémenté pour un objet regroupé en agrégats.  
  
 l'avantage d'utiliser `CComPolyObject` est que vous évitez d'avoir [CComAggObject](../../atl/reference/ccomaggobject-class.md) et [CComObject](../../atl/reference/ccomobject-class.md) dans votre module pour traiter les cas de synthèse et non regroupés en agrégats.  Handles d'objet unique d' `CComPolyObject` les deux cas.  Cela signifie qu'une copie du pointeur vtable et une copie des fonctions existent dans votre package.  Si votre pointeur vtable est important, cela peut considérablement réduire la taille du module.  Toutefois, si votre pointeur vtable est petite, à l'aide de `CComPolyObject` peuvent entraîner une taille légèrement plus grande de module car elle n'est pas optimisée pour un objet de synthèse ou non regroupé en agrégats, de même qu' `CComAggObject` et `CComObject`.  
  
 Si la macro d' `DECLARE_POLY_AGGREGATABLE` spécifiée dans la définition de classe de votre objet, `CComPolyObject` sera utilisé pour créer votre objet.  `DECLARE_POLY_AGGREGATABLE` sera automatiquement déclaré si vous utilisez l'Assistant Projet ATL pour créer un contrôle total ou un contrôle d'Internet Explorer.  
  
 Si regroupé, l'objet d' `CComPolyObject` a son propre **IUnknown**, distinct d' **IUnknown**externe de l'objet, et met à jour son propre décompte de références.  `CComPolyObject` utilise [CComContainedObject](../../atl/reference/ccomcontainedobject-class.md) pour le déléguer à l'inconnu externe.  
  
 Pour plus d'informations sur le regroupement, consultez l'article [Notions de base des objets COM ATL](../../atl/fundamentals-of-atl-com-objects.md).  
  
## Hiérarchie d'héritage  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComPolyObject`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)