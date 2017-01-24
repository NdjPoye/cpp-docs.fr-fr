---
title: "CComObjectRootEx Class | Microsoft Docs"
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
  - "ATL.CComObjectRootEx"
  - "ATL::CComObjectRootEx<ThreadModel>"
  - "CComObjectRootEx"
  - "ATL::CComObjectRootEx"
  - "ATL.CComObjectRootEx<ThreadModel>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "reference counting"
ms.assetid: 894a3d7c-2daf-4fd0-8fa4-e6a05bcfb631
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComObjectRootEx Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe fournit des méthodes à la gestion de décompte de référence d'objet de handle pour non regroupé en agrégats et des objets regroupés en agrégats.  
  
## Syntaxe  
  
```  
  
      template<  
   class ThreadModel   
>  
class CComObjectRootEx : public CComObjectRootBase  
```  
  
#### Paramètres  
 `ThreadModel`  
 La classe dont les méthodes implémentent le modèle de thread désiré.  Vous pouvez choisir explicitement le modèle de thread en définissant `ThreadModel` à [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md), à [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), ou à [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md).  Vous pouvez accepter le modèle de thread par défaut du serveur en définissant `ThreadModel` à [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) ou à [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md).  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[CComObjectRootEx](../Topic/CComObjectRootEx::CComObjectRootEx.md)|Constructeur.|  
|[InternalAddRef](../Topic/CComObjectRootEx::InternalAddRef.md)|Incrémente le décompte de références d'un objet non regroupé en agrégats.|  
|[InternalRelease](../Topic/CComObjectRootEx::InternalRelease.md)|Décrémente le décompte de références d'un objet non regroupé en agrégats.|  
|[Verrouiller](../Topic/CComObjectRootEx::Lock.md)|Si le modèle de thread est multithread, obtient la propriété d'un objet de section critique.|  
|[Déverrouillez](../Topic/CComObjectRootEx::Unlock.md)|Si le modèle de thread est multithread, libère la propriété d'un objet de section critique.|  
  
### Méthodes de CComObjectRootBase  
  
|||  
|-|-|  
|[FinalConstruct](../Topic/CComObjectRootEx::FinalConstruct.md)|Substitution dans votre classe pour effectuer toute initialisation requise par votre objet.|  
|[FinalRelease](../Topic/CComObjectRootEx::FinalRelease.md)|Substitution dans votre classe pour exécuter tout nettoyage requis par votre objet.|  
|[OuterAddRef](../Topic/CComObjectRootEx::OuterAddRef.md)|Incrémente le décompte de références d'un objet regroupé en agrégats.|  
|[OuterQueryInterface](../Topic/CComObjectRootEx::OuterQueryInterface.md)|Délégués à **IUnknown** externe d'un objet regroupé en agrégats.|  
|[OuterRelease](../Topic/CComObjectRootEx::OuterRelease.md)|Décrémente le décompte de références d'un objet regroupé en agrégats.|  
  
### Fonctions static  
  
|||  
|-|-|  
|[InternalQueryInterface](../Topic/CComObjectRootEx::InternalQueryInterface.md)|Délégués à **IUnknown** d'un objet non regroupé en agrégats.|  
|[ObjectMain](../Topic/CComObjectRootEx::ObjectMain.md)|Appelé pendant l'initialisation et l'arrêt de package pour les classes dérivées listé dans la table d'objets.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_dwRef](../Topic/CComObjectRootEx::m_dwRef.md)|Avec `m_pOuterUnknown`, une partie d'une union.  Utilisé lorsque l'objet n'est pas regroupé pour contenir le décompte de références d' `AddRef` et de **Release**.|  
|[m\_pOuterUnknown](../Topic/CComObjectRootEx::m_pOuterUnknown.md)|Avec `m_dwRef`, une partie d'une union.  Utilisé lorsque l'objet est regroupé pour stocker un pointeur vers l'inconnu externe.|  
  
## Notes  
 Gestion du nombre de référence d'objet de handles d'`CComObjectRootEx` pour non regroupé en agrégats et des objets regroupés en agrégats.  Il contient le nombre de référence d'objet si votre objet n'est pas regroupé, et contient le pointeur à l'extérieur inconnu si votre objet est regroupé.  Pour les objets regroupés en agrégats, des méthodes d' `CComObjectRootEx` peuvent être utilisées pour gérer l'échec de l'objet interne à l'élément, et protéger l'objet externe de la suppression lorsque les interfaces internes sont libérées ou l'objet interne est supprimé.  
  
 Une classe qui implémente un serveur COM doit hériter d' `CComObjectRootEx` ou de [CComObjectRoot](../../atl/reference/ccomobjectroot-class.md).  
  
 Si votre définition de classe spécifie la macro de [DECLARE\_POLY\_AGGREGATABLE](../Topic/DECLARE_POLY_AGGREGATABLE.md) , ATL crée une instance de **CComPolyObject\<CYourClass\>** lorsque **IClassFactory::CreateInstance** est appelé.  Pendant la création, la valeur de l'inconnu externe est activée.  Si c'est **NULL**, **IUnknown** est implémenté pour un objet non regroupé en agrégats.  Si l'inconnu externe n'est pas **NULL**, **IUnknown** est implémenté pour un objet regroupé en agrégats.  
  
 Si votre classe ne spécifie pas la macro d' `DECLARE_POLY_AGGREGATABLE` , ATL crée une instance de **CAggComObject\<CYourClass\>** pour les objets regroupés en agrégats ou une instance de **CComObject\<CYourClass\>** des objets non regroupés en agrégats.  
  
 l'avantage d'utiliser `CComPolyObject` est que vous évitez d'avoir `CComAggObject` et `CComObject` dans votre module pour traiter les cas de synthèse et non regroupés en agrégats.  Handles d'objet unique d' `CComPolyObject` les deux cas.  Par conséquent, une seule copie du pointeur vtable et une copie des fonctions existent dans votre package.  Si votre pointeur vtable est important, cela peut considérablement réduire la taille du module.  Toutefois, si votre pointeur vtable est petite, à l'aide de `CComPolyObject` peuvent entraîner une taille légèrement plus grande de module car elle n'est pas optimisée pour un objet de synthèse ou non regroupé en agrégats, de même qu' `CComAggObject` et `CComObject`.  
  
 Si votre objet est regroupé, [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) est implémenté par `CComAggObject` ou `CComPolyObject`.  Ces classes délèguent `QueryInterface`, `AddRef`, et les appels de **Release** à `OuterQueryInterface`, à `OuterAddRef`, et à `OuterRelease` d'`CComObjectRootEx` pour transférer à l'inconnu externe.  En général, vous substituez `CComObjectRootEx::FinalConstruct` dans votre classe pour créer tous les objets regroupés en agrégats, et remplacez `CComObjectRootEx::FinalRelease` pour libérer les objets regroupés en agrégats.  
  
 Si votre objet n'est pas regroupé, **IUnknown** est implémenté par `CComObject` ou `CComPolyObject`.  Dans ce cas, les appels à `QueryInterface`, l' `AddRef`, et le **Release** sont délégués à `InternalQueryInterface`, à `InternalAddRef`, et à `InternalRelease` d'`CComObjectRootEx` pour exécuter des opérations réelles.  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)