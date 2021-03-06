---
title: 'Classe Platform::Collections :: mapview | Documents Microsoft'
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- COLLECTION/Platform::Collections::MapView::MapView
- COLLECTION/Platform::Collections::MapView::First
- COLLECTION/Platform::Collections::MapView::HasKey
- COLLECTION/Platform::Collections::MapView::Lookup
- COLLECTION/Platform::Collections::MapView::Size
- COLLECTION/Platform::Collections::MapView::Split
dev_langs:
- C++
helpviewer_keywords:
- MapView Class
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9b5000ad06e542aa4616a29150601b8d628fc097
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="platformcollectionsmapview-class"></a>Platform::Collections::MapView, classe
Représente une vue en lecture seule dans une *carte*, qui est une collection de paires clé/valeur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = ::std::less<K>>  
ref class MapView sealed;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `K`  
 Type de la clé dans la paire clé-valeur.  
  
 `V`  
 Type de la valeur dans la paire clé-valeur.  
  
 `C`  
 Type qui fournit un objet de fonction qui peut comparer deux valeurs d'élément comme des clés de tri pour déterminer leur ordre relatif dans le MapView. Par défaut, [std::less\<K >](../standard-library/less-struct.md).  
  
### <a name="remarks"></a>Notes  
 MapView est une implémentation C++ concrète de la [Windows::Foundation::Collections::IMapView \<K, V >](http://go.microsoft.com/fwlink/p/?LinkId=262409) interface est passée à travers l’interface binaire d’application (ABI). Pour plus d'informations, consultez [Collections (C++/CX)](../cppcx/collections-c-cx.md).  
  
### <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[MapView::MapView](#ctor)|Initialise une nouvelle instance de la classe MapView.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[MapView::First](#first)|Retourne un itérateur qui est initialisé au premier élément de la vue cartographique.|  
|[MapView::HasKey](#haskey)|Détermine si le MapView actif contient la clé spécifiée.|  
|[MapView::Lookup](#lookup)|Récupère l'élément à la clé spécifiée dans l'objet MapView actif.|  
|[MapView::Size](#size)|Retourne le nombre d'éléments dans l'objet MapView actuel.|  
|[MapView::Split](#split)|Fractionne un objet MapView d'origine en deux objets MapView.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `MapView`  
  
### <a name="requirements"></a>Spécifications  
 **En-tête :** collection.h  
  
 **Espace de noms :** Platform::Collections  


## <a name="first"></a> MapView::First (méthode)
Retourne un itérateur qui spécifie le premier élément de la vue de mappage.  
  
### <a name="syntax"></a>Syntaxe  
  
```    
virtual Windows::Foundation::Collections::IIterator<  
   Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui spécifie le premier élément de la vue cartographique.  
  
### <a name="remarks"></a>Notes  
 Un moyen pratique de contenir l’itérateur retourné par First() est d’assigner la valeur de retournée à une variable déclarée avec le **automatique** mot clé de déduction de type. Par exemple, `auto x = myMapView->First();`.  
  


## <a name="haskey"></a>  MapView::HasKey (méthode)
Détermine si le MapView actif contient la clé spécifiée.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
  
bool HasKey(K key);  
```  
  
### <a name="parameters"></a>Paramètres  
 `key`  
 Clé utilisée pour rechercher l’élément MapView. Le type de `key` est le nom de type *K*.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la clé est trouvée ; sinon, `false`.  
  


##  <a name="lookup"></a> MapView::Lookup (méthode)
Récupère la valeur du type V associé à la clé spécifiée de type K.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
V Lookup(K key);  
```  
  
### <a name="parameters"></a>Paramètres  
 `key`  
 Clé utilisée pour trouver un élément dans le MapView. Le type de `key` est le nom de type *K*.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur associée à `key`. Le type de la valeur de retour est typename *V*.  
  


##  <a name="ctor"></a> MapView::MapView (constructeur)
Initialise une nouvelle instance de la classe MapView.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
explicit MapView(const C& comp = C());  
  
explicit MapView(const ::std::map<K, V, C>& m);  
  
explicit MapView(std::map<K, V, C>&& m);  
  
template <typename InIt> MapView(  
    InIt first,  
    InIt last,  
    const C& comp = C());  
  
MapView(
    ::std::initializer_list<std::pair<const K, V>> il,  
    const C& comp = C());  
```  
  
### <a name="parameters"></a>Paramètres  
 `InIt`  
 Typename du MapView actif.  
  
 `comp`  
 Objet de fonction qui peut comparer deux valeurs d'élément comme des clés de tri pour déterminer leur ordre relatif dans le MapView.  
  
 `m`  
 Une référence ou [Lvalues et Rvalues](../cpp/lvalues-and-rvalues-visual-cpp.md) à un `map Class` qui est utilisé pour initialiser le MapView actif.  
  
 `first`  
 Itérateur d'entrée du premier élément d'une plage d'éléments utilisée pour initialiser le MapView actif.  
  
 `last`  
 Itérateur d'entrée du premier élément qui suit une plage d'éléments utilisée pour initialiser le MapView actif.  
  
 il  
 A [std::initializer_list < std::pair\<K, V >>](../standard-library/initializer-list-class.md) dont les éléments sont insérés dans le MapView.  



##  <a name="size"></a> Mapview::Size, méthode
Retourne le nombre d'éléments dans l'objet MapView actuel.  
  
### <a name="syntax"></a>Syntaxe  
  
```cpp  
  
virtual property unsigned int Size;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre d’éléments dans l’objet MapView actuel.  
  


##  <a name="split"></a> MapView::Split (méthode)
Divise l'objet MapView actif en deux objets MapView. Cette méthode n'est pas opérationnelle.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
void Split(  
   Windows::Foundation::Collections::IMapView<  
                         K, V>^ * firstPartition,  
   Windows::Foundation::Collections::IMapView<  
                         K, V>^ * secondPartition);  
```  
  
### <a name="parameters"></a>Paramètres  
 `firstPartition`  
 Première partie de l'objet MapView d'origine.  
  
 `secondPartition`  
 Deuxième partie de l'objet MapView d'origine.  
  
### <a name="remarks"></a>Notes  
 Cette méthode n'est pas opérationnelle. Elle ne fait rien.  
    
## <a name="see-also"></a>Voir aussi  
 [Plateforme Namespace](platform-namespace-c-cx.md)