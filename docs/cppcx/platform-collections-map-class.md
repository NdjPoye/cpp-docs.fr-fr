---
title: "Platform::Collections::Map, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map (classe) (C++/Cx)"
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
caps.latest.revision: 19
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 19
---
# Platform::Collections::Map, classe
Représente *une carte* qui est une collection de paires clé\-valeur.  
  
## Syntaxe  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = std::less<K>  
ref class Map sealed;  
```  
  
#### Paramètres  
 `K`  
 Type de la clé dans la paire clé\-valeur.  
  
 `V`  
 Type de la valeur dans la paire clé\-valeur.  
  
 `C`  
 Type qui fournit un objet de fonction qui peut comparer deux valeurs d'élément comme des clés de tri pour déterminer leur ordre relatif dans le Map. Par défaut, [std::less\<K\>](../standard-library/less-struct.md).  
  
 \_\_is\_valid\_winrt\_type\(\)  
 Un compilateur a généré la fonction qui valide le type K et V et fournit un message d'erreur convivial si le type ne peut pas être enregistré dans le mappage.  
  
## Notes  
 Les types autorisés sont les suivants :  
  
-   Entiers  
  
-   Classe interface ^  
  
-   Classe ref publique ^  
  
-   value struct  
  
-   classe d'énumération publique  
  
 Map est essentiellement un wrapper pour [std::map](../standard-library/map-class.md). Il s’agit d’une implémentation concrète C\+\+ des types [Windows::Foundation::Collections::IMap\<Windows::Foundation::Collections::IKeyValuePair\<K,V\>\>](http://go.microsoft.com/fwlink/p/?LinkId=262408) et [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) qui sont passés à travers des interfaces [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)] publiques. Si vous tentez d'utiliser un type `Platform::Collections::Map` dans une valeur de retour ou un paramètre public, l'erreur de compilateur C3986 est générée. Vous pouvez corriger l’erreur en remplaçant le type du paramètre ou de la valeur de retour par [Windows::Foundation::Collections::IMap\<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262408).  
  
 Pour plus d'informations, consultez [Collections](../cppcx/collections-c-cx.md).  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[Map::Map \(constructeur\)](../cppcx/map-map-constructor.md)|Initialise une nouvelle instance de la classe Map.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[Map::Clear, méthode](../cppcx/map-clear-method.md)|Supprime toutes les paires clé\-valeur de l'objet Map actuel.|  
|[Map::First \(méthode\)](../cppcx/map-first-method.md)|Retourne un itérateur qui spécifie le premier élément de la carte.|  
|[Map::GetView \(méthode\)](../cppcx/map-getview-method.md)|Retourne une vue en lecture seule du Map actif ; autrement dit, [Platform::Collections::MapView, classe](../cppcx/platform-collections-mapview-class.md).|  
|[Map::HasKey \(méthode\)](../cppcx/map-haskey-method.md)|Détermine si le Map actuel contient la clé spécifiée.|  
|[Map::Insert, méthode](../cppcx/map-insert-method.md)|Ajoute une paire clé\-valeur spécifiée à l'objet Map actuel.|  
|[Map::Lookup \(méthode\)](../cppcx/map-lookup-method.md)|Récupère l'élément à la clé spécifiée dans l'objet Map actuel.|  
|[Map::Remove, méthode](../cppcx/map-remove-method.md)|Supprime la paire clé\-valeur spécifiée de l'objet Map actuel.|  
|[Map::Size, méthode](../cppcx/map-size-method.md)|Retourne le nombre d'éléments dans l'objet Map actuel.|  
  
### Événements  
  
|||  
|-|-|  
|Nom|Description|  
|[Map::MapChanged, événement](../cppcx/map-mapchanged-event.md) `event`|Se produit lorsque l'objet Map est modifié.|  
  
## Hiérarchie d'héritage  
 `Map`  
  
## Configuration requise  
 **En\-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  
  
## Voir aussi  
 [\(NOTINBUILD\) Espace de noms Platform](http://msdn.microsoft.com/fr-fr/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Création de composants Windows Runtime en C\+\+](../Topic/Creating%20Windows%20Runtime%20Components%20in%20C++.md)