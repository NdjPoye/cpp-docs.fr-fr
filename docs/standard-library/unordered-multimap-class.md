---
title: unordered_multimap, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unordered_multimap
- std::unordered_multimap
- unordered_map/std::unordered_multimap
- std::unordered_multimap::allocator_type
- unordered_map/std::unordered_multimap::allocator_type
- std::unordered_multimap::const_iterator
- unordered_map/std::unordered_multimap::const_iterator
- std::unordered_multimap::const_local_iterator
- unordered_map/std::unordered_multimap::const_local_iterator
- std::unordered_multimap::const_pointer
- unordered_map/std::unordered_multimap::const_pointer
- std::unordered_multimap::const_reference
- unordered_map/std::unordered_multimap::const_reference
- std::unordered_multimap::difference_type
- unordered_map/std::unordered_multimap::difference_type
- std::unordered_multimap::hasher
- unordered_map/std::unordered_multimap::hasher
- std::unordered_multimap::iterator
- unordered_map/std::unordered_multimap::iterator
- std::unordered_multimap::key_equal
- unordered_map/std::unordered_multimap::key_equal
- std::unordered_multimap::key_type
- unordered_map/std::unordered_multimap::key_type
- std::unordered_multimap::local_iterator
- unordered_map/std::unordered_multimap::local_iterator
- std::unordered_multimap::mapped_type
- unordered_map/std::unordered_multimap::mapped_type
- std::unordered_multimap::pointer
- unordered_map/std::unordered_multimap::pointer
- std::unordered_multimap::reference
- unordered_map/std::unordered_multimap::reference
- std::unordered_multimap::size_type
- unordered_map/std::unordered_multimap::size_type
- std::unordered_multimap::value_type
- unordered_map/std::unordered_multimap::value_type
- std::unordered_multimap::begin
- unordered_map/std::unordered_multimap::begin
- std::unordered_multimap::bucket
- unordered_map/std::unordered_multimap::bucket
- std::unordered_multimap::bucket_count
- unordered_map/std::unordered_multimap::bucket_count
- std::unordered_multimap::bucket_size
- unordered_map/std::unordered_multimap::bucket_size
- std::unordered_multimap::cbegin
- unordered_map/std::unordered_multimap::cbegin
- std::unordered_multimap::cend
- unordered_map/std::unordered_multimap::cend
- std::unordered_multimap::clear
- unordered_map/std::unordered_multimap::clear
- std::unordered_multimap::count
- unordered_map/std::unordered_multimap::count
- std::unordered_multimap::emplace
- unordered_map/std::unordered_multimap::emplace
- std::unordered_multimap::emplace_hint
- unordered_map/std::unordered_multimap::emplace_hint
- std::unordered_multimap::empty
- unordered_map/std::unordered_multimap::empty
- std::unordered_multimap::end
- unordered_map/std::unordered_multimap::end
- std::unordered_multimap::equal_range
- unordered_map/std::unordered_multimap::equal_range
- std::unordered_multimap::erase
- unordered_map/std::unordered_multimap::erase
- std::unordered_multimap::find
- unordered_map/std::unordered_multimap::find
- std::unordered_multimap::get_allocator
- unordered_map/std::unordered_multimap::get_allocator
- std::unordered_multimap::hash_function
- unordered_map/std::unordered_multimap::hash_function
- std::unordered_multimap::insert
- unordered_map/std::unordered_multimap::insert
- std::unordered_multimap::key_eq
- unordered_map/std::unordered_multimap::key_eq
- std::unordered_multimap::load_factor
- unordered_map/std::unordered_multimap::load_factor
- std::unordered_multimap::max_bucket_count
- unordered_map/std::unordered_multimap::max_bucket_count
- std::unordered_multimap::max_load_factor
- unordered_map/std::unordered_multimap::max_load_factor
- std::unordered_multimap::max_size
- unordered_map/std::unordered_multimap::max_size
- std::unordered_multimap::rehash
- unordered_map/std::unordered_multimap::rehash
- std::unordered_multimap::size
- unordered_map/std::unordered_multimap::size
- std::unordered_multimap::swap
- unordered_map/std::unordered_multimap::swap
- std::unordered_multimap::unordered_multimap
- unordered_map/std::unordered_multimap::unordered_multimap
- std::unordered_multimap::operator=
- unordered_map/std::unordered_multimap::operator=
dev_langs:
- C++
helpviewer_keywords:
- unordered_multimap class
ms.assetid: 4baead6c-5870-4b85-940f-a47d6b891c27
caps.latest.revision: 28
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 8c27a26f0e65066405694652be9d46937642043f
ms.lasthandoff: 02/24/2017

---
# <a name="unorderedmultimap-class"></a>unordered_multimap, classe
La classe de modèle décrit un objet qui contrôle une séquence de longueur variable constituée d'éléments de type `std::pair<const Key, Ty>`. La séquence est triée par ordre faible avec une fonction de hachage, qui partitionne la séquence en un ensemble trié de sous-séquences appelées compartiments. Dans chaque compartiment, une fonction de comparaison détermine si des paires d'éléments possèdent un ordre équivalent. Chaque élément stocke deux objets, une clé de tri et une valeur. La séquence est représentée de façon à permettre la recherche, l'insertion et la suppression d'un élément arbitraire à l'aide d'un certain nombre d'opérations qui peut être indépendant du nombre d'éléments de la séquence (temps constant), du moins lorsque les compartiments sont de longueur à peu près équivalente. Dans le pire des cas, lorsque tous les éléments se trouvent dans un compartiment, le nombre d'opérations est proportionnel au nombre d'éléments de la séquence (temps linéaire). De plus, l'insertion d'un élément n'entraîne pas la non validité des itérateurs, et la suppression d'un élément ne rend non valides que les itérateurs qui pointent vers l'élément supprimé.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class Key,  
    class Ty,  
    class Hash = std::hash<Key>,  
    class Pred = std::equal_to<Key>,  
    class Alloc = std::allocator<Key>>  
class unordered_multimap;  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`Key`|Type de clé.|  
|`Ty`|Type mappé.|  
|`Hash`|Type d’objet de la fonction de hachage.|  
|`Pred`|Type d’objet de fonction de comparaison d’égalité.|  
|`Alloc`|Classe allocator.|  
  
## <a name="members"></a>Membres  
  
