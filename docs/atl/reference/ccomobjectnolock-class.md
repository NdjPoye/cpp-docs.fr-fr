---
title: "CComObjectNoLock Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL.CComObjectNoLock"
  - "ATL::CComObjectNoLock"
  - "ATL.CComObjectNoLock<Base>"
  - "CComObjectNoLock"
  - "ATL::CComObjectNoLock<Base>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectNoLock class"
ms.assetid: 288c6506-7da8-4127-8d58-7f4bd779539a
caps.latest.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CComObjectNoLock Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente **IUnknown** pour un objet non regroupé en agrégats, mais n'incrémente pas le nombre de verrous sur le module dans le constructeur.  
  
## Syntaxe  
  
```  
  
      template<  
   class Base   
>  
class CComObjectNoLock :  
   public Base  
```  
  
#### Paramètres  
 `Base`  
 Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que d'une autre interface vous souhaitez prendre en charge sur l'objet.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComObjectNoLock::CComObjectNoLock](../Topic/CComObjectNoLock::CComObjectNoLock.md)|Constructeur.|  
|[CComObjectNoLock::~CComObjectNoLock](../Topic/CComObjectNoLock::~CComObjectNoLock.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComObjectNoLock::AddRef](../Topic/CComObjectNoLock::AddRef.md)|Incrémente le décompte de références à l'objet.|  
|[CComObjectNoLock::QueryInterface](../Topic/CComObjectNoLock::QueryInterface.md)|Retourne un pointeur vers l'interface demandée.|  
|[CComObjectNoLock::Release](../Topic/CComObjectNoLock::Release.md)|Décrémente le décompte de références à l'objet.|  
  
## Notes  
 `CComObjectNoLock` est semblable à [CComObject](../../atl/reference/ccomobject-class.md) car il implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) pour un objet non regroupé en agrégats ; toutefois, `CComObjectNoLock` n'incrémente pas le nombre de verrous sur le module dans le constructeur.  
  
 Utilise `CComObjectNoLock` ATL en interne pour les fabriques de classe.  En général vous n'utiliserez pas cette classe directement.  
  
## Hiérarchie d'héritage  
 `Base`  
  
 `CComObjectNoLock`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [Class Overview](../../atl/atl-class-overview.md)