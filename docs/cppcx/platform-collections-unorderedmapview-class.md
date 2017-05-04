---
title: "Platform::Collections::UnorderedMapView, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView"
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Platform::Collections::UnorderedMapView, classe
Représente une vue en lecture seule dans une *carte*, qui est une collection de paires clé\/valeur.  
  
## Syntaxe  
  
```cpp  
template <  
   typename K,  
   typename V,  
   typename C = ::std::equal_to<K>  
>  
ref class UnorderedMapView sealed;  
```  
  
#### Paramètres  
 `K`  
 Type de la clé dans la paire clé\-valeur.  
  
 `V`  
 Type de la valeur dans la paire clé\-valeur.  
  
 `C`  
 Type qui fournit un objet de fonction qui peut comparer l'égalité de deux valeurs de clés. Par défaut, [std::equal\_to\<K\>](../standard-library/equal-to-struct.md)  
  
## Notes  
 UnorderedMapView est une implémentation de C\+\+ concrète de l’interface [Windows::Foundation::Collections::IMapView\<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262409), qui est passée à travers l’interface binaire d’application \(ABI\). Pour plus d'informations, consultez [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[UnorderedMapView::UnorderedMapView, constructeur](../cppcx/unorderedmapview-unorderedmapview-constructor.md)|Initialise une nouvelle instance de la classe UnorderedMapView.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[UnorderedMapView::First, méthode](../cppcx/unorderedmapview-first-method.md)|Retourne un itérateur qui est initialisé au premier élément de la vue cartographique.|  
|[UnorderedMapView::HasKey, méthode](../cppcx/unorderedmapview-haskey-method.md)|Détermine si le UnorderedMapView actuel contient la clé spécifiée.|  
|[UnorderedMapView::Lookup, méthode](../cppcx/unorderedmapview-lookup-method.md)|Récupère l'élément à la clé spécifiée dans l'objet UnorderedMapView actuel.|  
|[UnorderedMapView::Size, méthode](../cppcx/unorderedmapview-size-method.md)|Retourne le nombre d'éléments de l'objet UnorderedMapView actuel.|  
|[UnorderedMapView::Split, méthode](../cppcx/unorderedmapview-split-method.md)|Fractionne un objet UnorderedMapView d'origine en deux objets UnorderedMapView.|  
  
## Hiérarchie d'héritage  
 `UnorderedMapView`  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [Platform::Collections \(espace de noms\)](../cppcx/platform-collections-namespace.md)   
 [Windows::Foundation::IMapView](http://go.microsoft.com/fwlink/p/?LinkId=262409)