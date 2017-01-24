---
title: "CComContainedObject Class | Microsoft Docs"
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
  - "CComContainedObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregate objects [C++], dans ATL"
  - "aggregation [C++], objets ATL"
  - "CComContainedObject class"
ms.assetid: e8616b41-c200-47b8-bf2c-fb9f713ebdad
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComContainedObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) en déléguant à **IUnknown**de l'objet propriétaire.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peuvent pas être utilisés dans les applications qui s'exécutent dans les fenêtres d'exécution.  
  
## Syntaxe  
  
```  
  
      template<  
class Base   
>  
class CComContainedObject :  
public Base  
```  
  
#### Paramètres  
 `Base`  
 Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComContainedObject::CComContainedObject](../Topic/CComContainedObject::CComContainedObject.md)|Constructeur.  Initialise le pointeur de membre à `IUnknown`de l'objet propriétaire.|  
|[CComContainedObject::~CComContainedObject](../Topic/CComContainedObject::~CComContainedObject.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComContainedObject::AddRef](../Topic/CComContainedObject::AddRef.md)|Incrémente le décompte de références sur l'objet propriétaire.|  
|[CComContainedObject::GetControllingUnknown](../Topic/CComContainedObject::GetControllingUnknown.md)|Récupère `IUnknown`de l'objet propriétaire.|  
|[CComContainedObject::QueryInterface](../Topic/CComContainedObject::QueryInterface.md)|Extrait un pointeur vers l'interface demandée sur l'objet propriétaire.|  
|[CComContainedObject::Release](../Topic/CComContainedObject::Release.md)|Décrémente le décompte de références sur l'objet propriétaire.|  
  
## Notes  
 ATL utilise `CComContainedObject` dans les classes [CComAggObject](../../atl/reference/ccomaggobject-class.md), [CComPolyObject](../../atl/reference/ccompolyobject-class.md), et [CComCachedTearOffObject](../../atl/reference/ccomcachedtearoffobject-class.md).  `CComContainedObject` implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) en déléguant à **IUnknown**de l'objet propriétaire.  \(Le propriétaire est l'objet externe d'un regroupement, ou l'objet pour lequel une interface volante est créé.\) `CComContainedObject` appelle `OuterQueryInterface`, `OuterAddRef`, et `OuterRelease`d'`CComObjectRootEx`, tout hérité par `Base`.  
  
## Hiérarchie d'héritage  
 `Base`  
  
 `CComContainedObject`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)