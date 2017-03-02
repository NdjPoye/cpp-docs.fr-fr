---
title: concurrent_unordered_multiset, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concurrent_unordered_set/concurrency::concurrent_unordered_multiset
dev_langs:
- C++
helpviewer_keywords:
- concurrent_unordered_multiset class
ms.assetid: 219d7d67-1ff0-45f4-9400-e9cc272991a4
caps.latest.revision: 12
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 19244e5527207f852256e646abd18ad298fb28cd
ms.openlocfilehash: 7a4b5edab0fdf1fcc18e223c859ca2859173154f
ms.lasthandoff: 02/24/2017

---
# <a name="concurrentunorderedmultiset-class"></a>concurrent_unordered_multiset, classe
La `concurrent_unordered_multiset` classe est un conteneur concurrentiel qui contrôle une séquence de longueur variable d’éléments de type K. La séquence est représentée de façon active concurrentiel append, l’accès aux éléments, les itérateurs et les opérations de parcours d’itérateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <typename K,
    typename _Hasher = std::hash<K>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>
>,
    typename key_equality = std::equal_to<K>,
    typename _Allocator_type = std::allocator<K>> class concurrent_unordered_multiset : public details::_Concurrent_hash<details::_Concurrent_unordered_set_traits<K,
    details::_Hash_compare<K,
 _Hasher,
    key_equality>,
 _Allocator_type,
    true>>;
```   
  
#### <a name="parameters"></a>Paramètres  
 `K`  
 Type de clé.  
  
 `_Hasher`  
 Type d'objet de la fonction de hachage. Cet argument est facultatif et sa valeur par défaut est `std::hash<``K``>`.  
  
 `key_equality`  
 Type d’objet de fonction de comparaison d’égalité. Cet argument est facultatif et sa valeur par défaut est `std::equal_to<``K``>`.  
  
 `_Allocator_type`  
 Type qui représente l’objet allocateur stocké qui contient des informations sur l’allocation et la désallocation de mémoire pour le vecteur simultané. Cet argument est facultatif et sa valeur par défaut est `std::allocator<``K``>`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`allocator_type`|Type d’un allocateur pour la gestion du stockage.|  
|`const_iterator`|Type d'un itérateur constant pour la séquence contrôlée.|  
|`const_local_iterator`|Type d’un itérateur de compartiment constant pour la séquence contrôlée.|  
|`const_pointer`|Type d'un pointeur constant vers un élément.|  
|`const_reference`|Type d'une référence constante à un élément.|  
|`difference_type`|Type d'une distance signée entre deux éléments.|  
|`hasher`|Type de la fonction de hachage.|  
|`iterator`|Type d'un itérateur pour la séquence contrôlée.|  
|`key_equal`|Type de la fonction de comparaison.|  
|`key_type`|Type d'une clé de tri.|  
|`local_iterator`|Type d'un itérateur de compartiment pour la séquence contrôlée.|  
|`pointer`|Type d'un pointeur vers un élément.|  
|`reference`|Type d'une référence à un élément.|  
|`size_type`|Type d'une distance non signée entre deux éléments.|  
|`value_type`|Type d’un élément.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[concurrent_unordered_multiset, constructeur](#ctor)|Surchargé. Construit un multiensemble non ordonné simultané.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[hash_function (méthode)](#hash_function)|Retourne l’objet de fonction de hachage stocké.|  
|[Insert (méthode)](#insert)|Surchargé. Ajoute des éléments à la `concurrent_unordered_multiset` objet.|  
|[key_eq (méthode)](#key_eq)|L’objet de fonction de comparaison d’égalité stockée.|  
|[swap (méthode)](#swap)|Échange le contenu de deux `concurrent_unordered_multiset` objets. Cette méthode n’est pas concurrentiel.|  
|[unsafe_erase (méthode)](#unsafe_erase)|Surchargé. Supprime les éléments à partir de la `concurrent_unordered_multiset` positions spécifiées. Cette méthode n’est pas concurrentiel.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[opérateur =, opérateur](#operator_eq)|Surchargé. Assigne le contenu d’un autre `concurrent_unordered_multiset` objet à celui-ci. Cette méthode n’est pas concurrentiel.|  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations sur la `concurrent_unordered_multiset` de classe, consultez la page [conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `_Traits`  
  
 `_Concurrent_hash`  
  
 `concurrent_unordered_multiset`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concurrent_unordered_set.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namebegina-begin"></a><a name="begin"></a>commencer 

 Retourne un itérateur qui pointe vers le premier élément dans le conteneur simultané. Cette méthode est sécurisée l’accès concurrentiel.  
  
```
iterator begin();

