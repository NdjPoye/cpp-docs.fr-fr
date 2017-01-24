---
title: "Fundamentals of ATL COM Objects | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL COM objects"
  - "ATL, COM"
  - "objets COM, ATL"
  - "COM, et ATL"
ms.assetid: 0f9c9d98-cc28-45da-89ac-dc94cee422fe
caps.latest.revision: 25
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fundamentals of ATL COM Objects
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'illustration suivante représente la relation entre les classes et les interfaces utilisées pour définir un objet ATL COM.  
  
 ![Structure ATL](../atl/media/vc307y1.png "vc307Y1")  
  
> [!NOTE]
>  Ce diagramme montre qu' `CComObject` est dérivé d' `CYourClass` pendant qu' `CComAggObject` et `CComPolyObject` incluent `CYourClass` comme variable membre.  
  
 Il existe trois façons de définir un objet ATL COM.  L'option standard est d'utiliser la classe d' `CComObject` dérivée d' `CYourClass`.  La deuxième option consiste à créer un objet regroupé en agrégats à l'aide de la classe d' `CComAggObject` .  La troisième option consiste à utiliser la classe d' `CComPolyObject` .  `CComPolyObject` agit comme un hybride : il peut fonctionner comme une classe d' `CComObject` ou comme classe d' `CComAggObject` , selon la façon dont il est d'abord créé.  Pour plus d'informations sur l'utilisation de la classe `CComPolyObject`, consultez [CComPolyObject Class](../atl/reference/ccompolyobject-class.md).  
  
 Lorsque vous utilisez ATL COM standard, vous utilisez deux objets : un objet externe et un objet interne.  Les clients externes accèdent aux fonctionnalités de l'objet interne via les fonctions wrapper qui sont définies dans l'objet externe.  l'objet externe est de type `CComObject`.  
  
 Lorsque vous utilisez un objet regroupé en agrégats, l'objet externe ne fournit pas les wrappers pour les fonctionnalités de l'objet interne.  Au lieu de cela, l'objet externe fournit un pointeur qui est directement accessible par les clients externes.  Dans ce cas, l'objet externe est de type `CComAggObject`.  l'objet interne est une variable membre de l'objet externe, et il est de type `CYourClass`.  
  
 Étant donné que le client ne doit pas passer par l'objet externe pour interagir avec l'objet interne, les objets regroupés en agrégats sont généralement plus efficaces.  De plus, l'objet externe ne doit pas connaître les fonctionnalités de l'objet regroupé en agrégats, dans la mesure où l'interface de l'objet regroupé en agrégats est directement à la disposition du client.  Toutefois, tous les objets peuvent être regroupés.  Pour qu'un objet est regroupé, il doit être conçu avec une agrégation à l'esprit.  
  
 Implémente [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) ATL en deux phases :  
  
-   Outils de[CComObject](../atl/reference/ccomobject-class.md), de [CComAggObject](../atl/reference/ccomaggobject-class.md), ou de [CComPolyObject](../atl/reference/ccompolyobject-class.md) les méthodes d' **IUnknown** .  
  
-   [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) ou [CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) gère le décompte de références et les pointeurs externes d' **IUnknown**.  
  
 D'autres aspects de votre objet ATL COM sont traités par d'autres classes :  
  
-   [CComCoClass](../atl/reference/ccomcoclass-class.md) définit le modèle par défaut de la fabrique de classe et le regroupement de l'objet.  
  
-   [IDispatchImpl](../atl/reference/idispatchimpl-class.md) fournit une implémentation par défaut de la partie d' `IDispatch Interface` de toutes les interfaces doubles sur l'objet.  
  
-   [ISupportErrorInfoImpl](../atl/reference/isupporterrorinfoimpl-class.md) implémente l'interface d' **ISupportErrorInfo** qui vérifie les informations d'erreur peut être propagée vers le haut de la chaîne d'appels correctement.  
  
## Dans cette section  
 [implémenter CComObjectRootEx](../atl/implementing-ccomobjectrootex.md)  
 Entrées de mappage COM d'exemple show pour implémenter `CComObjectRootEx`.  
  
 [implémenter CComObject, CComAggObject, et CComPolyObject](../atl/implementing-ccomobject-ccomaggobject-and-ccompolyobject.md)  
 Décrit comment les macros de **DECLARE\_\*\_AGGREGATABLE** affectent l'utilisation d' `CComObject`, d' `CComAggObject`, et d' `CComPolyObject`.  
  
 [IDispatch et de prise en charge IErrorInfo](../atl/supporting-idispatch-and-ierrorinfo.md)  
 Répertorie les classes d'implémentation ATL à utiliser pour prendre en charge `IDispatch` et les interfaces d' **IErrorInfo** .  
  
 [IDispEventImpl prenant](../atl/supporting-idispeventimpl.md)  
 Décrit les étapes pour implémenter un point de connexion pour votre classe.  
  
 [Modifier le modèle par défaut de fabrique de classes et de regroupement](../atl/changing-the-default-class-factory-and-aggregation-model.md)  
 Afficher les macros à utiliser pour modifier la fabrique de classes et le regroupement par défaut modèle.  
  
 [créer un objet regroupé en agrégats](../atl/creating-an-aggregated-object.md)  
 Répertorie les étapes pour créer un objet regroupé en agrégats.  
  
## Rubriques connexes  
 [créer un projet ATL](../atl/reference/creating-an-atl-project.md)  
 Fournit des informations sur la création d'un objet ATL COM.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Fournit des liens vers des rubriques conceptuelles sur comment programmer avec la bibliothèque ATL.  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)