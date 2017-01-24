---
title: "CComObjectGlobal Class | Microsoft Docs"
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
  - "CComObjectGlobal"
  - "ATL::CComObjectGlobal<Base>"
  - "ATL::CComObjectGlobal"
  - "ATL.CComObjectGlobal"
  - "ATL.CComObjectGlobal<Base>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectGlobal class"
ms.assetid: 79bdee55-66e4-4536-b5b3-bdf09f78b9a6
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComObjectGlobal Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe gère un décompte de références du package contenant votre objet d' `Base` .  
  
## Syntaxe  
  
```  
  
      template<  
   class Base   
>  
class CComObjectGlobal :  
   public Base  
```  
  
#### Paramètres  
 `Base`  
 Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que d'une autre interface vous souhaitez prendre en charge sur l'objet.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComObjectGlobal::CComObjectGlobal](../Topic/CComObjectGlobal::CComObjectGlobal.md)|Constructeur.|  
|[CComObjectGlobal::~CComObjectGlobal](../Topic/CComObjectGlobal::~CComObjectGlobal.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComObjectGlobal::AddRef](../Topic/CComObjectGlobal::AddRef.md)|Implémente `AddRef`global.|  
|[CComObjectGlobal::QueryInterface](../Topic/CComObjectGlobal::QueryInterface.md)|Implémente `QueryInterface`global.|  
|[CComObjectGlobal::Release](../Topic/CComObjectGlobal::Release.md)|Implémente **Release**global.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComObjectGlobal::m\_hResFinalConstruct](../Topic/CComObjectGlobal::m_hResFinalConstruct.md)|Contient **HRESULT** retourné pendant la construction de l'objet d' `CComObjectGlobal` .|  
  
## Notes  
 `CComObjectGlobal` gère un décompte de références du package contenant votre objet d' `Base` .  `CComObjectGlobal` garantit l'objet ne sera pas supprimé tant que le module n'est pas libéré.  Votre objet ne sera supprimé lorsque le décompte de références du module entier accède à zéro.  
  
 Par exemple, l'utilisation `CComObjectGlobal`, une fabrique de classe peut contenir un objet global\) qui est partagé par tous ses clients.  
  
## Hiérarchie d'héritage  
 `Base`  
  
 `CComObjectGlobal`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComObjectStack Class](../../atl/reference/ccomobjectstack-class.md)   
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)