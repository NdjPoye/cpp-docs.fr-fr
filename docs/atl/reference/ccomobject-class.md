---
title: "CComObject Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComObject<Base>"
  - "ATL::CComObject"
  - "ATL::CComObject<Base>"
  - "ATL.CComObject"
  - "CComObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObject class"
ms.assetid: e2b6433b-6349-4749-b4bc-acbd7a22c8b0
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** pour un objet non regroupé en agrégats.  
  
## Syntaxe  
  
```  
  
      template<  
   class Base   
>  
class CComObject :  
   public Base  
```  
  
#### Paramètres  
 `Base`  
 Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que de toutes les autres interfaces vous souhaitez prendre en charge sur l'objet.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComObject::CComObject](../Topic/CComObject::CComObject.md)|Constructeur.|  
|[CComObject::~CComObject](../Topic/CComObject::~CComObject.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComObject::AddRef](../Topic/CComObject::AddRef.md)|Incrémente le décompte de références à l'objet.|  
|[CComObject::CreateInstance](../Topic/CComObject::CreateInstance.md)|\(Statique\) crée un nouvel objet d' `CComObject` .|  
|[CComObject::QueryInterface](../Topic/CComObject::QueryInterface.md)|Extrait un pointeur vers l'interface demandée.|  
|[CComObject::Release](../Topic/CComObject::Release.md)|Décrémente le décompte de références à l'objet.|  
  
## Notes  
 Implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) d'`CComObject` pour un objet non regroupé en agrégats.  Toutefois, les appels à `QueryInterface`, à `AddRef`, et à **Release** sont délégués à `CComObjectRootEx`.  
  
 Pour plus d'informations sur l'utilisation `CComObject`, consultez l'article [Notions de base des objets COM ATL](../../atl/fundamentals-of-atl-com-objects.md).  
  
## Hiérarchie d'héritage  
 `Base`  
  
 `CComObject`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md)   
 [DECLARE\_NOT\_AGGREGATABLE](../Topic/DECLARE_NOT_AGGREGATABLE.md)   
 [Class Overview](../../atl/atl-class-overview.md)