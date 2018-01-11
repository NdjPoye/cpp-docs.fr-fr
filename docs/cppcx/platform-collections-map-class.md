---
title: "Classe Platform::Collections :: Map | Documents Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- COLLECTION/Platform::Collections::Map::Map
- COLLECTION/Platform::Collections::Map::Clear
- COLLECTION/Platform::Collections::Map::First
- COLLECTION/Platform::Collections::Map::GetView
- COLLECTION/Platform::Collections::Map::HasKey
- COLLECTION/Platform::Collections::Map::Insert
- COLLECTION/Platform::Collections::Map::Lookup
- COLLECTION/Platform::Collections::Map::Remove
- COLLECTION/Platform::Collections::Map::Size
dev_langs: C++
helpviewer_keywords: Map Class (C++/Cx)
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
caps.latest.revision: "19"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a3893f7213bc2b154851a5d2481070d0d43724bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="platformcollectionsmap-class"></a>Platform::Collections::Map, classe
Représente *une carte*qui est une collection de paires clé-valeur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = std::less<K>>  
ref class Map sealed;  
```  
#### <a name="parameters"></a>Paramètres  
 `K`  
 Type de la clé dans la paire clé-valeur.  
  
 `V`  
 Type de la valeur dans la paire clé-valeur.  
  
 `C`  
 Type qui fournit un objet de fonction qui peut comparer deux valeurs d'élément comme des clés de tri pour déterminer leur ordre relatif dans le Map. Par défaut, [std::less\<K >](../standard-library/less-struct.md).  
  
 __is_valid_winrt_type()  
 Un compilateur a généré la fonction qui valide le type K et V et fournit un message d'erreur convivial si le type ne peut pas être enregistré dans le mappage.  
  
### <a name="remarks"></a>Notes  
 Les types autorisés sont les suivants :  
  
-   Entiers  
  
-   Classe interface ^  
  
-   Classe ref publique ^  
  
-   value struct  
  
-   classe d'énumération publique  
  
 Map est essentiellement un wrapper pour [std::map](../standard-library/map-class.md). Il s’agit d’une implémentation concrète C++ de la [Windows::Foundation::Collections::IMap < Windows::Foundation::Collections::IKeyValuePair\<K, V >>](http://go.microsoft.com/fwlink/p/?LinkId=262408) et [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx) les types qui sont passés à travers public des interfaces Windows Runtime. Si vous tentez d'utiliser un type `Platform::Collections::Map` dans une valeur de retour ou un paramètre public, l'erreur de compilateur C3986 est générée. Vous pouvez corriger l’erreur en modifiant le type de la valeur de paramètre ou de retour à [Windows::Foundation::Collections::IMap\<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262408).  
  
 Pour plus d’informations, consultez [Collections](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Map::Map](#ctor)|Initialise une nouvelle instance de la classe Map.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Map::Clear](#clear)|Supprime toutes les paires clé-valeur de l'objet Map actuel.|  
|[Map::First](#first)|Retourne un itérateur qui spécifie le premier élément de la carte.|  
|[Map::GetView](#getview)|Retourne une vue en lecture seule du Map actif ; autrement dit, [Platform::Collections::MapView Class](../cppcx/platform-collections-mapview-class.md).|  
|[Map::HasKey](#haskey)|Détermine si le Map actuel contient la clé spécifiée.|  
|[Map::Insert](#insert)|Ajoute une paire clé-valeur spécifiée à l'objet Map actuel.|  
|[Map::Lookup](#lookup)|Récupère l'élément à la clé spécifiée dans l'objet Map actuel.|  
|[Map::Remove](#remove)|Supprime la paire clé-valeur spécifiée de l'objet Map actuel.|  
|[Map::Size](#size)|Retourne le nombre d'éléments dans l'objet Map actuel.|  
  
### <a name="events"></a>Événements  
  
|||  
|-|-|  
|Name|Description|  
|[Map::MapChanged](#mapchanged-event.md)`event`|Se produit lorsque l'objet Map est modifié.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `Map`  
  
### <a name="requirements"></a>Configuration requise  
 **En-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  

## <a name="clear"></a>Map::Clear, méthode
Supprime toutes les paires clé-valeur de l'objet Map actuel.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual void Clear();   
```  
  


## <a name="first"></a>Map::First (méthode)
Retourne un itérateur qui spécifie le premier élément de la carte ou `nullptr` si la carte est vide.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui spécifie le premier élément de la carte.  
  
### <a name="remarks"></a>Notes  
 Un moyen pratique de contenir l’itérateur retourné par First() est d’assigner la valeur de retournée à une variable déclarée avec le **automatique** mot clé de déduction de type. Par exemple, `auto x = myMap->First();`.  
  


