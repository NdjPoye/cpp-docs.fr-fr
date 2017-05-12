---
title: "Platform::Collections::MapView, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView (classe)"
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Platform::Collections::MapView, classe
Représente une vue en lecture seule dans une *carte*, qui est une collection de paires clé\/valeur.  
  
## Syntaxe  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = ::std::less<K>  
>  
ref class MapView sealed;  
```  
  
#### Paramètres  
 `K`  
 Type de la clé dans la paire clé\-valeur.  
  
 `V`  
 Type de la valeur dans la paire clé\-valeur.  
  
 `C`  
 Type qui fournit un objet de fonction qui peut comparer deux valeurs d'élément comme des clés de tri pour déterminer leur ordre relatif dans le MapView. Par défaut, [::std::less\<K\>](../standard-library/less-struct.md).  
  
## Notes  
 MapView est une implémentation C\+\+ concrète de l’interface [Windows::Foundation::Collections::IMapView \<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262409), qui est passée à travers l’interface binaire d’application \(ABI\). Pour plus d'informations, consultez [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[MapView::MapView \(constructeur\)](../cppcx/mapview-mapview-constructor.md)|Initialise une nouvelle instance de la classe MapView.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[MapView::First \(méthode\)](../cppcx/mapview-first-method.md)|Retourne un itérateur qui est initialisé au premier élément de la vue cartographique.|  
|[MapView::HasKey \(méthode\)](../cppcx/mapview-haskey-method.md)|Détermine si le MapView actif contient la clé spécifiée.|  
|[MapView::Lookup \(méthode\)](../cppcx/mapview-lookup-method.md)|Récupère l'élément à la clé spécifiée dans l'objet MapView actif.|  
|[MapView::Size, méthode](../cppcx/mapview-size-method.md)|Retourne le nombre d'éléments dans l'objet MapView actuel.|  
|[MapView::Split \(méthode\)](../cppcx/mapview-split-method.md)|Fractionne un objet MapView d'origine en deux objets MapView.|  
  
## Hiérarchie d'héritage  
 `MapView`  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)