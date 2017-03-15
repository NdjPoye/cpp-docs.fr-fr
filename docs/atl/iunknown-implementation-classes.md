---
title: "IUnknown Implementation Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.Iunknown"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IUnknown implementation classes"
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# IUnknown Implementation Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes suivantes s'appliquent **IUnknown** et des méthodes connexes :  
  
-   [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) gère le décompte de références pour les objets regroupés et non regroupés en agrégats.  Vous permet de spécifier un modèle de thread.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) gère le décompte de références pour les objets regroupés et non regroupés en agrégats.  Utilise le modèle de thread par défaut du serveur.  
  
-   Implémente **IUnknown** de[CComAggObject](../atl/reference/ccomaggobject-class.md) pour un objet regroupé en agrégats.  
  
-   Implémente **IUnknown** de[CComObject](../atl/reference/ccomobject-class.md) pour un objet non regroupé en agrégats.  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) implémente **IUnknown** pour les objets de synthèse et non regroupés en agrégats.  Utilisation `CComPolyObject` évite d'avoir `CComAggObject` et `CComObject` dans votre package.  Handles d'objet unique d' `CComPolyObject` regroupées et cas non regroupés en agrégats.  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) implémente **IUnknown** pour un objet non regroupé en agrégats, sans modifier le nombre de verrous sur le package.  
  
-   Implémente **IUnknown** de[CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) pour une interface volante.  
  
-   Les outils **IUnknown** de[CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) pour « mises en cache » l'interface volante.  
  
-   [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) implémente **IUnknown** pour l'objet interne d'un regroupement ou d'une interface volante.  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) gère un décompte de références du module pour garantir l'objet ne sera pas supprimé.  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md) crée un objet COM temporaire, à l'aide d'une implémentation squelette d' **IUnknown**.  
  
## Articles connexes  
 [Notions de base des objets COM ATL](../atl/fundamentals-of-atl-com-objects.md)  
  
## Voir aussi  
 [Class Overview](../atl/atl-class-overview.md)   
 [Aggregation and Class Factory Macros](../atl/reference/aggregation-and-class-factory-macros.md)   
 [COM Map Macros](../atl/reference/com-map-macros.md)   
 [COM Map Global Functions](../atl/reference/com-map-global-functions.md)