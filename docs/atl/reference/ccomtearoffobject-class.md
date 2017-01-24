---
title: "CComTearOffObject Class | Microsoft Docs"
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
  - "ATL::CComTearOffObject<Base>"
  - "ATL::CComTearOffObject"
  - "ATL.CComTearOffObject"
  - "ATL.CComTearOffObject<Base>"
  - "CComTearOffObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComTearOffObject class"
  - "tear-off interfaces"
  - "tear-off interfaces, ATL"
ms.assetid: d974b598-c6b2-42b1-8360-9190d9d0fbf3
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComTearOffObject Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe implémente une interface volante.  
  
## Syntaxe  
  
```  
  
      template<  
   class Base   
>  
class CComTearOffObject :  
   public Base  
```  
  
#### Paramètres  
 `Base`  
 Votre arrachez la classe, dérivée de `CComTearOffObjectBase` et les interfaces que vous souhaitez que votre arrachent l'objet en charge.  
  
 ATL implémente les interfaces volantes en deux phases — les méthodes d' `CComTearOffObjectBase` gèrent le décompte de références et `QueryInterface`, tandis que `CComTearOffObject` implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComTearOffObject::CComTearOffObject](../Topic/CComTearOffObject::CComTearOffObject.md)|Constructeur.|  
|[CComTearOffObject::~CComTearOffObject](../Topic/CComTearOffObject::~CComTearOffObject.md)|Le destructeur.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComTearOffObject::AddRef](../Topic/CComTearOffObject::AddRef.md)|Incrémente le décompte de références d'un objet d' `CComTearOffObject` .|  
|[CComTearOffObject::QueryInterface](../Topic/CComTearOffObject::QueryInterface.md)|Retourne un pointeur vers l'interface demandée sur votre arrachent la classe ou la classe propriétaire.|  
|[CComTearOffObject::Release](../Topic/CComTearOffObject::Release.md)|Décrémente le décompte de références d'un objet d' `CComTearOffObject` et le perd.|  
  
### Méthodes de CComTearOffObjectBase  
  
|||  
|-|-|  
|[CComTearOffObjectBase](../Topic/CComTearOffObject::CComTearOffObjectBase.md)|Constructeur.|  
  
### Membres de données de CComTearOffObjectBase  
  
|||  
|-|-|  
|[m\_pOwner](../Topic/CComTearOffObject::m_pOwner.md)|Un pointeur vers `CComObject` dérivé de la classe propriétaire.|  
  
## Notes  
 `CComTearOffObject` implémente une interface volante comme un objet séparé qui est instancié uniquement lorsque cette interface est interrogé pour.  L'arrachement est supprimé lorsque son décompte de références est zéro.  En général, vous générez une interface volante pour une interface qui est rarement utilisée, car vous utilisez un arrachement enregistre un pointeur vtable dans toutes les instances de votre objet principal.  
  
 Vous devez dériver la classe implémentant l'arrachement d' `CComTearOffObjectBase` et de toutes les interfaces vous souhaitez que votre arrachez l'objet en charge.  `CComTearOffObjectBase` est mis en modèle sur la classe propriétaire et le modèle de thread.  La classe propriétaire est la classe de l'objet pour lequel un arrachement est implémenté.  Si vous ne spécifiez pas un modèle de thread, le modèle de thread par défaut est utilisé.  
  
 Vous devez créer un mappage COM de votre arrachez la classe.  Lorsque ATL instancie l'arrachement, il crée **CComTearOffObject\<CYourTearOffClass\>** ou **CComCachedTearOffObject\<CYourTearOffClass\>**.  
  
 Par exemple, dans l'exemple BEEPER, la classe d' `CBeeper2` est la classe d'arrachement et la classe d' `CBeeper` est la classe propriétaire :  
  
 [!code-cpp[NVC_ATL_COM#43](../../atl/codesnippet/CPP/ccomtearoffobject-class_1.h)]  
  
## Hiérarchie d'héritage  
 `Base`  
  
 `CComTearOffObject`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComCachedTearOffObject Class](../../atl/reference/ccomcachedtearoffobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)