---
title: Array, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::array
dev_langs:
- C++
helpviewer_keywords:
- array class
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
caps.latest.revision: 31
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
ms.openlocfilehash: c1708bfedc35076f1d10f6c4dd128bb428a7855e
ms.lasthandoff: 02/24/2017

---
# <a name="array-class"></a>array, classe
Représente un conteneur de données utilisé pour déplacer des données vers un accélérateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <typename value_type, int _Rank>  
friend class array;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `value_type`  
 Le type d’élément de données.  
  
 `_Rank`  
 Le rang du tableau.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Array, constructeur](#ctor)|Initialise une nouvelle instance de la classe `array`.|  
|[~ array, destructeur](#dtor)|Détruit le `array` objet.|  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[copy_to (méthode)](#copy_to)|Copie le contenu du tableau dans un autre tableau.|  
|[données (méthode)](#data)|Retourne un pointeur vers les données brutes du tableau.|  
|[get_accelerator_view (méthode)](#get_accelerator_view)|Retourne le [accelerator_view](accelerator-view-class.md) objet qui représente l’emplacement où le tableau est alloué. Cette propriété est accessible uniquement sur le processeur.|  
|[get_associated_accelerator_view (méthode)](#get_associated_accelerator_view)|Obtient le second [accelerator_view](accelerator-view-class.md) objet passé en tant que paramètre lorsqu’une zone de transit est appelé pour instancier le `array` objet.|  
|[get_cpu_access_type (méthode)](#get_cpu_access_type)|Retourne le [access_type](concurrency-namespace-enums-amp.md#access_type) du tableau. Cette méthode est accessible uniquement sur le processeur.|  
|[get_extent (méthode)](#get_extent)|Retourne le [étendue](extent-class.md) objet du tableau.|  
|[reinterpret_as (méthode)](#reinterpret_as)|Retourne un tableau unidimensionnel qui contienne tous les éléments dans le `array` objet.|  
|[section (méthode)](#section)|Retourne une sous-section de le `array` objet qui est à l’origine spécifiée et, éventuellement, qui a l’étendue spécifiée.|  
|[view_as (méthode)](#view_as)|Retourne un [array_view](array-view-class.md) objet construit à partir de la `array` objet.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[opérateur std::vector&lt;value_type&gt; (opérateur)](#operator_vec)|Utilise `copy(*this, vector)` convertir implicitement le tableau à un std ::[vecteur](../../../standard-library/vector-class.md) objet.|  
|[operator() (opérateur)](#operator_call)|Retourne la valeur de l’élément spécifié par les paramètres.|  
|[operator [] (opérateur)](#operator_at)|Retourne l’élément situé à l’index spécifié.|  
|[opérateur =, opérateur](#operator_eq)|Copie le contenu de l’objet `array` objet dans celui-ci.|  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[RANK (constante)](#rank)|Stocke le rang du tableau.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[accelerator_view (donnée membre)](#accelerator_view)|Obtient le [accelerator_view](accelerator-view-class.md) objet qui représente l’emplacement où le tableau est alloué. Cette propriété est accessible uniquement sur le processeur.|  
|[associated_accelerator_view (donnée membre)](#associated_accelerator_view)|Obtient le second [accelerator_view](accelerator-view-class.md) objet passé en tant que paramètre lorsqu’une zone de transit est appelé pour instancier le `array` objet.|  
|[cpu_access_type (donnée membre)](#cpu_access_type)|Obtient le [access_type](concurrency-namespace-enums-amp.md#access_type) qui représente la façon dont le processeur peut accéder au stockage du tableau.|  
|[Membre de données de mesure](#extent)|Obtient l’étendue qui définit la forme du tableau.|  
  
## <a name="remarks"></a>Notes  
 Le type `array<T,N>` représente une densité et ordinaires (non en escalier) *N*-tableau unidimensionnel qui se trouve dans un emplacement spécifique, comme un accélérateur ou de l’UC. Le type de données des éléments du tableau est `T`, qui doit être d’un type qui est compatible avec l’accélérateur de cible. Bien que le classement, `N`, (du tableau est déterminé de manière statique et fait partie du type, la mesure du tableau est déterminée par le runtime et est exprimée à l’aide de la classe `extent<N>`.  
  
 Un tableau peut avoir n’importe quel nombre de dimensions, bien que certaines fonctionnalités sont spécialisée pour `array` objets avec un classement, deux et trois. Si vous omettez l’argument de dimension, la valeur par défaut est 1.  
  
 Données de tableau sont disposées de façon contiguë en mémoire. Les éléments qui diffèrent d’une unité dans la dimension moins significatif sont adjacents en mémoire.  
  
 Tableaux sont logiquement considérés comme des types valeur, car lorsqu’un tableau est copié dans un autre tableau, une copie complète est effectuée. Deux tableaux point jamais aux mêmes données.  
  
 Le `array<T,N>` est utilisé dans plusieurs scénarios :  
  
-   Conteneur de données qui peut être utilisé dans les calculs sur un accélérateur.  
  
-   Comme un conteneur de données pour contenir la mémoire sur l’hôte du processeur (qui peut être utilisé pour copier vers et à partir d’autres tableaux).  
  
-   Comme un objet intermédiaire d’agir comme un intermédiaire rapide de copie de l’hôte vers le périphérique.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `array`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp.h  
  
 **Espace de noms :** Concurrency  
  
##  <a name="a-namedtora-array"></a><a name="dtor"></a>~ tableau 

 Détruit le `array` objet.  
  
```  
~array() restrict(cpu);
```  
  
##  <a name="a-nameacceleratorviewa-acceleratorview"></a><a name="accelerator_view"></a>accelerator_view 

 Obtient le [accelerator_view](accelerator-view-class.md) objet qui représente l’emplacement où le tableau est alloué. Cette propriété est accessible uniquement sur le processeur.  
  
```  
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;  
```  
  
##  <a name="a-namectora-array"></a><a name="ctor"></a>tableau 

 Initialise une nouvelle instance de la [array, classe](array-class.md). Aucun constructeur par défaut pour `array<T,N>`. Tous les constructeurs sont exécutés sur le processeur uniquement. Elles ne peuvent pas être exécutées sur une cible de Direct3D.  
  
```  
explicit array(  
    const Concurrency::extent<_Rank>& _Extent) restrict(cpu);  
  
explicit array(  
    int _E0) restrict(cpu);  
  
explicit array(  
    int _E0,  
    int _E1) restrict(cpu);  
  
explicit array(  
    int _E0,  
    int _E1,  
    int _E2) restrict(cpu);  
  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    int _E0,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  

 
array(
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first, 
    _InputIterator _Src_last) restrict(cpu);
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(
    int _E0,  
    int _E1,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,    
    Concurrency::accelerator_view _Av,  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    const Concurrency::extent<_Rank>& _Extent,  
    _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    _InputIterator _Src_first,  
    _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
template <typename _InputIterator>  
array(  
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);  
  
explicit array(  
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);  
  
array(  
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);  
  
array(
    const array_view<const value_type, _Rank>& _Src,  
    accelerator_view _Av,  
    accelerator_view _Associated_Av) restrict(cpu);  
  
array(const array& _Other) restrict(cpu);  
  
array(array&& _Other) restrict(cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Associated_Av`  
 Un accelerator_view qui spécifie l’emplacement cible par défaut du tableau.  
  
 `_Av`  
 Un [accelerator_view](accelerator-view-class.md) objet qui spécifie l’emplacement du tableau.  
  
 `_Cpu_access_type`  
 L’élément [access_type](concurrency-namespace-enums-amp.md#access_type) pour le groupe de l’unité centrale. Ce paramètre a la valeur par défaut `access_type_auto` en laissant le processeur `access_type` détermination à l’exécution. Le processeur réel `access_type` pour le tableau peut être interrogé à l’aide de la `get_cpu_access_type` méthode.  
  
 `_Extent`  
 L’étendue de chaque dimension du tableau.  
  
 `_E0`  
 Le composant plus significatif de l’étendue de cette section.  
  
 `_E1`  
 Le composant suivant-à-plus significatif de l’étendue de cette section.  
  
 `_E2`  
 Le composant moins important de l’étendue de cette section.  
  
 `_InputIterator`  
 Le type de l’entrée interator.  
  
 `_Src`  
 Pour l’objet à copier.  
  
 `_Src_first`  
 Un itérateur de début dans le conteneur source.  
  
 `_Src_last`  
 Un itérateur de fin dans le conteneur source.  
  
 `_Other`  
 Autre source de données.  
  
 `_Rank`  
 Le classement de la section.  
  
 `value_type`  
 Le type de données des éléments qui sont copiés.  
  
##  <a name="a-nameassociatedacceleratorviewa-associatedacceleratorview"></a><a name="associated_accelerator_view"></a>associated_accelerator_view 

 Obtient le second [accelerator_view](accelerator-view-class.md) objet passé en tant que paramètre lorsqu’une zone de transit est appelé pour instancier le `array` objet.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="a-namecopytoa-copyto"></a><a name="copy_to"></a>copy_to 

 Copie le contenu de la `array` à un autre `array`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const ;  
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Dest`  
 Le [array_view](array-view-class.md) objet de destination.  
  
##  <a name="a-namecpuaccesstypea-cpuaccesstype"></a><a name="cpu_access_type"></a>cpu_access_type 

 Obtient l’access_type UC autorisées pour ce tableau.  
  
```  
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;  
```  
  
##  <a name="a-namedataa-data"></a><a name="data"></a>données 

 Retourne un pointeur vers les données brutes de la `array`.  
  
```  
value_type* data() restrict(amp, cpu);
  
const value_type* data() const restrict(amp, cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers les données brutes du tableau.  
  
##  <a name="a-nameextenta-extent"></a><a name="extent"></a>étendue 

 Obtient le [étendue](extent-class.md) objet qui définit la forme de la `array`.  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namegetacceleratorviewa-getacceleratorview"></a><a name="get_accelerator_view"></a>get_accelerator_view 

 Retourne le [accelerator_view](accelerator-view-class.md) objet qui représente l’emplacement où le `array` objet est alloué. Cette propriété est accessible uniquement sur le processeur.  
  
```  
Concurrency::accelerator_view get_accelerator_view() const;  
```    
  
### <a name="return-value"></a>Valeur de retour  
 Le `accelerator_view` objet qui représente l’emplacement où le `array` objet est alloué.  
  
##  <a name="a-namegetassociatedacceleratorviewa-getassociatedacceleratorview"></a><a name="get_associated_accelerator_view"></a>get_associated_accelerator_view 

 Obtient le second [accelerator_view](accelerator-view-class.md) objet passé en tant que paramètre lorsqu’une zone de transit est appelé pour instancier le `array` objet.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const ;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La seconde [accelerator_view](accelerator-view-class.md) objet passé au constructeur intermédiaire.  
  
##  <a name="a-namegetcpuaccesstypea-getcpuaccesstype"></a><a name="get_cpu_access_type"></a>get_cpu_access_type 

 Access_type renvoie le processeur qui est autorisée pour ce tableau.  
  
```  
access_type get_cpu_access_type() const restrict(cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-namegetextenta-getextent"></a><a name="get_extent"></a>get_extent 

 Retourne le [étendue](extent-class.md) objet de la `array`.  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le `extent` objet de la `array`.  
  
##  <a name="a-nameoperatorveca-operator-stdvectorltvaluetypegt"></a><a name="operator_vec"></a>opérateur std::vector&lt;value_type&gt; 

 Utilise `copy(*this, vector)` convertir implicitement le tableau à un objet std::vector.  
  
```  
operator std::vector<value_type>() const restrict(cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `value_type`  
 Le type de données des éléments du vecteur.  
  
### <a name="return-value"></a>Valeur de retour  
 Un objet de type `vector<T>` qui contient une copie des données contenues dans le tableau.  
  
##  <a name="a-nameoperatorcalla-operator"></a><a name="operator_call"></a>operator() 

 Retourne la valeur de l’élément spécifié par les paramètres.  
  
```  
value_type& operator() (const index<_Rank>& _Index) restrict(amp,cpu);  
  
const value_type& operator() (const index<_Rank>& _Index) cons  t restrict(amp,cpu);
  
value_type& operator() (int _I0, int _I1) restrict(amp,cpu);  
  
const value_type& operator() (int _I0, int _I1) const restrict(amp,cpu)  ;
  
value_type& operator() (int _I0, int _I1, int _I2) restrict(amp,cpu);  
  
const value_type& operator() (int _I0, int _I1, int _I2) const restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator()(int _I) restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator()(int _I) const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 L’emplacement de l’élément.  
  
 `_I0`  
 Le composant plus significatif de l’origine de cette section.  
  
 `_I1`  
 Le composant suivant-à-plus significatif de l’origine de cette section.  
  
 `_I2`  
 Le composant moins significatif de l’origine de cette section.  
  
 `_I`  
 L’emplacement de l’élément.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur d’élément spécifiée par les paramètres.  
  
##  <a name="a-nameoperatorata-operator"></a><a name="operator_at"></a>operator] 

 Retourne l’élément situé à l’index spécifié.  
  
```  
value_type& operator[](const index<_Rank>& _Index) restrict(amp,cpu);  
  
const value_type& operator[]  
    (const index<_Rank>& _Index) const restrict(amp,cpu);  
  
typename details::_Projection_result_type<value_type,_Rank>::_Result_type operator[](int _i) restrict(amp,cpu);
  
typename details::_Projection_result_type<value_type,_Rank>::_Const_result_type operator[](int _i) const restrict(amp,cpu);
```  
    
### <a name="parameters"></a>Paramètres  
 `_Index`  
 Index.  
  
 `_I`  
 Index.  
  
### <a name="return-value"></a>Valeur de retour  
 L’élément qui est à l’index spécifié.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>opérateur = 

 Copie le contenu de l’objet `array` objet.  
  
```  
array& operator= (const array& _Other) restrict(cpu);  
   
array& operator= (array&& _Other) restrict(cpu);  
 
array& operator= (  
    const array_view<const value_type, _Rank>& _Src) restrict(cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `array` objet d’origine.  
  
 `_Src`  
 Le `array` objet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `array` objet.  
  
##  <a name="a-nameranka-rank"></a><a name="rank"></a>rang 

 Stocke le rang de la `array`.  
  
```  
static const int rank = _Rank;  
```  
## <a name="a-namereinterpretasa-reinterpretas"></a><a name="reinterpret_as"></a>reinterpret_as 

Réinterprète groupe via un array_view unidimensionnel, qui peut être un type de valeur différente de la baie source.

### <a name="syntax"></a>Syntaxe
``` 
template <typename _Value_type2>  
array_view<_Value_type2,1> reinterpret_as() restrict(amp,cpu);  
  
template <typename _Value_type2>  
array_view<const _Value_type2, 1> reinterpret_as() const restrict(amp,cpu);  
``` 
  
### <a name="parameters"></a>Paramètres  
`_Value_type2`Le type de données des données retournées.

### <a name="return-value"></a>Valeur de retour
Un array_view ou un objet const array_view qui est basé sur le tableau, avec le type d’élément réinterprétée dans T ElementType et le rang réduit de N à 1.

### <a name="remarks"></a>Remarques
Il est parfois commode afficher un tableau multidimensionnel, comme si elle était un tableau unidimensionnel linéaire, éventuellement avec un type de valeur différente que le tableau source. Vous pouvez utiliser cette méthode pour y parvenir.
**Attention** réinterprétation un objet tableau à l’aide d’un type valeur différent est une opération potentiellement dangereuse. Nous vous recommandons d’utiliser cette fonctionnalité avec précaution. 

Le code suivant fournit un exemple.

```cpp  
struct RGB { float r; float g; float b; };

array<RGB,3>  a = ...; 
array_view<float,1> v = a.reinterpret_as<float>(); 

assert(v.extent == 3*a.extent);
```  
  
##  <a name="a-namesectiona-section"></a><a name="section"></a>section 

 Retourne une sous-section de le `array` objet qui est à l’origine spécifiée et, éventuellement, qui a l’étendue spécifiée.  
  
```  
array_view<value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const Concurrency::index<_Rank>& _Section_origin,  
    const Concurrency::extent<_Rank>& _Section_extent) const restrict(amp,cpu);
  
array_view<value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const Concurrency::extent<_Rank>& _Ext) const restrict(amp,cpu);
  
array_view<value_type,_Rank> section(
    const index<_Rank>& _Idx) restrict(amp,cpu);
  
array_view<const value_type,_Rank> section(
    const index<_Rank>& _Idx) const restrict(amp,cpu);
  
array_view<value_type,1> section(
    int _I0,  
    int _E0) restrict(amp,cpu);
  
array_view<const value_type,1> section(
    int _I0,  
    int _E0) const restrict(amp,cpu);
  
array_view<value_type,2> section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) restrict(amp,cpu);
  
array_view<const value_type,2> section(
    int _I0,  
    int _I1,  
    int _E0,  
    int _E1) const restrict(amp,cpu);
  
array_view<value_type,3> section(
    int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    int _E2) restrict(amp,cpu);
  
array_view<const value_type,3> section(
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
  
 `value_type`  
 Le type de données des éléments qui sont copiés.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une sous-section de le `array` objet qui est à l’origine spécifiée et, éventuellement, qui a l’étendue spécifiée. Lorsque seul le `index` objet est spécifié, la sous-section contienne tous les éléments dans la grille associée qui ont des index supérieurs à l’index des éléments dans le `index` objet.  
  
##  <a name="a-nameviewasa-viewas"></a><a name="view_as"></a>view_as 

 Réinterprète ce tableau comme une [array_view](array-view-class.md) d’un rang différent.  
  
```  
template <int _New_rank>  
array_view<value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) restrict(amp,cpu);

 
template <int _New_rank>  
array_view<const value_type,_New_rank> view_as(
    const Concurrency::extent<_New_rank>& _View_extent) const restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_New_rank`  
 Le classement de la `extent` objet passé comme paramètre.  
  
 `_View_extent`  
 L’étendue qui est utilisé pour construire la nouvelle [array_view](array-view-class.md) objet.  
  
 `value_type`  
 Le type de données des éléments dans les deux d’origine `array` objet et retourné `array_view` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Le [array_view](array-view-class.md) objet construit.  
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

