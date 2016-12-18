---
title: "CComObjectStack Class | Microsoft Docs"
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
  - "ATL::CComObjectStack"
  - "ATL.CComObjectStack"
  - "ATL::CComObjectStack<Base>"
  - "ATL.CComObjectStack<Base>"
  - "CComObjectStack"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectStack class"
ms.assetid: 3da72c40-c834-45f6-bb76-6ac204028d80
caps.latest.revision: 19
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComObjectStack Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe crée un objet COM temporaire et lui fournit une implémentation squelette d' **IUnknown**.  
  
## Syntaxe  
  
```  
  
      template<  
   class Base   
>  
class CComObjectStack :  
   public Base  
```  
  
#### Paramètres  
 `Base`  
 Votre classe, dérivée de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md) ou de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md), ainsi que d'une autre interface vous souhaitez prendre en charge sur l'objet.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComObjectStack::CComObjectStack](../Topic/CComObjectStack::CComObjectStack.md)|Constructeur.|  
|[CComObjectStack::~CComObjectStack](../Topic/CComObjectStack::~CComObjectStack.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComObjectStack::AddRef](../Topic/CComObjectStack::AddRef.md)|Retourne zéro.  En mode débogage, appelle `_ASSERTE`.|  
|[CComObjectStack::QueryInterface](../Topic/CComObjectStack::QueryInterface.md)|Retourne **E\_NOINTERFACE**.  En mode débogage, appelle `_ASSERTE`.|  
|[CComObjectStack::Release](../Topic/CComObjectStack::Release.md)|Retourne zéro.  En mode débogage, appelle `_ASSERTE`.  ~|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComObjectStack::m\_hResFinalConstruct](../Topic/CComObjectStack::m_hResFinalConstruct.md)|Contient **HRESULT** retourné pendant la construction de l'objet d' `CComObjectStack` .|  
  
## Notes  
 `CComObjectStack` est utilisé pour créer un objet COM temporaire et pour fournir l'objet une implémentation squelette d' **IUnknown**.  En général, l'objet est utilisé comme une variable locale à moins d'une fonction \(autrement dit, l'objet d'un push dans la pile\).  Étant donné que l'objet est détruit lorsque la fonction termine, le décompte de références n'est pas effectué pour augmenter l'efficacité.  
  
 L'exemple suivant montre comment créer un objet COM utilisé dans une fonction :  
  
 [!code-cpp[NVC_ATL_COM#42](../../atl/codesnippet/CPP/ccomobjectstack-class_1.cpp)]  
  
 L'objet temporaire `Tempobj` est de type push dans la pile et disparaît automatiquement lorsque la fonction termine.  
  
## Hiérarchie d'héritage  
 `Base`  
  
 `CComObjectStack`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComObjectGlobal Class](../../atl/reference/ccomobjectglobal-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)