const_iterator begin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur au premier élément dans le conteneur simultané.  
  
##  <a name="a-namecbegina-cbegin"></a><a name="cbegin"></a>cbegin 

 Retourne un itérateur const qui pointe vers le premier élément dans le conteneur simultané. Cette méthode est sécurisée l’accès concurrentiel.  
  
```
const_iterator cbegin() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur const sur le premier élément dans le conteneur simultané.  
  
##  <a name="a-namecenda-cend"></a><a name="cend"></a>cend 

 Retourne un itérateur const qui pointe vers l’emplacement suivant le dernier élément dans le conteneur simultané. Cette méthode est sécurisée l’accès concurrentiel.  
  
```
const_iterator cend() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur const à l’emplacement suivant le dernier élément dans le conteneur simultané.  
  
##  <a name="a-namecleara-clear"></a><a name="clear"></a>Effacer 

 Efface tous les éléments dans le conteneur simultané. Cette fonction n’est pas sécurisée l’accès concurrentiel.  
  
```
void clear();
```  
  
##  <a name="a-namectora-concurrentunorderedmultiset"></a><a name="ctor"></a>concurrent_unordered_multiset 

 Construit un multiensemble non ordonné simultané.  
  
```
explicit concurrent_unordered_multiset(
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multiset(
    const allocator_type& _Allocator);

template <typename _Iterator>
concurrent_unordered_multiset(_Iterator first,
    _Iterator last,
    size_type _Number_of_buckets = 8,
    const hasher& _Hasher = hasher(),
    const key_equal& key_equality = key_equal(),
    const allocator_type& _Allocator = allocator_type());

concurrent_unordered_multiset(
    const concurrent_unordered_multiset& _Uset);

concurrent_unordered_multiset(
    const concurrent_unordered_multiset& _Uset,
    const allocator_type& _Allocator);

concurrent_unordered_multiset(
    concurrent_unordered_multiset&& _Uset);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Iterator`  
 Type de l'itérateur d'entrée.  
  
 `_Number_of_buckets`  
 Nombre initial de compartiments pour cette classe multiset non ordonnée.  
  
 `_Hasher`  
 La fonction de hachage pour cette classe multiset non ordonnée.  
  
 `key_equality`  
 La fonction de comparaison d’égalité pour cette classe multiset non ordonnée.  
  
 `_Allocator`  
 L’allocateur de cette classe multiset non ordonnée.  
  
 `first`  
 `last`  
 `_Uset`  
 La source `concurrent_unordered_multiset` déplacer les éléments d’objet.  
  
### <a name="remarks"></a>Remarques  
 Tous les constructeurs stockent un objet allocateur `_Allocator` et initialiser la classe multiset non ordonnée.  
  
 Le premier constructeur spécifie un multiensemble initial vide et spécifie explicitement les fonctions de hachage et d’égalité et allocateur tapez le nombre de compartiments, pour être utilisé.  
  
 Le deuxième constructeur spécifie un allocateur pour la classe multiset non ordonnée.  
  
 Le troisième constructeur spécifie les valeurs fournies par la plage d’itérateurs [ `_Begin`, `_End`).  
  
 Les quatrième et cinquième constructeurs spécifient une copie d’un multiensemble non ordonné simultanée `_Uset`.  
  
 Le dernier constructeur spécifie le déplacement d’un multiensemble non ordonné simultané `_Uset`.  
  
##  <a name="a-namecounta-count"></a><a name="count"></a>nombre 

 Compte le nombre d’éléments qui correspondent à une clé spécifiée. Cette fonction est sécurisée l’accès concurrentiel.  
  
```
size_type count(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `KVal`  
 Clé à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de tentatives le nombre de fois où que la clé s’affiche dans le conteneur.  
  
##  <a name="a-nameemptya-empty"></a><a name="empty"></a>vide 

 Vérifie l'absence d'éléments. Cette méthode est sécurisée l’accès concurrentiel.  
  
```
bool empty() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le conteneur simultané est vide, `false` dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 En présence d’insertions simultanées, ou non le conteneur simultané est vide peut changer immédiatement après l’appel de cette fonction, avant même la lecture la valeur de retour.  
  
