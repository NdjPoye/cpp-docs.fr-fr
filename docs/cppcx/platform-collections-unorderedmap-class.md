---
title: "Platform::Collections::UnorderedMap, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap"
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Platform::Collections::UnorderedMap, classe
Représente une *carte* non triée qui est une collection de paires clé\-valeur.  
  
## Syntaxe  
  
```scr  
template <  
   typename K,  
   typename V,  
   typename C = std::equal_to<K>  
>  
ref class Map sealed;  
```  
  
#### Paramètres  
 `K`  
 Type de la clé dans la paire clé\-valeur.  
  
 `V`  
 Type de la valeur dans la paire clé\-valeur.  
  
 `C`  
 Type qui fournit un objet de fonction qui peut comparer deux valeurs d'élément comme des clés de tri pour déterminer leur ordre relatif dans le Map. Par défaut, [std::equal\_to\<K\>](../standard-library/equal-to-struct.md).  
  
## Notes  
 Les types autorisés sont les suivants :  
  
-   Entiers  
  
-   Classe interface ^  
  
-   Classe ref publique ^  
  
-   value struct  
  
-   classe d'énumération publique  
  
 UnorderedMap est essentiellement un wrapper de [std::unordered\_map](../standard-library/unordered-map-class.md) qui prend en charge le stockage des types [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Il s’agit d’une implémentation concrète des types [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408) et [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) qui sont transmis aux interfaces [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] publiques. Si vous tentez d'utiliser un type Platform::Collections::UnorderedMap dans une valeur de retour ou un paramètre public, l'erreur de compilateur C3986 est générée. Vous pouvez corriger l’erreur en modifiant le type du paramètre ou la valeur de retour par [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408).  
  
 Pour plus d'informations, consultez [Collections](../cppcx/collections-c-cx.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|UnorderedMap::UnorderedMap, constructeur|Initialise une nouvelle instance de la classe Map.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[UnorderedMap::Clear, méthode](../cppcx/unorderedmap-clear-method.md)|Supprime toutes les paires clé\-valeur de l'objet Map actuel.|  
|[UnorderedMap::First, méthode](../cppcx/unorderedmap-first-method.md)|Retourne un itérateur qui spécifie le premier élément de la carte.|  
|[UnorderedMap::GetView, méthode](../cppcx/unorderedmap-getview-method.md)|Retourne une vue en lecture seule de la carte active, soit une classe Platform::Collections::UnorderedMapView.|  
|[UnorderedMap::HasKey, méthode](../cppcx/unorderedmap-haskey-method.md)|Détermine si le Map actuel contient la clé spécifiée.|  
|[UnorderedMap::Insert, méthode](../cppcx/unorderedmap-insert-method.md)|Ajoute une paire clé\-valeur spécifiée à l'objet Map actuel.|  
|[UnorderedMap::Lookup, méthode](../cppcx/unorderedmap-lookup-method.md)|Récupère l'élément à la clé spécifiée dans l'objet Map actuel.|  
|[UnorderedMap::Remove, méthode](../cppcx/unorderedmap-remove-method.md)|Supprime la paire clé\-valeur spécifiée de l'objet Map actuel.|  
|[UnorderedMap::Size, méthode](../cppcx/unorderedmap-size-method.md)|Retourne le nombre d'éléments dans l'objet Map actuel.|  
  
### Événements  
  
|||  
|-|-|  
|Nom|Description|  
|[Map::MapChanged, événement](../cppcx/map-mapchanged-event.md) `event`|Se produit lorsque l'objet Map est modifié.|  
  
## Hiérarchie d'héritage  
 `UnorderedMap`  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Platform::Collections \(espace de noms\)](../cppcx/platform-collections-namespace.md)   
 [Platform::Collections::Map, classe](../cppcx/platform-collections-map-class.md)   
 [Platform::Collections::UnorderedMapView, classe](../cppcx/platform-collections-unorderedmapview-class.md)   
 [Collections](../cppcx/collections-c-cx.md)   
 [Création de composants Windows Runtime en C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)