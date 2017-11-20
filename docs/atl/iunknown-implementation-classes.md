---
title: "Classes d’implémentation de IUnknown (ATL) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.Iunknown
dev_langs: C++
helpviewer_keywords: IUnknown implementation classes
ms.assetid: 47b69bb5-69d8-4a9c-84a8-329bdde2bb3f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: ac484e58b585a09eff40d1b058e44dad6b8d394c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="iunknown-implementation-classes"></a>Classes d’implémentation de IUnknown
Les classes suivantes implémentent **IUnknown** et des méthodes apparentées :  
  
-   [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) gère le décompte de références pour les objets regroupés et agrégées. Vous permet de spécifier un modèle de thread.  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) gère le décompte de références pour les objets regroupés et agrégées. Utilise la valeur par défaut, le modèle du serveur de thread.  
  
-   [CComAggObject](../atl/reference/ccomaggobject-class.md) implémente **IUnknown** pour un objet.  
  
-   [CComObject](../atl/reference/ccomobject-class.md) implémente **IUnknown** pour un objet brutes et non agrégée.  
  
-   [CComPolyObject](../atl/reference/ccompolyobject-class.md) implémente **IUnknown** pour les objets regroupés et. À l’aide de `CComPolyObject` évite d’avoir à la fois `CComAggObject` et `CComObject` dans votre module. Un seul `CComPolyObject` objet gère les cas regroupés et agrégées.  
  
-   [CComObjectNoLock](../atl/reference/ccomobjectnolock-class.md) implémente **IUnknown** pour un objet brutes et non agrégée, sans modifier le nombre de verrous du module.  
  
-   [CComTearOffObject](../atl/reference/ccomtearoffobject-class.md) implémente **IUnknown** pour une interface détachable.  
  
-   [CComCachedTearOffObject](../atl/reference/ccomcachedtearoffobject-class.md) implémente **IUnknown** pour une interface détachable « mis en cache ».  
  
-   [CComContainedObject](../atl/reference/ccomcontainedobject-class.md) implémente **IUnknown** pour l’objet interne d’une agrégation ou une interface détachable.  
  
-   [CComObjectGlobal](../atl/reference/ccomobjectglobal-class.md) gère un décompte de références sur le module pour vous assurer de votre objet n’est pas supprimé.  
  
-   [CComObjectStack](../atl/reference/ccomobjectstack-class.md) crée un objet COM temporaire, à l’aide d’une implémentation squelette de **IUnknown**.  
  
## <a name="related-articles"></a>Articles connexes  
 [Principes de base des objets ATL COM](../atl/fundamentals-of-atl-com-objects.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../atl/atl-class-overview.md)   
 [Agrégation et Macros de fabrique de classe](../atl/reference/aggregation-and-class-factory-macros.md)   
 [Macros de mappage COM](../atl/reference/com-map-macros.md)   
 [Fonctions globales de mappage COM](../atl/reference/com-map-global-functions.md)