##  <a name="a-nameenda-end"></a><a name="end"></a>fin 

 Retourne un itérateur qui pointe vers l’emplacement suivant le dernier élément dans le conteneur simultané. Cette méthode est sécurisée l’accès concurrentiel.  
  
```
iterator end();

const_iterator end() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur vers l’emplacement suivant le dernier élément dans le conteneur simultané.  
  
##  <a name="a-nameequalrangea-equalrange"></a><a name="equal_range"></a>equal_range 

 Recherche une plage qui correspond à une clé spécifiée. Cette fonction est sécurisée l’accès concurrentiel.  
  
```
std::pair<iterator,
    iterator> equal_range(
    const key_type& KVal);

std::pair<const_iterator,
    const_iterator> equal_range(
    const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `KVal`  
 La valeur de clé à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 A [paire](http://msdn.microsoft.com/en-us/32e72d66-3020-4cb9-92c3-f7a5fa7998ff) où le premier élément est un itérateur vers le début et le deuxième élément est un itérateur à la fin de la plage.  
  
### <a name="remarks"></a>Notes  
 Il est possible pour les insertions simultanées provoquer des clés supplémentaires à insérer après l’itérateur begin et avant l’itérateur de fin.  
  
##  <a name="a-namefinda-find"></a><a name="find"></a>Rechercher 

 Recherche un élément qui correspond à une clé spécifiée. Cette fonction est sécurisée l’accès concurrentiel.  
  
```
iterator find(const key_type& KVal);

const_iterator find(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `KVal`  
 La valeur de clé à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Un itérateur qui pointe vers l’emplacement du premier élément correspondant à la clé fournie, ou l’itérateur `end()` si aucun élément n’existe.  
  
##  <a name="a-namegetallocatora-getallocator"></a><a name="get_allocator"></a>get_allocator 

 Retourne l’objet allocateur stocké pour ce conteneur simultané. Cette méthode est sécurisée l’accès concurrentiel.  
  
```
allocator_type get_allocator() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’objet allocateur stocké pour ce conteneur simultané.  
  
##  <a name="a-namehashfunctiona-hashfunction"></a><a name="hash_function"></a>hash_function 

 Retourne l’objet de fonction de hachage stocké.  
  
```
hasher hash_function() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’objet de fonction de hachage stocké.  
  
##  <a name="a-nameinserta-insert"></a><a name="insert"></a>Insérer 

 Ajoute des éléments à la `concurrent_unordered_multiset` objet.  
  
```
iterator insert(
    const value_type& value);

iterator insert(
    const_iterator _Where,
    const value_type& value);

template<class _Iterator>
void insert(_Iterator first,
    _Iterator last);

template<class V>
iterator insert(
    V&& value);

template<class V>
typename std::enable_if<!std::is_same<const_iterator,
    typename std::remove_reference<V>::type>::value,
    iterator>::type insert(
    const_iterator _Where,
    V&& value);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Iterator`  
 Le type d’itérateur permet l’insertion.  
  
 `V`  
 Le type de la valeur insérée.  
  
 `value`  
 La valeur à insérer.  
  
 `_Where`  
 L’emplacement de départ pour rechercher un point d’insertion.  
  
 `first`  
 Début de la plage à insérer.  
  
 `last`  
 La fin de la plage à insérer.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui pointe vers l’emplacement d’insertion.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre insère l’élément `value` dans la séquence contrôlée, puis retourne l’itérateur qui désigne l’élément inséré.  
  
 La seconde fonction membre retourne insert ( `value`), en utilisant `_Where` comme point de départ dans la séquence contrôlée pour rechercher le point d’insertion.  
  
 La troisième fonction membre insère la séquence de valeurs d’éléments de la plage [ `first`, `last`).  
  
 Les deux dernières fonctions membres comportent comme les deux premières, à ceci près que `value` est utilisé pour construire la valeur insérée.  
  
##  <a name="a-namekeyeqa-keyeq"></a><a name="key_eq"></a>key_eq 

 L’objet de fonction de comparaison d’égalité stockée.  
  
```
key_equal key_eq() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’objet de fonction de comparaison d’égalité stockée.  
  
##  <a name="a-nameloadfactora-loadfactor"></a><a name="load_factor"></a>load_factor 

 Calcule et retourne le facteur de charge actuel du conteneur. Le facteur de charge est le nombre d’éléments dans le conteneur divisé par le nombre de compartiments.  
  
```
float load_factor() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le facteur de charge pour le conteneur.  
  
##  <a name="a-namemaxloadfactora-maxloadfactor"></a><a name="max_load_factor"></a>max_load_factor 

 Obtient ou définit le facteur de charge maximale du conteneur. Le facteur de charge maximale est le plus grand nombre d’éléments que possible dans chaque compartiment avant le conteneur augmente sa table interne.  
  
```
float max_load_factor() const;

void max_load_factor(float _Newmax);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Newmax`  
  
### <a name="return-value"></a>Valeur de retour  
 La première fonction membre retourne le facteur de charge maximale stockée. La seconde fonction membre ne retourne pas de valeur, mais lève une [out_of_range](../../../standard-library/out-of-range-class.md) exception si le facteur de charge fourni n’est pas valide...  
  
##  <a name="a-namemaxsizea-maxsize"></a><a name="max_size"></a>max_size 

 Retourne la taille maximale du conteneur simultanée, déterminée par l’allocateur. Cette méthode est sécurisée l’accès concurrentiel.  
  
```
size_type max_size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre maximal d’éléments qui peuvent être insérées dans ce conteneur simultané.  
  
### <a name="remarks"></a>Remarques  
 Cette valeur limite supérieure peut être supérieure à ce que le conteneur peut réellement contenir.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>opérateur = 

 Assigne le contenu d’un autre `concurrent_unordered_multiset` objet à celui-ci. Cette méthode n’est pas concurrentiel.  
  
```
concurrent_unordered_multiset& operator= (const concurrent_unordered_multiset& _Uset);

concurrent_unordered_multiset& operator= (concurrent_unordered_multiset&& _Uset);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Uset`  
 Objet `concurrent_unordered_multiset` source.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `concurrent_unordered_multiset` objet.  
  
### <a name="remarks"></a>Remarques  
 Après avoir supprimé les éléments existants dans un multiensemble non ordonné simultané, `operator=` copie ou déplace le contenu de `_Uset` dans la simultanées désordonnés multiset.  
  
##  <a name="a-namerehasha-rehash"></a><a name="rehash"></a>rehash) 

 Régénère la table de hachage.  
  
```
void rehash(size_type _Buckets);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Buckets`  
 Le nombre de compartiments voulu.  
  
### <a name="remarks"></a>Remarques  
 La fonction membre modifie le nombre de compartiments pour qu’il soit au moins égal à `_Buckets` et régénère la table de hachage en fonction des besoins. Le nombre de compartiments doit être une puissance de 2. Si pas une puissance de 2, elle sera arrondie à la plus grande puissance de 2 suivante.  
  
 Elle génère une [out_of_range](../../../standard-library/out-of-range-class.md) exception si le nombre de compartiments n’est pas valide (0 ou supérieur au nombre maximal de compartiments).  
  
##  <a name="a-namesizea-size"></a><a name="size"></a>taille 

 Retourne le nombre d’éléments dans ce conteneur simultané. Cette méthode est sécurisée l’accès concurrentiel.  
  
```
size_type size() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’éléments dans le conteneur.  
  
### <a name="remarks"></a>Remarques  
 En présence d’insertions simultanées, le nombre d’éléments dans le conteneur simultané peut changer immédiatement après l’appel de cette fonction, avant même la lecture la valeur de retour.  
  
##  <a name="a-nameswapa-swap"></a><a name="swap"></a>échange 

 Échange le contenu de deux `concurrent_unordered_multiset` objets. Cette méthode n’est pas concurrentiel.  
  
```
void swap(concurrent_unordered_multiset& _Uset);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Uset`  
 Le `concurrent_unordered_multiset` objet pour le remplacement.  
  
##  <a name="a-nameunsafebegina-unsafebegin"></a><a name="unsafe_begin"></a>unsafe_begin 

 Retourne un itérateur au premier élément dans ce conteneur pour un compartiment spécifique.  
  
```
local_iterator unsafe_begin(size_type _Bucket);

const_local_iterator unsafe_begin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Bucket`  
 L’index du compartiment.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui pointe vers le début de la plage.  
  
##  <a name="a-nameunsafebucketa-unsafebucket"></a><a name="unsafe_bucket"></a>unsafe_bucket 

 Retourne l’index de compartiments correspondant à une clé spécifique dans ce conteneur.  
  
```
size_type unsafe_bucket(const key_type& KVal) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `KVal`  
 La clé de l’élément à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 L’index de compartiment pour la clé dans ce conteneur.  
  
##  <a name="a-nameunsafebucketcounta-unsafebucketcount"></a><a name="unsafe_bucket_count"></a>unsafe_bucket_count 

 Retourne le nombre actuel de compartiments dans ce conteneur.  
  
```
size_type unsafe_bucket_count() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de compartiments dans ce conteneur.  
  
##  <a name="a-nameunsafebucketsizea-unsafebucketsize"></a><a name="unsafe_bucket_size"></a>unsafe_bucket_size 

 Retourne le nombre d’éléments dans un compartiment spécifique de ce conteneur.  
  
```
size_type unsafe_bucket_size(size_type _Bucket);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Bucket`  
 Le compartiment à rechercher.  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de compartiments dans ce conteneur.  
  
##  <a name="a-nameunsafecbegina-unsafecbegin"></a><a name="unsafe_cbegin"></a>unsafe_cbegin 

 Retourne un itérateur au premier élément dans ce conteneur pour un compartiment spécifique.  
  
```
const_local_iterator unsafe_cbegin(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Bucket`  
 L’index du compartiment.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui pointe vers le début de la plage.  
  
##  <a name="a-nameunsafecenda-unsafecend"></a><a name="unsafe_cend"></a>unsafe_cend 

 Retourne un itérateur vers l’emplacement suivant le dernier élément dans un compartiment spécifique.  
  
```
const_local_iterator unsafe_cend(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Bucket`  
 L’index du compartiment.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui pointe vers le début de la plage.  
  
##  <a name="a-nameunsafeenda-unsafeend"></a><a name="unsafe_end"></a>unsafe_end 

 Retourne un itérateur au dernier élément dans ce conteneur pour un compartiment spécifique.  
  
```
local_iterator unsafe_end(size_type _Bucket);

const_local_iterator unsafe_end(size_type _Bucket) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `_Bucket`  
 L’index du compartiment.  
  
### <a name="return-value"></a>Valeur de retour  
 Itérateur qui pointe vers la fin de la plage.  
  
##  <a name="a-nameunsafeerasea-unsafeerase"></a><a name="unsafe_erase"></a>unsafe_erase 

 Supprime les éléments à partir de la `concurrent_unordered_multiset` positions spécifiées. Cette méthode n’est pas concurrentiel.  
  
```
iterator unsafe_erase(
    const_iterator _Where);

iterator unsafe_erase(
    const_iterator first,
    const_iterator last);

size_type unsafe_erase(
    const key_type& KVal);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Where`  
 La position de l’itérateur sur l’effacement de.  
  
 `first`  
 `last`  
 `KVal`  
 La valeur de clé à effacer.  
  
### <a name="return-value"></a>Valeur de retour  
 Les première deux fonctions membres retournent un itérateur qui désigne le premier élément restant après tous les éléments supprimés, ou [fin méthode](#end)() si aucun élément n’existe. La troisième fonction membre retourne le nombre d’éléments à que supprimer.  
  
### <a name="remarks"></a>Notes  
 La première fonction membre supprime l’élément désigné par `_Where`. La seconde fonction membre supprime les éléments de la plage [ `_Begin`, `_End`).  
  
 La troisième fonction membre supprime les éléments de la plage délimitée par [equal_range méthode](#equal_range)(KVal).  
  
##  <a name="a-nameunsafemaxbucketcounta-unsafemaxbucketcount"></a><a name="unsafe_max_bucket_count"></a>unsafe_max_bucket_count 

 Retourne le nombre maximal de compartiments dans ce conteneur.  
  
```
size_type unsafe_max_bucket_count() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre maximal de compartiments dans ce conteneur.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [Conteneurs et objets parallèles](../../../parallel/concrt/parallel-containers-and-objects.md)