|||  
|-|-|  
|Définition de types|Description|  
|[unordered_multimap::allocator_type](#unordered_multimap__allocator_type)|Type d’un allocateur pour la gestion du stockage.|  
|[unordered_multimap::const_iterator](#unordered_multimap__const_iterator)|Type d'un itérateur constant pour la séquence contrôlée.|  
|[unordered_multimap::const_local_iterator](#unordered_multimap__const_local_iterator)|Type d’un itérateur de compartiment constant pour la séquence contrôlée.|  
|[unordered_multimap::const_pointer](#unordered_multimap__const_pointer)|Type d'un pointeur constant vers un élément.|  
|[unordered_multimap::const_reference](#unordered_multimap__const_reference)|Type d'une référence constante à un élément.|  
|[unordered_multimap::difference_type](#unordered_multimap__difference_type)|Type d'une distance signée entre deux éléments.|  
|[unordered_multimap::hasher](#unordered_multimap__hasher)|Type de la fonction de hachage.|  
|[unordered_multimap::iterator](#unordered_multimap__iterator)|Type d'un itérateur pour la séquence contrôlée.|  
|[unordered_multimap::key_equal](#unordered_multimap__key_equal)|Type de la fonction de comparaison.|  
|[unordered_multimap::key_type](#unordered_multimap__key_type)|Type d'une clé de tri.|  
|[unordered_multimap::local_iterator](#unordered_multimap__local_iterator)|Type d'un itérateur de compartiment pour la séquence contrôlée.|  
|[unordered_multimap::mapped_type](#unordered_multimap__mapped_type)|Type d'une valeur mappée associée à chaque clé.|  
|[unordered_multimap::pointer](#unordered_multimap__pointer)|Type d'un pointeur vers un élément.|  
|[unordered_multimap::reference](#unordered_multimap__reference)|Type d'une référence à un élément.|  
|[unordered_multimap::size_type](#unordered_multimap__size_type)|Type d'une distance non signée entre deux éléments.|  
|[unordered_multimap::value_type](#unordered_multimap__value_type)|Type d’un élément.|  
  
|||  
|-|-|  
|Fonction membre|Description|  
|[unordered_multimap::begin](#unordered_multimap__begin)|Désigne le début de la séquence contrôlée.|  
|[unordered_multimap::bucket](#unordered_multimap__bucket)|Obtient le numéro du compartiment pour une valeur de clé.|  
|[unordered_multimap::bucket_count](#unordered_multimap__bucket_count)|Obtient le nombre de compartiments.|  
|[unordered_multimap::bucket_size](#unordered_multimap__bucket_size)|Obtient la taille d'un compartiment.|  
|[unordered_multimap::cbegin](#unordered_multimap__cbegin)|Désigne le début de la séquence contrôlée.|  
|[unordered_multimap::cend](#unordered_multimap__cend)|Désigne la fin de la séquence contrôlée.|  
|[unordered_multimap::clear](#unordered_multimap__clear)|Supprime tous les éléments.|  
|[unordered_multimap::count](#unordered_multimap__count)|Recherche le nombre d’éléments qui correspondent à une clé spécifiée.|  
|[unordered_multimap::emplace](#unordered_multimap__emplace)|Ajoute un élément construit sur place.|  
|[unordered_multimap::emplace_hint](#unordered_multimap__emplace_hint)|Ajoute un élément construit sur place, avec un indicateur.|  
|[unordered_multimap::empty](#unordered_multimap__empty)|Vérifie l'absence d'éléments.|  
|[unordered_multimap::end](#unordered_multimap__end)|Désigne la fin de la séquence contrôlée.|  
|[unordered_multimap::equal_range](#unordered_multimap__equal_range)|Recherche une plage qui correspond à une clé spécifiée.|  
|[unordered_multimap::erase](#unordered_multimap__erase)|Supprime les éléments placés aux positions spécifiées.|  
|[unordered_multimap::find](#unordered_multimap__find)|Recherche un élément qui correspond à une clé spécifiée.|  
|[unordered_multimap::get_allocator](#unordered_multimap__get_allocator)|Obtient l’objet allocateur stocké.|  
|[unordered_multimap::hash_function](#unordered_multimap__hash_function)|Obtient l'objet de fonction de hachage stocké.|  
|[unordered_multimap::insert](#unordered_multimap__insert)|Ajoute des éléments.|  
|[unordered_multimap::key_eq](#unordered_multimap__key_eq)|Obtient l'objet de fonction de comparaison stocké.|  
|[unordered_multimap::load_factor](#unordered_multimap__load_factor)|Compte le nombre moyen d'éléments par compartiment.|  
|[unordered_multimap::max_bucket_count](#unordered_multimap__max_bucket_count)|Obtient le nombre maximal de compartiments.|  
|[unordered_multimap::max_load_factor](#unordered_multimap__max_load_factor)|Obtient ou définit le nombre maximal d’éléments par compartiment.|  
|[unordered_multimap::max_size](#unordered_multimap__max_size)|Obtient ou définit la taille maximale de la séquence contrôlée.|  
|[unordered_multimap::rehash](#unordered_multimap__rehash)|Régénère la table de hachage.|  
|[unordered_multimap::size](#unordered_multimap__size)|Compte le nombre d'éléments.|  
|[unordered_multimap::swap](#unordered_multimap__swap)|Échange le contenu de deux conteneurs.|  
|[unordered_multimap::unordered_multimap](#unordered_multimap__unordered_multimap)|Construit un objet conteneur.|  
  
|||  
|-|-|  
|Opérateur|Description|  
|[unordered_multimap::operator=](#unordered_multimap__operator_eq)|Copie une table de hachage.|  
  
## <a name="remarks"></a>Notes  
 L’objet trie la séquence qu’il contrôle en appelant deux objets stockés, un objet de fonction de comparaison de type [unordered_multimap::key_equal](#unordered_multimap__key_equal) et un objet de fonction de hachage de type [unordered_multimap::hasher](#unordered_multimap__hasher). Pour accéder au premier objet stocké, appelez la fonction membre [unordered_multimap::key_eq](#unordered_multimap__key_eq)`()`. Pour accéder au second objet stocké, appelez la fonction membre [unordered_multimap::hash_function](#unordered_multimap__hash_function)`()`. Pour toutes les valeurs `X` et `Y` de type `Key`, l'appel `key_eq()(X, Y)` retourne true uniquement si les valeurs des deux arguments ont un classement équivalent. L'appel `hash_function()(keyval)` génère une distribution des valeurs de type `size_t`. Contrairement à la classe de modèle [unordered_map](../standard-library/unordered-map-class.md), un objet de classe de modèle `unordered_multimap` ne garantit pas que `key_eq()(X, Y)` a toujours la valeur false pour deux éléments quelconques de la séquence contrôlée. Il n'est pas nécessaire que les clés soient uniques.  
  
 L'objet stocke également un facteur de charge maximale, qui spécifie le nombre moyen maximal d'éléments souhaité par compartiment. Si après l’insertion d’un élément, [unordered_multimap::load_factor](#unordered_multimap__load_factor)`()` dépasse le facteur de charge maximale, le conteneur augmente le nombre de compartiments et reconstruit la table de hachage si nécessaire.  
  
 L'ordre réel des éléments de la séquence contrôlée dépend de la fonction de hachage, de la fonction de comparaison, de l'ordre d'insertion, du facteur de charge maximale et du nombre de compartiments. En général, il n'est pas possible de prévoir l'ordre des éléments de la séquence contrôlée. Toutefois, vous avez la garantie que tous les sous-ensembles d'éléments dont le classement est équivalent sont adjacents dans la séquence contrôlée.  
  
 L’objet alloue et libère du stockage pour la séquence qu’il contrôle via un objet allocateur stocké de type [unordered_multimap::allocator_type](#unordered_multimap__allocator_type). Un tel objet allocateur doit avoir la même interface externe qu'un objet de classe de modèle `allocator`. Notez que l'objet allocateur stocké n'est pas copié lorsque l'objet conteneur est assigné.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<unordered_map>  
  
 **Espace de noms :** std  
  
##  <a name="a-nameunorderedmultimapallocatortypea--unorderedmultimapallocatortype"></a><a name="unordered_multimap__allocator_type"></a>  unordered_multimap::allocator_type  
 Type d’un allocateur pour la gestion du stockage.  
  
```  
typedef Alloc allocator_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle `Alloc`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_allocator_type.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
typedef std::allocator<std::pair<const char, int> > Myalloc;   
int main()   
    {   
    Mymap c1;   
  
    Mymap::allocator_type al = c1.get_allocator();   
    std::cout << "al == std::allocator() is "   
        << std::boolalpha << (al == Myalloc()) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
al == std::allocator() is true  
```  
  
##  <a name="a-nameunorderedmultimapbegina--unorderedmultimapbegin"></a><a name="unordered_multimap__begin"></a>  unordered_multimap::begin  
 Désigne le début de la séquence contrôlée ou un compartiment.  
  
```  
iterator begin();

const_iterator begin() const;

 
local_iterator begin(size_type nbucket);

const_local_iterator begin(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`nbucket`|Numéro de compartiment.|  
  
### <a name="remarks"></a>Notes  
 Les deux premières fonctions membres retournent un itérateur vers l'avant qui pointe vers le premier élément de la séquence (ou juste après la fin d'une séquence vide). Les deux dernières fonctions membres retournent un itérateur vers l'avant qui pointe vers le premier élément du compartiment `nbucket` (ou juste après la fin d'un compartiment vide).  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_begin.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// inspect first two items " [c 3] [b 2]"   
    Mymap::iterator it2 = c1.begin();   
    std::cout << " [" << it2->first << ", " << it2->second << "]";   
    ++it2;   
    std::cout << " [" << it2->first << ", " << it2->second << "]";   
    std::cout << std::endl;   
  
// inspect bucket containing 'a'   
    Mymap::const_local_iterator lit = c1.begin(c1.bucket('a'));   
    std::cout << " [" << lit->first << ", " << lit->second << "]";   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
[c, 3] [b, 2]  
[a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapbucketa--unorderedmultimapbucket"></a><a name="unordered_multimap__bucket"></a>  unordered_multimap::bucket  
 Obtient le numéro du compartiment pour une valeur de clé.  
  
```  
size_type bucket(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `keyval`  
 Valeur de clé à mapper.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne le numéro de compartiment correspondant actuellement à la valeur de clé `keyval`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_bucket.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// display buckets for keys   
    Mymap::size_type bs = c1.bucket('a');   
    std::cout << "bucket('a') == " << bs << std::endl;   
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
bucket('a') == 7  
bucket_size(7) == 1  
```  
  
##  <a name="a-nameunorderedmultimapbucketcounta--unorderedmultimapbucketcount"></a><a name="unordered_multimap__bucket_count"></a>  unordered_multimap::bucket_count  
 Obtient le nombre de compartiments.  
  
```  
size_type bucket_count() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne le nombre actuel de comportements.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_bucket_count.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// inspect current parameters   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
// change max_load_factor and redisplay   
    c1.max_load_factor(0.10f);   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
// rehash and redisplay   
    c1.rehash(100);   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_bucket_count() == 128  
max_load_factor() == 0.1  
  
```  
  
##  <a name="a-nameunorderedmultimapbucketsizea--unorderedmultimapbucketsize"></a><a name="unordered_multimap__bucket_size"></a>  unordered_multimap::bucket_size  
 Obtient la taille d’un compartiment.  
  
```  
size_type bucket_size(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `nbucket`  
 Numéro de compartiment.  
  
### <a name="remarks"></a>Notes  
 Les fonctions membres retournent la taille du compartiment numéro `nbucket`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_bucket_size.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// display buckets for keys   
    Mymap::size_type bs = c1.bucket('a');   
    std::cout << "bucket('a') == " << bs << std::endl;   
    std::cout << "bucket_size(" << bs << ") == " << c1.bucket_size(bs)   
        << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
bucket('a') == 7  
bucket_size(7) == 1  
```  
  
##  <a name="a-nameunorderedmultimapcbegina--unorderedmultimapcbegin"></a><a name="unordered_multimap__cbegin"></a>  unordered_multimap::cbegin  
 Retourne un itérateur `const` qui traite le premier élément d'une plage.  
  
```  
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur forward `const` qui pointe vers le premier élément de la plage, ou vers l'emplacement situé juste après la fin d'une plage vide (pour une plage vide : `cbegin() == cend()`).  
  
### <a name="remarks"></a>Notes  
 Avec la valeur de retour `cbegin`, les éléments de la plage ne peuvent pas être modifiés.  
  
 Vous pouvez utiliser cette fonction membre à la place de la fonction membre `begin()` afin de garantir que la valeur de retour est `const_iterator`. En général, elle est utilisée conjointement au mot clé de déduction de type [auto](../cpp/auto-cpp.md), comme le montre l’exemple suivant. Dans cet exemple, il est supposé que `Container` est un conteneur modifiable (autre que `const`) de tout type, prenant en charge `begin()` et `cbegin()`.  
  
```cpp  
auto i1 = Container.begin();
// i1 is Container<T>::iterator   
auto i2 = Container.cbegin();

// i2 is Container<T>::const_iterator  
```  
  
##  <a name="a-nameunorderedmultimapcenda--unorderedmultimapcend"></a><a name="unordered_multimap__cend"></a>  unordered_multimap::cend  
 Retourne un itérateur `const` qui traite l'emplacement situé immédiatement après le dernier élément d'une plage.  
  
```  
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur forward `const` qui pointe juste après la fin de la plage.  
  
### <a name="remarks"></a>Notes  
 `cend` est utilisé pour vérifier si un itérateur a dépassé la fin de la plage.  
  
 Vous pouvez utiliser cette fonction membre à la place de la fonction membre `end()` afin de garantir que la valeur de retour est `const_iterator`. En général, elle est utilisée conjointement au mot clé de déduction de type [auto](../cpp/auto-cpp.md), comme le montre l’exemple suivant. Dans cet exemple, il est supposé que `Container` est un conteneur modifiable (autre que `const`) de tout type prenant en charge `end()` et `cend()`.  
  
```cpp  
auto i1 = Container.end();
// i1 is Container<T>::iterator   
auto i2 = Container.cend();

// i2 is Container<T>::const_iterator  
```  
  
 La valeur retournée par `cend` ne doit pas être déréférencée.  
  
##  <a name="a-nameunorderedmultimapcleara--unorderedmultimapclear"></a><a name="unordered_multimap__clear"></a>  unordered_multimap::clear  
 Supprime tous les éléments.  
  
```  
void clear();
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre appelle [unordered_multimap::erase](#unordered_multimap__erase)`(` [unordered_multimap::begin](#unordered_multimap__begin)`(),` [unordered_multimap::end](#unordered_multimap__end)`())`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_clear.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// clear the container and reinspect   
    c1.clear();   
    std::cout << "size == " << c1.size() << std::endl;   
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;   
    std::cout << std::endl;   
  
    c1.insert(Mymap::value_type('d', 4));   
    c1.insert(Mymap::value_type('e', 5));   
  
// display contents " [e 5] [d 4]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    std::cout << "size == " << c1.size() << std::endl;   
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
size == 0  
empty() == true  
  
 [e, 5] [d, 4]  
size == 2  
empty() == false  
```  
  
##  <a name="a-nameunorderedmultimapconstiteratora--unorderedmultimapconstiterator"></a><a name="unordered_multimap__const_iterator"></a>  unordered_multimap::const_iterator  
 Type d'un itérateur constant pour la séquence contrôlée.  
  
```  
typedef T1 const_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir d'itérateur vers l'avant constant pour la séquence contrôlée. Il est décrit ici comme un synonyme du type défini par l'implémentation `T1`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_const_iterator.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapconstlocaliteratora--unorderedmultimapconstlocaliterator"></a><a name="unordered_multimap__const_local_iterator"></a>  unordered_multimap::const_local_iterator  
 Type d’un itérateur de compartiment constant pour la séquence contrôlée.  
  
```  
typedef T5 const_local_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir d’itérateur de constante vers l’avant pour un compartiment. Il est décrit ici comme un synonyme du type défini par l’implémentation `T5`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_const_local_iterator.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// inspect bucket containing 'a'   
    Mymap::const_local_iterator lit = c1.begin(c1.bucket('a'));   
    std::cout << " [" << lit->first << ", " << lit->second << "]";   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
[a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapconstpointera--unorderedmultimapconstpointer"></a><a name="unordered_multimap__const_pointer"></a>  unordered_multimap::const_pointer  
 Type d'un pointeur constant vers un élément.  
  
```  
typedef Alloc::const_pointer const_pointer;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir de pointeur constant à un élément de la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_const_pointer.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   
        Mymap::const_pointer p = &*it;   
        std::cout << " [" << p->first << ", " << p->second << "]";   
        }   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapconstreferencea--unorderedmultimapconstreference"></a><a name="unordered_multimap__const_reference"></a>  unordered_multimap::const_reference  
 Type d'une référence constante à un élément.  
  
```  
typedef Alloc::const_reference const_reference;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir de référence constante à un élément de la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_const_reference.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   
        Mymap::const_reference ref = *it;   
        std::cout << " [" << ref.first << ", " << ref.second << "]";   
        }   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapcounta--unorderedmultimapcount"></a><a name="unordered_multimap__count"></a>  unordered_multimap::count  
 Recherche le nombre d’éléments qui correspondent à une clé spécifiée.  
  
```  
size_type count(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `keyval`  
 Valeur de clé à rechercher.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne le nombre d’éléments dans la plage délimitée par [unordered_multimap::equal_range](#unordered_multimap__equal_range)`(keyval)`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_count.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    std::cout << "count('A') == " << c1.count('A') << std::endl;   
    std::cout << "count('b') == " << c1.count('b') << std::endl;   
    std::cout << "count('C') == " << c1.count('C') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
count('A') == 0  
count('b') == 1  
count('C') == 0  
```  
  
##  <a name="a-nameunorderedmultimapdifferencetypea--unorderedmultimapdifferencetype"></a><a name="unordered_multimap__difference_type"></a>  unordered_multimap::difference_type  
 Type d'une distance signée entre deux éléments.  
  
```  
typedef T3 difference_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type d'entier signé décrit un objet qui peut représenter la différence entre les adresses de deux éléments quelconques dans la séquence contrôlée. Il est décrit ici comme un synonyme du type défini par l'implémentation `T3`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_difference_type.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// compute positive difference   
    Mymap::difference_type diff = 0;   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        ++diff;   
    std::cout << "end()-begin() == " << diff << std::endl;   
  
// compute negative difference   
    diff = 0;   
    for (Mymap::const_iterator it = c1.end();   
        it != c1.begin(); --it)   
        --diff;   
    std::cout << "begin()-end() == " << diff << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
end()-begin() == 3  
begin()-end() == -3  
```  
  
##  <a name="a-nameunorderedmultimapemplacea--unorderedmultimapemplace"></a><a name="unordered_multimap__emplace"></a>  unordered_multimap::emplace  
 Insère un élément construit sur place (aucune opération de copie ni de déplacement n’est effectuée) avec un indicateur de positionnement.  
  
```  
template <class... Args>  
iterator emplace(Args&&... args);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`args`|Les arguments transférés pour construire un élément à insérer dans la classe unordered_multimap.|  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur vers l’élément qui vient d’être inséré.  
  
### <a name="remarks"></a>Remarques  
 Aucune référence aux éléments conteneurs n’est invalidée par cette fonction, mais elle peut invalider tous les itérateurs du conteneur.  
  
 Le [value_type](../standard-library/map-class.md#map__value_type) d’un élément est une paire, si bien que la valeur d’un élément est une paire ordonnée dont le premier composant est égal à la valeur de clé et le deuxième à la valeur de données de l’élément.  
  
 Durant l’insertion, si une exception est levée mais qu’elle ne se produit pas dans la fonction de hachage du conteneur, le conteneur n’est pas modifié. Si l'exception est levée dans la fonction de hachage, le résultat n'est pas défini.  
  
 Pour obtenir un exemple de code, consultez [multimap::emplace](../standard-library/multimap-class.md#multimap__emplace).  
  
##  <a name="a-nameunorderedmultimapemplacehinta--unorderedmultimapemplacehint"></a><a name="unordered_multimap__emplace_hint"></a>  unordered_multimap::emplace_hint  
 Insère un élément construit sur place (aucune opération de copie ni de déplacement n’est effectuée) avec un indicateur de positionnement.  
  
```  
template <class... Args>  
iterator emplace_hint(
    const_iterator where,  
    Args&&... args);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`args`|Les arguments transférés pour construire un élément à insérer dans la classe unordered.|  
|`where`|Indicateur concernant l’emplacement où commencer à rechercher le point d’insertion correct.|  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur vers l’élément qui vient d’être inséré.  
  
### <a name="remarks"></a>Remarques  
 Aucune référence aux éléments conteneurs n’est invalidée par cette fonction, mais elle peut invalider tous les itérateurs du conteneur.  
  
 Durant l’insertion, si une exception est levée mais qu’elle ne se produit pas dans la fonction de hachage du conteneur, le conteneur n’est pas modifié. Si l'exception est levée dans la fonction de hachage, le résultat n'est pas défini.  
  
 Le [value_type](../standard-library/map-class.md#map__value_type) d’un élément est une paire, si bien que la valeur d’un élément est une paire ordonnée dont le premier composant est égal à la valeur de clé et le deuxième à la valeur de données de l’élément.  
  
 Pour obtenir un exemple de code, consultez [map::emplace_hint](../standard-library/map-class.md#map__emplace_hint).  
  
##  <a name="a-nameunorderedmultimapemptya--unorderedmultimapempty"></a><a name="unordered_multimap__empty"></a>  unordered_multimap::empty  
 Vérifie l'absence d'éléments.  
  
```  
bool empty() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne la valeur true pour une séquence contrôlée vide.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_empty.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// clear the container and reinspect   
    c1.clear();   
    std::cout << "size == " << c1.size() << std::endl;   
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;   
    std::cout << std::endl;   
  
    c1.insert(Mymap::value_type('d', 4));   
    c1.insert(Mymap::value_type('e', 5));   
  
// display contents " [e 5] [d 4]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    std::cout << "size == " << c1.size() << std::endl;   
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
size == 0  
empty() == true  
  
 [e, 5] [d, 4]  
size == 2  
empty() == false  
```  
  
##  <a name="a-nameunorderedmultimapenda--unorderedmultimapend"></a><a name="unordered_multimap__end"></a>  unordered_multimap::end  
 Désigne la fin de la séquence contrôlée.  
  
```  
iterator end();

const_iterator end() const;

 
local_iterator end(size_type nbucket);

const_local_iterator end(size_type nbucket) const;
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`nbucket`|Numéro de compartiment.|  
  
### <a name="remarks"></a>Notes  
 Les deux premières fonctions membres retournent un itérateur vers l'avant qui pointe juste après la fin de la séquence. Les deux dernières fonctions membres retournent un itérateur vers l'avant qui pointe juste après la fin du compartiment `nbucket`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_end.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// inspect last two items " [a 1] [b 2]"   
    Mymap::iterator it2 = c1.end();   
    --it2;   
    std::cout << " [" << it2->first << ", " << it2->second << "]";   
    --it2;   
    std::cout << " [" << it2->first << ", " << it2->second << "]";   
    std::cout << std::endl;   
  
// inspect bucket containing 'a'   
    Mymap::const_local_iterator lit = c1.end(c1.bucket('a'));   
    --lit;   
    std::cout << " [" << lit->first << ", " << lit->second << "]";   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
[a, 1] [b, 2]  
[a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapequalrangea--unorderedmultimapequalrange"></a><a name="unordered_multimap__equal_range"></a>  unordered_multimap::equal_range  
 Recherche une plage qui correspond à une clé spécifiée.  
  
```  
std::pair<iterator, iterator>  
    equal_range(const Key& keyval);

std::pair<const_iterator, const_iterator>  
    equal_range(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `keyval`  
 Valeur de clé à rechercher.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne une paire d’itérateurs `X` tel que `[X.first, X.second)` délimite uniquement les éléments de la séquence contrôlée qui ont un classement équivalent à `keyval`. Si aucun de ces éléments n’existe, les deux itérateurs sont `end()`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_equal_range.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// display results of failed search   
    std::pair<Mymap::iterator, Mymap::iterator> pair1 =   
        c1.equal_range('x');   
    std::cout << "equal_range('x'):";   
    for (; pair1.first != pair1.second; ++pair1.first)   
        std::cout << " [" << pair1.first->first   
            << ", " << pair1.first->second << "]";   
    std::cout << std::endl;   
  
// display results of successful search   
    pair1 = c1.equal_range('b');   
    std::cout << "equal_range('b'):";   
    for (; pair1.first != pair1.second; ++pair1.first)   
        std::cout << " [" << pair1.first->first   
            << ", " << pair1.first->second << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
equal_range('x'):  
equal_range('b'): [b, 2]  
```  
  
##  <a name="a-nameunorderedmultimaperasea--unorderedmultimaperase"></a><a name="unordered_multimap__erase"></a>  unordered_multimap::erase  
 Supprime un élément ou une plage d’éléments dans une classe unordered_multimap aux positions spécifiées ou supprime les éléments qui correspondent à une clé spécifiée.  
  
```  
iterator erase(
    const_iterator Where);

iterator erase(
    const_iterator First,  
    const_iterator Last);

size_type erase(
    const key_type& Key);
```  
  
### <a name="parameters"></a>Paramètres  
 `Where`  
 Position de l’élément à supprimer.  
  
 `First`  
 Position du premier élément à supprimer.  
  
 `Last`  
 Position juste après le dernier élément à supprimer.  
  
 `Key`  
 Valeur de clé des éléments à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 Pour les deux premières fonctions membres, un itérateur bidirectionnel qui désigne le premier élément restant après tous les éléments supprimés, ou un élément à la fin de la classe map si aucun élément de ce type n’existe.  
  
 Pour la troisième fonction membre, retourne le nombre d’éléments qui ont été supprimés de la classe unordered_multimap.  
  
### <a name="remarks"></a>Notes  
 Pour obtenir un exemple de code, consultez [map::erase](../standard-library/map-class.md#map__erase).  
  
##  <a name="a-nameunorderedmultimapfinda--unorderedmultimapfind"></a><a name="unordered_multimap__find"></a>  unordered_multimap::find  
 Recherche un élément qui correspond à une clé spécifiée.  
  
```  
const_iterator find(const Key& keyval) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `keyval`  
 Valeur de clé à rechercher.  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne [unordered_multimap::equal_range](#unordered_multimap__equal_range)`(keyval).first`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_find.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// try to find and fail   
    std::cout << "find('A') == "   
        << std::boolalpha << (c1.find('A') != c1.end()) << std::endl;   
  
// try to find and succeed   
    Mymap::iterator it = c1.find('b');   
    std::cout << "find('b') == "   
        << std::boolalpha << (it != c1.end())   
        << ": [" << it->first << ", " << it->second << "]" << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
find('A') == false  
find('b') == true: [b, 2]  
```  
  
##  <a name="a-nameunorderedmultimapgetallocatora--unorderedmultimapgetallocator"></a><a name="unordered_multimap__get_allocator"></a>  unordered_multimap::get_allocator  
 Obtient l’objet allocateur stocké.  
  
```  
Alloc get_allocator() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne l’objet d’allocateur stocké.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_get_allocator.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
typedef std::allocator<std::pair<const char, int> > Myalloc;   
int main()   
    {   
    Mymap c1;   
  
    Mymap::allocator_type al = c1.get_allocator();   
    std::cout << "al == std::allocator() is "   
        << std::boolalpha << (al == Myalloc()) << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
al == std::allocator() is true  
```  
  
##  <a name="a-nameunorderedmultimaphashfunctiona--unorderedmultimaphashfunction"></a><a name="unordered_multimap__hash_function"></a>  unordered_multimap::hash_function  
 Obtient l'objet de fonction de hachage stocké.  
  
```  
Hash hash_function() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne l’objet de fonction de hachage stocké.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_hash_function.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    Mymap::hasher hfn = c1.hash_function();   
    std::cout << "hfn('a') == " << hfn('a') << std::endl;   
    std::cout << "hfn('b') == " << hfn('b') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
hfn('a') == 1630279  
hfn('b') == 1647086  
```  
  
##  <a name="a-nameunorderedmultimaphashera--unorderedmultimaphasher"></a><a name="unordered_multimap__hasher"></a>  unordered_multimap::hasher  
 Type de la fonction de hachage.  
  
```  
typedef Hash hasher;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle `Hash`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_hasher.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    Mymap::hasher hfn = c1.hash_function();   
    std::cout << "hfn('a') == " << hfn('a') << std::endl;   
    std::cout << "hfn('b') == " << hfn('b') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
hfn('a') == 1630279  
hfn('b') == 1647086  
```  
  
##  <a name="a-nameunorderedmultimapinserta--unorderedmultimapinsert"></a><a name="unordered_multimap__insert"></a>  unordered_multimap::insert  
 Insère un élément ou une plage d'éléments dans une classe unordered_multimap.  
  
```  
// (1) single element  
pair<iterator, bool> insert(
    const value_type& Val);

 
// (2) single element, perfect forwarded  
template <class ValTy>  
pair<iterator, bool>  
insert(
    ValTy&& Val);

 
// (3) single element with hint  
iterator insert(
    const_iterator Where,  
    const value_type& Val);

 
// (4) single element, perfect forwarded, with hint  
template <class ValTy>  
iterator insert(
    const_iterator Where,  
    ValTy&& Val);

 
// (5) range   
template <class InputIterator>   
void insert(
    InputIterator First,  
    InputIterator Last);

 
// (6) initializer list  
void insert(
    initializer_list<value_type>  
IList);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`Val`|Valeur d'un élément à insérer dans la classe unordered_multimap.|  
|`Where`|Emplacement où commencer à rechercher le point d'insertion correct.|  
|`ValTy`|Paramètre de modèle qui spécifie le type d’argument que la classe unordered_multimap peut utiliser pour construire un élément de [value_type](../standard-library/map-class.md#map__value_type) et effectue un transfert parfait de `Val` comme argument.|  
|`First`|Position du premier élément à copier.|  
|`Last`|Position juste au-delà du dernier élément à copier.|  
|`InputIterator`|Argument de fonction de modèle qui remplit les conditions requises par un [itérateur d’entrée](../standard-library/input-iterator-tag-struct.md) qui pointe vers des éléments d’un type pouvant servir à construire des objets [value_type](../standard-library/map-class.md#map__value_type).|  
|`IList`|[initializer_list](../standard-library/initializer-list.md) à partir de laquelle copier les éléments.|  
  
### <a name="return-value"></a>Valeur de retour  
 Les fonctions membres d'insertion à un élément, (1) et (2), retournent un itérateur vers l'emplacement où le nouvel élément a été inséré dans la classe unordered_multimap.  
  
 Les fonctions membres à un élément avec indicateur, (3) et (4), retournent un itérateur qui pointe vers l'emplacement où le nouvel élément a été inséré dans la classe unordered_multimap.  
  
### <a name="remarks"></a>Notes  
 Aucun pointeur ou référence n'est invalidé par cette fonction, mais elle peut invalider tous les itérateurs du conteneur.  
  
 Durant l'insertion d'un seul élément, si une exception est levée mais qu'elle ne se produit pas dans la fonction de hachage du conteneur, l'état du conteneur n'est pas modifié. Si l'exception est levée dans la fonction de hachage, le résultat n'est pas défini. Durant l'insertion de plusieurs éléments, si une exception est levée, le conteneur reste dans un état non spécifié mais valide.  
  
 Le [value_type](../standard-library/map-class.md#map__value_type) d’un conteneur est un typedef qui appartient au conteneur et, pour la classe map, `map<K, V>::value_type` est `pair<const K, V>`. La valeur d'un élément est une paire ordonnée dans laquelle le premier composant est égal à la valeur de clé et le second composant est égal à la valeur de données de l'élément.  
  
 La fonction membre de plage (5) insère la séquence de valeurs d'éléments dans une classe unordered_multimap qui correspond à chaque élément traité par un itérateur dans la plage `[First, Last)` ; ainsi, `Last` n'est pas inséré. La fonction membre de conteneur `end()` fait référence à la position qui suit le dernier élément du conteneur. Par exemple, l'instruction `m.insert(v.begin(), v.end());` insère tous les éléments de `v` dans `m`.  
  
 La fonction membre de liste d’initialiseurs (6) utilise un objet [initializer_list](../standard-library/initializer-list.md) pour copier des éléments dans l’objet unordered_multimap.  
  
 Pour l’insertion d’un élément construit sur place (aucune opération de copie ni de déplacement n’est effectuée), consultez [unordered_multimap::emplace](#unordered_multimap__emplace) et [unordered_multimap::emplace_hint](#unordered_multimap__emplace_hint).  
  
 Pour obtenir un exemple de code, consultez [multimap::insert](../standard-library/multiset-class.md#multiset__insert).  
  
##  <a name="a-nameunorderedmultimapiteratora--unorderedmultimapiterator"></a><a name="unordered_multimap__iterator"></a>  unordered_multimap::iterator  
 Type d'un itérateur pour la séquence contrôlée.  
  
```  
typedef T0 iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir d’itérateur forward pour la séquence contrôlée. Il est décrit ici comme un synonyme du type défini par l'implémentation `T0`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_iterator.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapkeyeqa--unorderedmultimapkeyeq"></a><a name="unordered_multimap__key_eq"></a>  unordered_multimap::key_eq  
 Obtient l'objet de fonction de comparaison stocké.  
  
```  
Pred key_eq() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne l’objet de fonction de comparaison stocké.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_key_eq.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    Mymap::key_equal cmpfn = c1.key_eq();   
    std::cout << "cmpfn('a', 'a') == "   
        << std::boolalpha << cmpfn('a', 'a') << std::endl;   
    std::cout << "cmpfn('a', 'b') == "   
        << std::boolalpha << cmpfn('a', 'b') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
cmpfn('a', 'a') == true  
cmpfn('a', 'b') == false  
```  
  
##  <a name="a-nameunorderedmultimapkeyequala--unorderedmultimapkeyequal"></a><a name="unordered_multimap__key_equal"></a>  unordered_multimap::key_equal  
 Type de la fonction de comparaison.  
  
```  
typedef Pred key_equal;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle `Pred`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_key_equal.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    Mymap::key_equal cmpfn = c1.key_eq();   
    std::cout << "cmpfn('a', 'a') == "   
        << std::boolalpha << cmpfn('a', 'a') << std::endl;   
    std::cout << "cmpfn('a', 'b') == "   
        << std::boolalpha << cmpfn('a', 'b') << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
cmpfn('a', 'a') == true  
cmpfn('a', 'b') == false  
```  
  
##  <a name="a-nameunorderedmultimapkeytypea--unorderedmultimapkeytype"></a><a name="unordered_multimap__key_type"></a>  unordered_multimap::key_type  
 Type d'une clé de tri.  
  
```  
typedef Key key_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle `Key`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_key_type.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// add a value and reinspect   
    Mymap::key_type key = 'd';   
    Mymap::mapped_type mapped = 4;   
    Mymap::value_type val = Mymap::value_type(key, mapped);   
    c1.insert(val);   
  
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
[d, 4] [c, 3] [b, 2] [a, 1]  
```  
  
##  <a name="a-nameunorderedmultimaploadfactora--unorderedmultimaploadfactor"></a><a name="unordered_multimap__load_factor"></a>  unordered_multimap::load_factor  
 Compte le nombre moyen d'éléments par compartiment.  
  
```  
float load_factor() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne `(float)`[unordered_multimap::size](#unordered_multimap__size)`() / (float)`[unordered_multimap::bucket_count](#unordered_multimap__bucket_count)`()`, le nombre moyen d’éléments par compartiment.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_load_factor.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// inspect current parameters   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
// change max_load_factor and redisplay   
    c1.max_load_factor(0.10f);   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
// rehash and redisplay   
    c1.rehash(100);   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
##  <a name="a-nameunorderedmultimaplocaliteratora--unorderedmultimaplocaliterator"></a><a name="unordered_multimap__local_iterator"></a>  unordered_multimap::local_iterator  
 Type d'un itérateur de compartiment.  
  
```  
typedef T4 local_iterator;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir d'itérateur vers l'avant pour un compartiment. Il est décrit ici comme un synonyme du type défini par l'implémentation `T4`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_local_iterator.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// inspect bucket containing 'a'   
    Mymap::local_iterator lit = c1.begin(c1.bucket('a'));   
    std::cout << " [" << lit->first << ", " << lit->second << "]";   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
[a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapmappedtypea--unorderedmultimapmappedtype"></a><a name="unordered_multimap__mapped_type"></a>  unordered_multimap::mapped_type  
 Type d'une valeur mappée associée à chaque clé.  
  
```  
typedef Ty mapped_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type est un synonyme du paramètre de modèle `Ty`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_mapped_type.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// add a value and reinspect   
    Mymap::key_type key = 'd';   
    Mymap::mapped_type mapped = 4;   
    Mymap::value_type val = Mymap::value_type(key, mapped);   
    c1.insert(val);   
  
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
[d, 4] [c, 3] [b, 2] [a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapmaxbucketcounta--unorderedmultimapmaxbucketcount"></a><a name="unordered_multimap__max_bucket_count"></a>  unordered_multimap::max_bucket_count  
 Obtient le nombre maximal de compartiments.  
  
```  
size_type max_bucket_count() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne le nombre maximal de compartiments actuellement autorisés.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_max_bucket_count.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// inspect current parameters   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
// change max_load_factor and redisplay   
    c1.max_load_factor(0.10f);   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
// rehash and redisplay   
    c1.rehash(100);   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_bucket_count() == 128  
max_load_factor() == 0.1  
  
```  
  
##  <a name="a-nameunorderedmultimapmaxloadfactora--unorderedmultimapmaxloadfactor"></a><a name="unordered_multimap__max_load_factor"></a>  unordered_multimap::max_load_factor  
 Obtient ou définit le nombre maximal d’éléments par compartiment.  
  
```  
float max_load_factor() const;

 
void max_load_factor(float factor);
```  
  
### <a name="parameters"></a>Paramètres  
 `factor`  
 Nouveau facteur de charge maximale.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre retourne le facteur de charge maximale stockée. La seconde fonction membre retourne le facteur de charge maximale stockée avec `factor`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_max_load_factor.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// inspect current parameters   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
// change max_load_factor and redisplay   
    c1.max_load_factor(0.10f);   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
// rehash and redisplay   
    c1.rehash(100);   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_bucket_count() == "   
        << c1.max_bucket_count() << std::endl;   
    std::cout << "max_load_factor() == "   
        << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_bucket_count() == 8  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_bucket_count() == 128  
max_load_factor() == 0.1  
  
```  
  
##  <a name="a-nameunorderedmultimapmaxsizea--unorderedmultimapmaxsize"></a><a name="unordered_multimap__max_size"></a>  unordered_multimap::max_size  
 Obtient ou définit la taille maximale de la séquence contrôlée.  
  
```  
size_type max_size() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne la longueur de la séquence la plus longue que l'objet peut contrôler.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_max_size.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    std::cout << "max_size() == " << c1.max_size() << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
max_size() == 536870911  
```  
  
##  <a name="a-nameunorderedmultimapoperatoreqa--unorderedmultimapoperator"></a><a name="unordered_multimap__operator_eq"></a>  unordered_multimap::operator=  
 Copie une table de hachage.  
  
```  
unordered_multimap& operator=(const unordered_multimap& right);

unordered_multimap& operator=(unordered_multimap&& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|` right`|unordered_multimap qui est copié dans le unordered_multimap.|  
  
### <a name="remarks"></a>Notes  
 Après l'effacement des éléments existants dans un unordered_multimap, `operator=` copie ou déplace le contenu de ` right` dans le unordered_multimap.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// unordered_multimap_operator_as.cpp  
// compile with: /EHsc  
#include <unordered_multimap>  
#include <iostream>  
  
int main( )  
   {  
   using namespace std;  
   unordered_multimap<int, int> v1, v2, v3;  
   unordered_multimap<int, int>::iterator iter;  
  
   v1.insert(pair<int, int>(1, 10));  
  
   cout << "v1 = " ;  
   for (iter = v1.begin(); iter != v1.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
  
   v2 = v1;  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
  
// move v1 into v2  
   v2.clear();  
   v2 = move(v1);  
   cout << "v2 = ";  
   for (iter = v2.begin(); iter != v2.end(); iter++)  
      cout << iter->second << " ";  
   cout << endl;  
   }  
```  
  
##  <a name="a-nameunorderedmultimappointera--unorderedmultimappointer"></a><a name="unordered_multimap__pointer"></a>  unordered_multimap::pointer  
 Type d'un pointeur vers un élément.  
  
```  
typedef Alloc::pointer pointer;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet pouvant servir de pointeur vers un élément de la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_pointer.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   
        Mymap::pointer p = &*it;   
        std::cout << " [" << p->first << ", " << p->second << "]";   
        }   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapreferencea--unorderedmultimapreference"></a><a name="unordered_multimap__reference"></a>  unordered_multimap::reference  
 Type d'une référence à un élément.  
  
```  
typedef Alloc::reference reference;  
```  
  
### <a name="remarks"></a>Notes  
 Le type décrit un objet qui peut servir de référence à un élément de la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_reference.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::iterator it = c1.begin();   
        it != c1.end(); ++it)   
        {   
        Mymap::reference ref = *it;   
        std::cout << " [" << ref.first << ", " << ref.second << "]";   
        }   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
```  
  
##  <a name="a-nameunorderedmultimaprehasha--unorderedmultimaprehash"></a><a name="unordered_multimap__rehash"></a>  unordered_multimap::rehash  
 Régénère la table de hachage.  
  
```  
void rehash(size_type nbuckets);
```  
  
### <a name="parameters"></a>Paramètres  
 `nbuckets`  
 Nombre de compartiments demandés.  
  
### <a name="remarks"></a>Notes  
 La fonction membre modifie le nombre de compartiments pour qu’il soit au moins égal à `nbuckets` et régénère la table de hachage en fonction des besoins.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_rehash.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// inspect current parameters   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
// change max_load_factor and redisplay   
    c1.max_load_factor(0.10f);   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;   
    std::cout << std::endl;   
  
// rehash and redisplay   
    c1.rehash(100);   
    std::cout << "bucket_count() == " << c1.bucket_count() << std::endl;   
    std::cout << "load_factor() == " << c1.load_factor() << std::endl;   
    std::cout << "max_load_factor() == " << c1.max_load_factor() << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
bucket_count() == 8  
load_factor() == 0.375  
max_load_factor() == 4  
  
bucket_count() == 8  
load_factor() == 0.375  
max_load_factor() == 0.1  
  
bucket_count() == 128  
load_factor() == 0.0234375  
max_load_factor() == 0.1  
```  
  
##  <a name="a-nameunorderedmultimapsizea--unorderedmultimapsize"></a><a name="unordered_multimap__size"></a>  unordered_multimap::size  
 Compte le nombre d'éléments.  
  
```  
size_type size() const;
```  
  
### <a name="remarks"></a>Notes  
 La fonction membre retourne la longueur de la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_size.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// clear the container and reinspect   
    c1.clear();   
    std::cout << "size == " << c1.size() << std::endl;   
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;   
    std::cout << std::endl;   
  
    c1.insert(Mymap::value_type('d', 4));   
    c1.insert(Mymap::value_type('e', 5));   
  
// display contents " [e 5] [d 4]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    std::cout << "size == " << c1.size() << std::endl;   
    std::cout << "empty() == " << std::boolalpha << c1.empty() << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
 [c, 3] [b, 2] [a, 1]  
size == 0  
empty() == true  
  
 [e, 5] [d, 4]  
size == 2  
empty() == false  
```  
  
##  <a name="a-nameunorderedmultimapsizetypea--unorderedmultimapsizetype"></a><a name="unordered_multimap__size_type"></a>  unordered_multimap::size_type  
 Type d'une distance non signée entre deux éléments.  
  
```  
typedef T2 size_type;  
```  
  
### <a name="remarks"></a>Notes  
 Le type d'entier non signé décrit un objet qui peut représenter la longueur de n'importe quelle séquence contrôlée. Il est décrit ici comme un synonyme du type défini par l'implémentation `T2`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_size_type.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
    Mymap::size_type sz = c1.size();   
  
    std::cout << "size == " << sz << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
size == 0  
```  
  
##  <a name="a-nameunorderedmultimapswapa--unorderedmultimapswap"></a><a name="unordered_multimap__swap"></a>  unordered_multimap::swap  
 Échange le contenu de deux conteneurs.  
  
```  
void swap(unordered_multimap& right);
```  
  
### <a name="parameters"></a>Paramètres  
 `right`  
 Conteneur avec lequel faire l’échange.  
  
### <a name="remarks"></a>Notes  
 La fonction membre échange les séquences contrôlées entre `*this` et `right`. Si [unordered_multimap::get_allocator](#unordered_multimap__get_allocator)`() == right.get_allocator()`, elle le fait en un temps constant, elle lève une exception seulement dans le cas de la copie de l’objet traits stocké de type `Tr`, et n’invalide aucune référence, ni aucun pointeur ou itérateur, qui désigne des éléments dans les deux séquences contrôlées. Sinon, elle effectue un nombre d’affectations d’éléments et d’appels de constructeurs proportionnel au nombre d’éléments dans les deux séquences contrôlées.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_swap.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    Mymap c2;   
  
    c2.insert(Mymap::value_type('d', 4));   
    c2.insert(Mymap::value_type('e', 5));   
    c2.insert(Mymap::value_type('f', 6));   
  
    c1.swap(c2);   
  
// display contents " [f 6] [e 5] [d 4]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    swap(c1, c2);   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
[f, 6] [e, 5] [d, 4]  
[c, 3] [b, 2] [a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapunorderedmultimapa--unorderedmultimapunorderedmultimap"></a><a name="unordered_multimap__unordered_multimap"></a>  unordered_multimap::unordered_multimap  
 Construit un objet conteneur.  
  
```  
unordered_multimap(
    const unordered_multimap& Right);

explicit unordered_multimap(
    size_type Bucket_count = N0,  
    const Hash& Hash = Hash(),  
    const Comp& Comp = Pred(),  
    const Allocator& Al = Alloc());

unordered_multimap(
    unordered_multimap&& Right);

unordered_multimap(
    initializer_list<Type> IList);

unordered_multimap(
    initializer_list<Type> IList,  
    size_type Bucket_count);

unordered_multimap(
    initializer_list<Type> IList,  
    size_type Bucket_count,   
    const Hash& Hash);

unordered_multimap(
    initializer_list<Type> IList,  
    size_type Bucket_count,   
    const Hash& Hash,  
    const Key& Key);

unordered_multimap(
    initializer_list<Type> IList,  
    size_type Bucket_count,   
    const Hash& Hash,  
    const Key& Key,   
    const Allocator& Al);

template <class InputIterator>  
unordered_multimap(
 InputIterator first, InputIterator last,  
    size_type Bucket_count = N0,  
    const Hash& Hash = Hash(),  
    const Comp& Comp = Pred(),  
    const Allocator& Al = Alloc());
```  
  
### <a name="parameters"></a>Paramètres  
  
|||  
|-|-|  
|Paramètre|Description|  
|`InputIterator`|Type d'itérateur.|  
|`Al`|Objet allocateur à stocker.|  
|`Comp`|Objet de fonction de comparaison à stocker.|  
|`Hash`|Objet de fonction de hachage à stocker.|  
|`Bucket_count`|Nombre minimal de compartiments.|  
|`Right`|Conteneur à copier.|  
|`IList`|Initializer_list depuis laquelle copier les éléments.|  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur spécifie une copie de la séquence contrôlée par `Right`. Le deuxième constructeur spécifie une séquence vide contrôlée. Le troisième constructeur spécifie une copie de la séquence en déplaçant `Right`. Le quatrième, le cinquième, le sixième, le septième et le huitième constructeurs utilisent une initializer_list pour les membres. Le neuvième constructeur insère la séquence de valeurs d'éléments `[First, Last)`.  
  
 Tous les constructeurs initialisent également plusieurs valeurs stockées. Pour le constructeur de copie, les valeurs sont obtenues à partir de `Right`. Sinon :  
  
 Le nombre minimal de compartiments est l'argument `Bucket_count`, s'il existe ; sinon c'est une valeur par défaut décrite ici comme valeur `N0` définie par l'implémentation.  
  
 L'objet de fonction de hachage est l'argument `Hash`, s'il existe ; sinon c'est `Hash()`.  
  
 L'objet de fonction de comparaison est l'argument `Comp`, s'il existe ; sinon c'est `Pred()`.  
  
 L'objet allocateur est l'argument `Al`, s'il existe ; sinon, c'est `Alloc()`.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_construct.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
using namespace std;  
  
using  Mymap = unordered_multimap<char, int> ;  
int main()  
{  
    Mymap c1;  
  
    c1.insert(Mymap::value_type('a', 1));  
    c1.insert(Mymap::value_type('b', 2));  
    c1.insert(Mymap::value_type('c', 3));  
  
    // display contents " [c 3] [b 2] [a 1]"   
    for (const auto& c : c1) {  
        cout << " [" << c.first << ", " << c.second << "]";  
    }  
    cout << endl;  
  
    Mymap c2(8,  
        hash<char>(),  
        equal_to<char>(),  
        allocator<pair<const char, int> >());  
  
    c2.insert(Mymap::value_type('d', 4));  
    c2.insert(Mymap::value_type('e', 5));  
    c2.insert(Mymap::value_type('f', 6));  
  
    // display contents " [f 6] [e 5] [d 4]"   
    for (const auto& c : c2) {  
        cout << " [" << c.first << ", " << c.second << "]";  
    }  
    cout << endl;  
  
    Mymap c3(c1.begin(),  
        c1.end(),  
        8,  
        hash<char>(),  
        equal_to<char>(),  
        allocator<pair<const char, int> >());  
  
    // display contents " [c 3] [b 2] [a 1]"   
    for (const auto& c : c3) {  
        cout << " [" << c.first << ", " << c.second << "]";  
    }  
    cout << endl;  
  
    Mymap c4(move(c3));  
  
    // display contents " [c 3] [b 2] [a 1]"   
    for (const auto& c : c4) {  
        cout << " [" << c.first << ", " << c.second << "]";  
    }  
    cout << endl;  
  
    // Construct with an initializer_list  
    unordered_multimap<int, char> c5({ { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } });  
    for (const auto& c : c5) {  
        cout << " [" << c.first << ", " << c.second << "]";  
    }  
    cout << endl;  
  
    // Initializer_list plus size  
    unordered_multimap<int, char> c6({ { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } }, 4);  
    for (const auto& c : c1) {  
        cout << " [" << c.first << ", " << c.second << "]";  
    }  
    cout << endl;  
  
    // Initializer_list plus size and hash  
    unordered_multimap<int, char, hash<char>> c7(  
        { { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } },  
        4,  
        hash<char>()  
    );  
  
    for (const auto& c : c1) {  
        cout << " [" << c.first << ", " << c.second << "]";  
    }  
    cout << endl;  
  
    // Initializer_list plus size, hash, and key_equal  
    unordered_multimap<int, char, hash<char>, equal_to<char>> c8(  
        { { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } },  
        4,  
        hash<char>(),  
        equal_to<char>()  
    );  
  
    for (const auto& c : c1) {  
        cout << " [" << c.first << ", " << c.second << "]";  
    }  
    cout << endl;  
  
    // Initializer_list plus size, hash, key_equal, and allocator  
    unordered_multimap<int, char, hash<char>, equal_to<char>> c9(  
        { { 5, 'g' }, { 6, 'h' }, { 7, 'i' }, { 8, 'j' } },  
        4,  
        hash<char>(),  
        equal_to<char>(),  
        allocator<pair<const char, int> >()  
    );  
  
    for (const auto& c : c1) {  
        cout << " [" << c.first << ", " << c.second << "]";  
    }  
    cout << endl;  
}  
  
```  
  
```Output  
[a, 1] [b, 2] [c, 3] [d, 4] [e, 5] [f, 6] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [5, g] [6, h] [7, i] [8, j] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [a, 1] [b, 2] [c, 3] [c, 3] [b, 2] [a, 1]  
 [f, 6] [e, 5] [d, 4]  
 [c, 3] [b, 2] [a, 1]  
 [c, 3] [b, 2] [a, 1]  
```  
  
##  <a name="a-nameunorderedmultimapvaluetypea--unorderedmultimapvaluetype"></a><a name="unordered_multimap__value_type"></a>  unordered_multimap::value_type  
 Type d’un élément.  
  
```  
typedef std::pair<const Key, Ty> value_type;  
```  
  
### <a name="remarks"></a>Notes  
 Ce type décrit un élément de la séquence contrôlée.  
  
### <a name="example"></a>Exemple  
  
```cpp  
// std__unordered_map__unordered_multimap_value_type.cpp   
// compile with: /EHsc   
#include <unordered_map>   
#include <iostream>   
  
typedef std::unordered_multimap<char, int> Mymap;   
int main()   
    {   
    Mymap c1;   
  
    c1.insert(Mymap::value_type('a', 1));   
    c1.insert(Mymap::value_type('b', 2));   
    c1.insert(Mymap::value_type('c', 3));   
  
// display contents " [c 3] [b 2] [a 1]"   
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
// add a value and reinspect   
    Mymap::key_type key = 'd';   
    Mymap::mapped_type mapped = 4;   
    Mymap::value_type val = Mymap::value_type(key, mapped);   
    c1.insert(val);   
  
    for (Mymap::const_iterator it = c1.begin();   
        it != c1.end(); ++it)   
        std::cout << " [" << it->first << ", " << it->second << "]";   
    std::cout << std::endl;   
  
    return (0);   
    }  
  
```  
  
```Output  
[c, 3] [b, 2] [a, 1]  
[d, 4] [c, 3] [b, 2] [a, 1]  
```  
  
## <a name="see-also"></a>Voir aussi  
 [<unordered_map>](../standard-library/unordered-map.md)   
 [Conteneurs](../cpp/containers-modern-cpp.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Informations de référence sur la bibliothèque standard C++](../standard-library/cpp-standard-library-reference.md)

