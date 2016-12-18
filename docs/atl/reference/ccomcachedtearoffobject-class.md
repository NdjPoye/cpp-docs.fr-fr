---
title: "CComCachedTearOffObject Class | Microsoft Docs"
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
  - "ATL::CComCachedTearOffObject"
  - "ATL.CComCachedTearOffObject"
  - "ATL.CComCachedTearOffObject<contained>"
  - "CComCachedTearOffObject"
  - "ATL::CComCachedTearOffObject<contained>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "cache, ATL cached tear-off objects"
  - "CComCachedTearOffObject class"
ms.assetid: ae19507d-a1de-4dbc-a988-da9f75a50c95
caps.latest.revision: 19
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComCachedTearOffObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) pour une interface volante.  
  
## Syntaxe  
  
```  
  
      template <  
   class contained  
>  
class CComCachedTearOffObject : public IUnknown,  
   public CComObjectRootEx< contained::_ThreadModel::ThreadModelNoCS >  
```  
  
#### Paramètres  
 `contained`  
 Votre arrachez la classe, dérivée de `CComTearOffObjectBase` et les interfaces que vous souhaitez que votre arrachent l'objet en charge.  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCachedTearOffObject::CComCachedTearOffObject](../Topic/CComCachedTearOffObject::CComCachedTearOffObject.md)|Constructeur.|  
|[CComCachedTearOffObject::~CComCachedTearOffObject](../Topic/CComCachedTearOffObject::~CComCachedTearOffObject.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCachedTearOffObject::AddRef](../Topic/CComCachedTearOffObject::AddRef.md)|Incrémente le décompte de références d'un objet d' `CComCachedTearOffObject` .|  
|[CComCachedTearOffObject::FinalConstruct](../Topic/CComCachedTearOffObject::FinalConstruct.md)|Appelle `m_contained::FinalConstruct` \(méthode d'arrachement\).|  
|[CComCachedTearOffObject::FinalRelease](../Topic/CComCachedTearOffObject::FinalRelease.md)|Appelle `m_contained::FinalRelease` \(méthode d'arrachement\).|  
|[CComCachedTearOffObject::QueryInterface](../Topic/CComCachedTearOffObject::QueryInterface.md)|Retourne un pointeur vers `IUnknown` de l'objet d' `CComCachedTearOffObject` , ou à l'interface demandée sur votre arrachez la classe \(classe `contained`\).|  
|[CComCachedTearOffObject::Release](../Topic/CComCachedTearOffObject::Release.md)|Décrémente le décompte de références d'un objet d' `CComCachedTearOffObject` et le perd si le décompte de références est 0.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComCachedTearOffObject::m\_contained](../Topic/CComCachedTearOffObject::m_contained.md)|Un objet d' `CComContainedObject` dérivé de votre arrachent la classe \(classe `contained`\).|  
  
## Notes  
 Implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) d'`CComCachedTearOffObject` pour une interface volante.  Cette classe est différent d' `CComTearOffObject` du fait `CComCachedTearOffObject` a son propre **IUnknown**, distinct d' **IUnknown** de l'objet propriétaire \(le propriétaire est l'objet pour lequel l'arrachement est créé.\)  `CComCachedTearOffObject` met à jour son propre décompte de références sur son **IUnknown** et se supprime une fois que son décompte de références est zéro.  Toutefois, si vous interrogez pour un de ses interfaces volantes, le décompte de références d' **IUnknown** de l'objet propriétaire est incrémenté.  
  
 Si l'objet d' `CComCachedTearOffObject` implémentant l'arrachement est déjà été instancié, et l'interface volante est interrogée de nouveau, le même objet d' `CComCachedTearOffObject` est réutilisé.  En revanche, si une interface volante implémentée par `CComTearOffObject` est encore interrogé pour via l'objet propriétaire, un autre `CComTearOffObject` est instancié.  
  
 La classe propriétaire doit implémenter `FinalRelease` et appeler **Release** sur **IUnknown** mis en cache pour `CComCachedTearOffObject`, qui décrémentera son décompte de références.  Cela entraîne être appelé et supprimer `FinalRelease` d'`CComCachedTearOffObject` l'arrachement.  
  
## Hiérarchie d'héritage  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `IUnknown`  
  
 `CComCachedTearOffObject`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComTearOffObject Class](../../atl/reference/ccomtearoffobject-class.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)