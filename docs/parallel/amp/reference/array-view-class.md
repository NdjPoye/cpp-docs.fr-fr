---
title: array_view, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::array_view
dev_langs:
- C++
helpviewer_keywords:
- array_view class
ms.assetid: 7e7ec9bc-05a2-4372-b05d-752b50006c5a
caps.latest.revision: 21
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: ec096dbcd485b9360d07d1b56511b13c13d1b4cf
ms.lasthandoff: 02/24/2017

---
# <a name="arrayview-class"></a>array_view, classe
Représente une vue de dimension N sur les données contenues dans un autre conteneur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <
    typename value_type,  
    int _Rank = 1  
>  
class array_view : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;  
 
template <
    typename value_type,  
    int _Rank  
>  
class array_view<const value_type, _Rank> : public _Array_view_base<_Rank, sizeof(value_type)/sizeof(int)>;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `value_type`  
 Le type de données des éléments de la `array_view` objet.  
  
 `_Rank`  
 Le classement de la `array_view` objet.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[array_view, constructeur](#ctor)|Initialise une nouvelle instance de la classe `array_view`. Aucun constructeur par défaut pour `array<T,N>`. Tous les constructeurs sont restreints à exécuter sur le processeur uniquement et ne peut pas être exécutées sur une cible de Direct3D.|  
|[~ array_view, destructeur](#ctor)|Détruit le `array_view` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[copy_to (méthode)](#copy_to)|Copie le contenu de la `array_view` objet vers la destination spécifiée en appelant `copy(*this, dest)`.|  
|[données (méthode)](#data)|Retourne un pointeur vers les données brutes de la `array_view`.|  
|[discard_data (méthode)](#discard_data)|Ignore les données actuelles sous-jacente de cette vue.|  
|[get_extent (méthode)](#get_extent)|Retourne l’objet de mesure de l’objet array_view.|  
|[get_ref (méthode)](#get_ref)|Retourne une référence à l’élément indexé.|  
|[get_source_accelerator_view (méthode)](#get_source_accelerator_view)|Retourne le [accelerator_view](accelerator-view-class.md) où la source de données de la `array_view` se trouve.|  
|[Méthode Refresh](#refresh)|Notifie le `array_view` objet sa mémoire lié a été modifié en dehors de la `array_view` interface. Un appel à cette méthode affiche toutes les informations mises en cache obsolète.|  
|[reinterpret_as (méthode)](#reinterpret_as)|Retourne un tableau unidimensionnel qui contienne tous les éléments dans le `array_view` objet.|  
|[section (méthode)](#section)|Retourne une sous-section de le `array_view` objet qui est à l’origine spécifiée et, éventuellement, qui a l’étendue spécifiée.|  
|[Synchronize (méthode)](#synchronize)|Synchronise les modifications apportées à la `array_view` objet à sa source de données.|  
|[synchronize_async (méthode)](#synchronize_async)|En mode asynchrone synchronise les modifications apportées à la `array_view` objet à sa source de données.|  
|[synchronize_to (méthode)](#synchronize_to)|Synchronise les modifications apportées à la `array_view` objet spécifié à la [accelerator_view](accelerator-view-class.md).|  
|[synchronize_to_async (méthode)](#synchronize_to_async)|En mode asynchrone synchronise les modifications apportées à la `array_view` objet spécifié à la [accelerator_view](accelerator-view-class.md).|  
|[view_as (méthode)](#view_as)|Génère une `array_view` objet d’un rang différent en utilisant cette `array_view` données de l’objet.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[operator() (opérateur)](#operator_call)|Retourne la valeur de l’élément spécifié par l’ou les paramètres.|  
|[operator [] (opérateur)](#operator_at)|Retourne l’élément qui est spécifié par les paramètres.|  
|[opérateur =, opérateur](#operator_eq)|Copie le contenu de l’objet `array_view` objet dans celui-ci.|  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[RANK (constante)](#rank)|Stocke le rang de la `array_view` objet.|  
  
### <a name="data-members"></a>Membres de données  
  
|Nom|Description|  
|----------|-----------------|  
|[Membre de données de mesure](#extent)|Obtient l'objet `extent` qui définit la forme de l'objet `array_view`.|  
|[source_accelerator_view (donnée membre)](#source_accelerator_view)|Obtient le [accelerator_view](accelerator-view-class.md) où la source de données de la `array_view` se trouve|  
|[Value_type (donnée membre)](#value_type)|Type de valeur de le `array_view` et le tableau lié.|  
  
## <a name="remarks"></a>Notes  
 Le `array_view` classe représente une vue des données contenues dans une [tableau](array-class.md) objet ou une sous-section d’un `array` objet.  
  
 Vous pouvez accéder à le `array_view` où la source de données se trouve (locale) ou sur un autre accélérateur ou un domaine de la cohérence de l’objet (à distance). Lorsque vous accédez à l’objet à distance, les vues sont copiés et mis en cache si nécessaire. À l’exception des effets de mise en cache automatique `array_view` objets ont un profil de performances similaire à celle de `array` objets. Il existe une altération des performances lorsque vous accédez aux données via des vues.  
  
 Il existe trois scénarios d’utilisation à distance :  
  
-   Une vue à un pointeur de mémoire système est transmise au moyen d’un [parallel_for_each](../../../parallel/concrt/reference/concurrency-namespace-functions.md#parallel_for_each) appel à un accélérateur et accessibles sur l’accélérateur.  
  
-   Un affichage dans un tableau situé sur un accélérateur est passé au moyen d’un `parallel_for_each` appel à un autre accélérateur et il accessible.  
  
-   Une vue de tableau situé sur un accélérateur est accessible sur le processeur.  
  
 Dans l’un de ces scénarios, les vues référencées sont copiées par le runtime à l’emplacement distant et, si modifiés par les appels à la `array_view` de l’objet, sont copiés vers l’emplacement local. Le runtime peut optimiser le processus de copie des modifications, peut copier uniquement les éléments modifiés ou peut également copier des parties inchangés. Chevauchement des `array_view` des objets sur une source de données ne sont pas garanti que pour maintenir l’intégrité référentielle dans un emplacement distant.  
  
 Vous devez synchroniser l’accès multithread à la même source de données.  
  
 Le runtime apporte les garanties suivantes concernant la mise en cache des données dans `array_view` objets :  
  
-   Tous les accès bien synchronisées à un `array` objet et un `array_view` un objet dans l’ordre du programme obéir à une série qui se produit-avant la relation.  
  
-   Tous les accès bien synchronisées chevauchant `array_view` des objets sur le même accélérateur sur un seul `array` objet sont des alias via la `array` objet. Provoquent un total se produit-avant la relation qui respecte l’ordre du programme. Il n’existe aucune mise en cache. Si le `array_view` objets sont exécutent sur différents accélérateurs, l’ordre d’accès n’est pas défini, la création d’une condition de concurrence.  
  
 Lorsque vous créez un `array_view` de l’objet à l’aide d’un pointeur dans la mémoire système, vous devez modifier la vue `array_view` uniquement par le biais de l’objet du `array_view` pointeur. Ou bien, vous devez appeler `refresh()` sur un de la `array_view` les objets qui sont attachés au pointeur système, si la mémoire native sous-jacente est modifiée directement, plutôt que via les `array_view` objet.  
  
 Ces deux actions notifie le `array_view` de l’objet que la mémoire native sous-jacente est modifiée et que toutes les copies qui sont trouvent sur un accélérateur sont obsolètes. Si vous suivez ces instructions, les vues utilisant des pointeurs sont identiques à ceux fournis pour les vues de tableaux de données en parallèle.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `_Array_view_shape`  
  
 `_Array_view_base`  
  
 `array_view`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp.h  
  
 **Espace de noms :** Concurrency  
  
##  <a name="a-namedtora-arrayview"></a><a name="dtor"></a>~ array_view 

 Détruit le `array_view` objet.  
  
```  
~array_view()restrict(amp,cpu);
```  
  
##  <a name="a-namectora-arrayview"></a><a name="ctor"></a>array_view 

 Initialise une nouvelle instance de la classe `array_view`.  
  
```  
array_view(
    array<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view& _Other)restrict(amp,cpu);

 
explicit array_view(
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);

 
template <
    typename _Container  
>  
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    _Container& _Src) restrict(cpu);

 
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    value_type* _Src)restrict(amp,cpu);

 
explicit array_view(
    int _E0) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    _Container& _Src,  
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    _Container& _Src) restrict(cpu);

 
explicit array_view(
    int _E0,  
    int _E1) __CPU_ONLY;  
 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    int _E1,  
    _Container& _Src) restrict(cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2) __CPU_ONLY;  
 
template <
    typename _Container  
>  
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    _Container& _Src);

 
explicit array_view(
    int _E0,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
template <
    typename _Arr_type,  
    int _Size  
>  
explicit array_view(
    _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
explicit array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    _In_ value_type* _Src)restrict(amp,cpu);

 
array_view(
    const array<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view<value_type, _Rank>& _Src)restrict(amp,cpu);

 
array_view(
    const array_view<const value_type, _Rank>& _Src)restrict(amp,cpu);

 
template <
    typename _Container  
>  
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    const _Container& _Src) restrict(cpu);

 
template <
    typename _Container  
>  
explicit array_view(
    const _Container& _Src,  
    typename std::enable_if<details::_Is_container<_Container>::type::value, void **>::type = 0) restrict(cpu);

 
array_view(
    const Concurrency::extent<_Rank>& _Extent,  
    const value_type* _Src)restrict(amp,cpu);

 
template <
    typename _Arr_type,  
    int _Size  
>  
explicit array_view(
    const _In_ _Arr_type (& _Src) [_Size]) restrict(amp,cpu);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    const _Container& _Src);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    int _E1,  
    const _Container& _Src);

 
template <
    typename _Container  
>  
array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    const _Container& _Src);

 
array_view(
    int _E0,  
    const value_type* _Src)restrict(amp,cpu);

 
array_view(
    int _E0,  
    int _E1,  
    const value_type* _Src) restrict(amp,cpu);

 
array_view(
    int _E0,  
    int _E1,  
    int _E2,  
    const value_type* _Src) restrict(amp,cpu);

 
```  
  
### <a name="parameters"></a>Paramètres  
 `_Arr_type`  
 Le type d’élément d’un tableau de style C à partir de laquelle les données sont fournies.  
  
 `_Container`  
 Un argument de modèle qui doit spécifier un conteneur linéaire qui prend en charge `data()` et `size()` membres.  
  
 `_E0`  
 Le composant plus significatif de l’étendue de cette section.  
  
 `_E1`  
 Le composant suivant-à-plus significatif de l’étendue de cette section.  
  
 `_E2`  
 Le composant moins important de l’étendue de cette section.  
  
 `_Extent`  
 L’étendue de chaque dimension de ce `array_view`.  
  
 `_Other`  
 Un objet de type `array_view<T,N>` à partir de laquelle initialiser la nouvelle `array_view`.  
  
 `_Size`  
 La taille d’un tableau de style C à partir de laquelle les données sont fournies.  
  
 `_Src`  
 Pointeur vers les données source qui seront copiés dans le nouveau tableau.  
  
##  <a name="a-namecopytoa-copyto"></a><a name="copy_to"></a>copy_to 

 Copie le contenu de la `array_view` objet à l’objet de destination spécifié en appelant `copy(*this, dest)`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const;

 
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const;

 
```  
  
### <a name="parameters"></a>Paramètres  
 `_Dest`  
 L’objet de destination.  
  
##  <a name="a-namedataa-data"></a><a name="data"></a>données 

 Retourne un pointeur vers les données brutes de la `array_view`.  
  
```  
value_type* data() const restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers les données brutes de la `array_view`.  
  
##  <a name="a-namediscarddataa-discarddata"></a><a name="discard_data"></a>discard_data 

 Ignore les données actuelles sous-jacente de cette vue. Il s’agit d’un indicateur d’optimisation de runtime utilisée pour éviter de copier le contenu actuel de la vue vers une cible `accelerator_view` qui y accède sur, et son utilisation est recommandée si le contenu existant n’est pas nécessaire. Cette méthode est une opération inefficace lorsqu’il est utilisé dans un contexte Restrict (amp)  
  
```  
void discard_data() const restrict(cpu);
```  
  
##  <a name="a-nameextenta-extent"></a><a name="extent"></a>étendue 

 Obtient l'objet `extent` qui définit la forme de l'objet `array_view`.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namegetextenta-getextent"></a><a name="get_extent"></a>get_extent 

 Retourne le [étendue](extent-class.md) objet de la `array_view` objet.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(cpu, amp);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le `extent` objet de la `array_view` objet  
  
##  <a name="a-namegetrefa-getref"></a><a name="get_ref"></a>get_ref 

 Obtenir une référence à l’élément indexé par _Index. Contrairement à d’autres opérateurs d’indexation pour accéder à l’array_view sur l’UC, cette méthode ne synchronise pas implicitement le contenu de ce array_view pour le processeur. Après l’accès à l’array_view sur un emplacement distant ou une opération de copie impliquant cette array_view les utilisateurs sont chargés pour synchroniser explicitement l’array_view au processeur avant d’appeler cette méthode. Cela entraîne un comportement non défini.  
  
```  
value_type& get_ref(
    const index<_Rank>& _Index) const restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 Index.  
  
### <a name="return-value"></a>Valeur de retour  
 Référence à l’élément indexé par _Index  
  
##  <a name="a-namegetsourceacceleratorviewa-getsourceacceleratorview"></a><a name="get_source_accelerator_view"></a>get_source_accelerator_view 

 Retourne l’accelerator_view où se trouve la source de données de l’array_view. Si l’array_view ne dispose pas d’une source de données, cette API lève une runtime_exception  
  
```  
accelerator_view get_source_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-nameoperatorcalla-operator"></a><a name="operator_call"></a>operator() 

 Retourne la valeur de l’élément spécifié par l’ou les paramètres.  
  
```  
value_type& operator() (
    const index<_Rank>& _Index) const restrict(amp,cpu);

 
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator() (
    int _I) const restrict(amp,cpu);

 
value_type& operator() (
    int _I0,  
    int _I1) const restrict(amp,cpu);

 
value_type& operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp,cpu);

 
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator() (
    int _I) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 L’emplacement de l’élément.  
  
 `_I0`  
 L’index de la première dimension.  
  
 `_I1`  
 Index dans la deuxième dimension.  
  
 `_I2`  
 L’index de la troisième dimension.  
  
 `_I`  
 L’emplacement de l’élément.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de l’élément spécifié par l’ou les paramètres.  
  
##  <a name="a-nameoperatorata-operator"></a><a name="operator_at"></a>operator] 

 Retourne l’élément qui est spécifié par les paramètres.  
  
```  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[] (
    int _I) const restrict(amp,cpu);

 
value_type& operator[] (
    const index<_Rank>& _Index) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 Index.  
  
 `_I`  
 Index.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de l’élément à l’index, ou un `array_view` projetée sur la dimension plus significatif.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>opérateur = 

 Copie le contenu de l’objet `array_view` objet à celui-ci.  
  
```  
array_view& operator= (
    const array_view& _Other) restrict(amp,cpu);

 
array_view& operator= (
    const array_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `array_view` objet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `array_view` objet.  
  
##  <a name="a-nameranka-rank"></a><a name="rank"></a>rang 

 Stocke le rang de la `array_view` objet.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-namerefresha-refresh"></a><a name="refresh"></a>actualisation 

 Notifie le `array_view` objet sa mémoire lié a été modifié en dehors de la `array_view` interface. Un appel à cette méthode affiche toutes les informations mises en cache obsolète.  
  
```  
void refresh() const restrict(cpu);
```  
## <a name="a-namereinterpretasa-reinterpretas"></a><a name="reinterpret_as"></a>reinterpret_as 

Réinterprète l’array_view via un array_view unidimensionnel, qui peut avoir un type de valeur différente que l’array_view source en tant qu’option.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
template <  
    typename _Value_type2  
>  
array_view< _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);  
  
template <  
    typename _Value_type2  
>  
array_view<const _Value_type2, _Rank> reinterpret_as() const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Value_type2`  
 Le type de données de la nouvelle `array_view` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Un `array_view` objet ou const `array_view` objet basé sur cette `array_view`, avec le type d’élément converti à partir de `T` à `_Value_type2`, et le rang réduit de *N* 1.  
  
### <a name="remarks"></a>Remarques  
 Il est parfois commode afficher un tableau multidimensionnel comme un tableau unidimensionnel linéaire, qui peut-être avoir un type de valeur différente que le tableau source. Vous pouvez l’obtenir sur un `array_view` à l’aide de cette méthode.  
  
**Avertissement** Reinterpeting un objet array_view à l’aide d’un type valeur différent est une opération potentiellement dangereuse. Cette fonctionnalité doit être utilisée avec précaution.  
  
 Voici un exemple :  
  
```cpp  
struct RGB { float r; float g; float b; };  
  
array<RGB,3>  a = ...;   
array_view<float,1> v = a.reinterpret_as<float>();   
  
assert(v.extent == 3*a.extent);  
```  
    
##  <a name="a-namesectiona-section"></a><a name="section"></a>section 

 Retourne une sous-section de le `array_view` objet qui est à l’origine spécifiée et, éventuellement, qui a l’étendue spécifiée.  
  
```  
array_view section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);

 
array_view section(
    const Concurrency::index<_Rank>& _Idx) const restrict(amp,cpu);

 
array_view section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _E0) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) const restrict(amp,cpu);

 
array_view section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_E0`  
 Le composant plus significatif de l’étendue de cette section.  
  
 `_E1`  
 Le composant suivant-à-plus significatif de l’étendue de cette section.  
  
 `_E2`  
 Le composant moins important de l’étendue de cette section.  
  
 `_Ext`  
 Le [étendue](extent-class.md) objet qui spécifie l’étendue de la section. L’origine est 0.  
  
 `_Idx`  
 Le [index](index-class.md) objet qui spécifie l’emplacement d’origine. La sous-section est le reste de l’étendue.  
  
 `_I0`  
 Le composant plus significatif de l’origine de cette section.  
  
 `_I1`  
 Le composant suivant-à-plus significatif de l’origine de cette section.  
  
 `_I2`  
 Le composant moins significatif de l’origine de cette section.  
  
 `_Rank`  
 Le classement de la section.  
  
 `_Section_extent`  
 Le [étendue](extent-class.md) objet qui spécifie l’étendue de la section.  
  
 `_Section_origin`  
 Le [index](index-class.md) objet qui spécifie l’emplacement d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une sous-section de le `array_view` objet qui est à l’origine spécifiée et, éventuellement, qui a l’étendue spécifiée. Lorsque seul le `index` objet est spécifié, la sous-section contienne tous les éléments de l’étendue associée qui ont des index supérieurs à l’index des éléments dans le `index` objet.  
  
##  <a name="a-namesourceacceleratorviewa-sourceacceleratorview"></a><a name="source_accelerator_view"></a>source_accelerator_view 

 Obtient l’accelerator_view source qui est associé à ce array_view.  
  
```  
__declspec(property(get= get_source_accelerator_view)) accelerator_view source_accelerator_view;  
```  
  
##  <a name="a-namesynchronizea-synchronize"></a><a name="synchronize"></a>synchroniser 

 Synchronise les modifications apportées à la `array_view` objet à sa source de données.  
  
```  
void synchronize(access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize() const restrict(cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Access_type`  
 La destination [access_type](concurrency-namespace-enums-amp.md#access_type) sur la cible [accelerator_view](accelerator-view-class.md). Ce paramètre a la valeur par défaut `access_type_read`.  
  
##  <a name="a-namesynchronizeasynca-synchronizeasync"></a><a name="synchronize_async"></a>synchronize_async 

 En mode asynchrone synchronise les modifications apportées à la `array_view` objet à sa source de données.  
  
```  
concurrency::completion_future synchronize_async(access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_async() const restrict(cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Access_type`  
 La destination [access_type](concurrency-namespace-enums-amp.md#access_type) sur la cible [accelerator_view](accelerator-view-class.md). Ce paramètre a la valeur par défaut `access_type_read`.  
  
### <a name="return-value"></a>Valeur de retour  
 Un futur sur lequel vous souhaitez attendre que l’opération soit terminée.  
  
##  <a name="a-namesynchronizetoa-synchronizeto"></a><a name="synchronize_to"></a>synchronize_to 

 Synchronise les modifications apportées à cette array_view pour l’accelerator_view spécifié.  
  
```  
void synchronize_to(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
void synchronize_to(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Accl_view`  
 Accelerator_view de cible à synchroniser avec.  
  
 `_Access_type`  
 L’access_type souhaitée sur la cible accelerator_view. Ce paramètre a la valeur par défaut access_type_read.  
  
##  <a name="a-namesynchronizetoasynca-synchronizetoasync"></a><a name="synchronize_to_async"></a>synchronize_to_async 

 En mode asynchrone synchronise les modifications apportées à cette array_view pour l’accelerator_view spécifié.  
  
```  
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view,  
    access_type _Access_type = access_type_read) const restrict(cpu);

 
concurrency::completion_future synchronize_to_async(
    const accelerator_view& _Accl_view) const restrict(cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Accl_view`  
 Accelerator_view de cible à synchroniser avec.  
  
 `_Access_type`  
 L’access_type souhaitée sur la cible accelerator_view. Ce paramètre a la valeur par défaut access_type_read.  
  
### <a name="return-value"></a>Valeur de retour  
 Un futur sur lequel vous souhaitez attendre que l’opération soit terminée.  
  
##  <a name="a-namevaluetypea-valuetype"></a><a name="value_type"></a>Value_type 

 Le type de valeur de l’array_view et le tableau lié.  
  
```  
typedef typenamevalue_type value_type;  
```  
  
##  <a name="a-nameviewasa-viewas"></a><a name="view_as"></a>view_as 

 Cela réinterprète `array_view` comme un `array_view` d’un rang différent.  
  
```  
template <
    int _New_rank  
>  
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);

 
template <
    int _New_rank  
>  
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank> _View_extent) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_New_rank`  
 Le rang du nouveau `array_view` objet.  
  
 `_View_extent`  
 La modification `extent`.  
  
 `value_type`  
 Le type de données des éléments dans les deux d’origine [tableau](array-class.md) objet et retourné `array_view` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Le `array_view` objet construit.  
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