## <a name="getview"></a>Map::GetView (méthode)
Retourne une vue en lecture seule de l’objet Map actuel. Autrement dit, un [classe Platform::Collections :: mapview](../cppcx/platform-collections-mapview-class.md), qui implémente le [Windows::Foundation::Collections::IMapView\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226037.aspx) interface.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
Windows::Foundation::Collections::IMapView<K, V>^ GetView();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `MapView`.  
  


## <a name="haskey"></a>Map::HasKey (méthode)
Détermine si le Map actuel contient la clé spécifiée.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>Paramètres  
 `key`  
 Clé utilisée pour rechercher l’élément Map. Le type de `key` est le nom de type *K*.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la clé est trouvée ; sinon, `false`.  
  


## <a name="insert"></a>Map::INSERT, méthode
Ajoute une paire clé-valeur spécifiée à l'objet Map actuel.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
virtual bool Insert(K key, V value);  
```  
  
### <a name="parameters"></a>Paramètres  
 `key`  
 Partie de clé de la paire clé-valeur. Le type de `key` est le nom de type *K*.  
  
 `value`  
 Partie de valeur de la paire clé-valeur. Le type de `value` est le nom de type *V*.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la clé d'un élément existant dans les correspondances de l'objet Map actuel `key` et si la partie de la valeur de cet élément a la valeur `value`. `false` si aucun élément existant dans les correspondances de l'objet Map actuel `key` et si les paramètres `key` et `value` sont transformés en paire clé-valeur puis ajoutés à l'objet Map actuel.  
  


## <a name="lookup"></a>Map::Lookup (méthode)
Récupère la valeur de type V associée à la clé spécifiée de type K si la clé existe.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>Paramètres  
 `key`  
 Clé utilisée pour trouver un élément dans le Map. Le type de `key` est le nom de type *K*.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur associée à `key`. Le type de la valeur de retour est typename *V*.  
  
### <a name="remarks"></a>Notes  
 Si la clé n’existe pas, un [Platform::OutOfBoundsException](../cppcx/platform-outofboundsexception-class.md) est levée.  
  


## <a name="ctor"></a>Map::Map (constructeur)
Initialise une nouvelle instance de la classe Map.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
explicit Map(const C& comp = C());  
explicit Map(const StdMap& m);  
explicit Map(StdMap&& m ;  
template <typename InIt>  
Map(  
   InItfirst,  
   InItlast,  
   const C& comp = C());  
```  
  
### <a name="parameters"></a>Paramètres  
 `InIt`  
 Nom de type de l'objet Map actuel.  
  
 `comp`  
 Type qui fournit un objet de fonction qui peut comparer deux valeurs d'élément comme des clés de tri pour déterminer leur ordre relatif dans le Map.  
  
 `m`  
 Une référence ou [Lvalues et Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) à un `map Class` qui est utilisé pour initialiser le Map actuel.  
  
 `first`  
 Itérateur d'entrée du premier élément d'une plage d'éléments utilisée pour initialiser le Map actuel.  
  
 `last`  
 Itérateur d'entrée du premier élément qui suit une plage d'éléments utilisée pour initialiser le Map actuel.  
  


## <a name="mapchanged"></a>Map::mapchanged, événement
Se déclenche lorsqu'un élément est inséré ou supprimé dans le mappage.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
event Windows::Foundation::Collections::MapChangedEventHandler<K,V>^ MapChanged;  
```  
  
### <a name="property-valuereturn-value"></a>Valeur de propriété/valeur de retour  
 A [MapChangedEventHandler\<K, V >](http://msdn.microsoft.com/library/windows/apps/br206644.aspx) qui contient des informations sur l’objet qui a déclenché l’événement et le type de modification qui s’est produite. Voir aussi [IMapChangedEventArgs\<K >](http://msdn.microsoft.com/library/windows/apps/br226034.aspx) et [énumération CollectionChange](http://msdn.microsoft.com/library/windows/apps/windows.foundation.collections.collectionchange.aspx).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Les applications du Windows Store qui utilisent c# ou Visual Basic projet IMap\<K, V > comme IDictionary\<K, V >.  
  


## <a name="remove"></a>Map::Remove, méthode
Supprime la paire clé-valeur spécifiée de l'objet Map actuel.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual void Remove(K key);  
```  
  
### <a name="parameters"></a>Paramètres  
 `key`  
 Partie de clé de la paire clé-valeur. Le type de `key` est le nom de type *K*.  
  


## <a name="size"></a>Map::Size, méthode
Retourne le nombre de [Windows::Foundation::Collections::IKeyValuePair\<K, V >](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) contenus dans le Map.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d'éléments du Map.  
  

  
## <a name="see-also"></a>Voir aussi  
 [Plateforme Namespace](platform-namespace-c-cx.md)   
 [Création de composants Windows Runtime en C++](/MicrosoftDocs/windows-uwp/blob/docs/windows-apps-src/winrt-components/creating-windows-runtime-components-in-cpp.md)