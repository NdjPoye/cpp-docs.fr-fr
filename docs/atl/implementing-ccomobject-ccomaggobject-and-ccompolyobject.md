---
title: "Implementing CComObject, CComAggObject, and CComPolyObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CComPolyObject"
  - "CComAggObject"
  - "CComObject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComAggObject class"
  - "CComObject class, implémenter"
  - "CComPolyObject class, implémenter"
  - "CreateInstance (méthode)"
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Implementing CComObject, CComAggObject, and CComPolyObject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes de modèle [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), et [CComPolyObject](../atl/reference/ccompolyobject-class.md) sont toujours des classes plus dérivées dans la chaîne d'héritage.  Il est de la responsabilité de gérer toutes les méthodes dans **IUnknown**: `QueryInterface`, `AddRef`, et **Release**.  En outre, `CComAggObject` et `CComPolyObject` \(en cas de utilisation pour les objets regroupés en agrégats\) fournissent un décompte de références et la sémantique spéciaux d' `QueryInterface` requis pour l'inconnu interne.  
  
 Si `CComObject`, `CComAggObject`, ou `CComPolyObject` est utilisé dépend de si vous n'en déclarez une \(ou aucune\) des macros suivantes :  
  
|Macro|Effet|  
|-----------|-----------|  
|`DECLARE_NOT_AGGREGATABLE`|Utilise toujours `CComObject`.|  
|`DECLARE_AGGREGATABLE`|Utilise `CComAggObject` si l'objet est regroupé et `CComObject` s'il n'est pas.  `CComCoClass` contient cette macro si aucune des macros de **DECLARE\_\*\_AGGREGATABLE** n'est déclarée dans votre classe, il sera la valeur par défaut.|  
|`DECLARE_ONLY_AGGREGATABLE`|Utilise toujours `CComAggObject`.  Retourne une erreur si l'objet n'est pas regroupé.|  
|`DECLARE_POLY_AGGREGATABLE`|ATL crée une instance de **CComPolyObject\<CYourClass\>** lorsque **IClassFactory::CreateInstance** est appelé.  Pendant la création, la valeur de l'inconnu externe est activée.  Si c'est **NULL**, **IUnknown** est implémenté pour un objet non regroupé en agrégats.  Si l'inconnu externe n'est pas **NULL**, **IUnknown** est implémenté pour un objet regroupé en agrégats.|  
  
 L'avantage d'utiliser `CComAggObject` et `CComObject` est que l'implémentation d' **IUnknown** est optimisée pour le type d'objet créé.  Par exemple, un objet non regroupé en agrégats a uniquement besoin d'un décompte de références, alors qu'un objet regroupé en agrégats a besoin d'un décompte de références pour l'inconnu interne et d'un pointeur vers l'inconnu externe.  
  
 l'avantage d'utiliser `CComPolyObject` est que vous évitez d'avoir `CComAggObject` et `CComObject` dans votre module pour traiter les cas de synthèse et non regroupés en agrégats.  Handles d'objet unique d' `CComPolyObject` les deux cas.  Cela signifie qu'une copie du pointeur vtable et une copie des fonctions existent dans votre package.  Si votre pointeur vtable est important, cela peut considérablement réduire la taille du module.  Toutefois, si votre pointeur vtable est petite, à l'aide de `CComPolyObject` peuvent entraîner une taille légèrement plus grande de module car elle n'est pas optimisée pour un objet de synthèse ou non regroupé en agrégats, de même qu' `CComAggObject` et `CComObject`.  
  
## Voir aussi  
 [Fundamentals of ATL COM Objects](../atl/fundamentals-of-atl-com-objects.md)   
 [Aggregation and Class Factory Macros](../atl/reference/aggregation-and-class-factory-macros.md)