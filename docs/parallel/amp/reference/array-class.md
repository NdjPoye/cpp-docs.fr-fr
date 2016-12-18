---
title: "array, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::array"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "array (classe)"
ms.assetid: 0832b6c1-40f0-421d-9104-6b1baa0c63a7
caps.latest.revision: 31
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# array, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représente un conteneur de données utilisé pour déplacer des données vers un accélérateur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
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
|[Array::Array, constructeur](#array__array_constructor)|Initialise une nouvelle instance de la classe `array`.|  
|[tableau :: ~ array, destructeur](#array___dtorarray_destructor)|Détruit le `array` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Array::copy_to, méthode](#array__copy_to_method)|Copie le contenu du tableau dans un autre tableau.|  
|[Array::Data, méthode](#array__data_method)|Retourne un pointeur vers les données brutes du tableau.|  
|[Array::get_accelerator_view, méthode](#array__get_accelerator_view_method)|Retourne le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet qui représente l’emplacement où le tableau est alloué. Cette propriété est accessible uniquement sur le processeur.|  
|[Array::get_associated_accelerator_view, méthode](#array__get_associated_accelerator_view_method)|Obtient le second [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet passé en tant que paramètre lorsqu’une zone de transit est appelé pour instancier le [tableau](../../../parallel/amp/reference/array-class.md) objet.|  
|[Array::get_cpu_access_type, méthode](#array__get_cpu_access_type_method)|Retourne le [access_type](access_type%20Enumeration.md) du tableau. Cette méthode est accessible uniquement sur le processeur.|  
|[Array::get_extent, méthode](#array__get_extent_method)|Retourne le [étendue](../../../parallel/amp/reference/extent-class-cpp-amp.md) objet du tableau.|  
|[Array::reinterpret_as, méthode](#array__reinterpret_as_method)|Retourne un tableau unidimensionnel qui contienne tous les éléments dans le `array` objet.|  
|[Array::section, méthode](#array__section_method)|Retourne une sous-section de le [tableau](../../../parallel/amp/reference/array-class.md) objet qui est à l’origine spécifiée et, éventuellement, qui a l’étendue spécifiée.|  
|[Array::view_as, méthode](#array__view_as_method)|Retourne un [array_view](../../../parallel/amp/reference/array-view-class.md) objet construit à partir de la `array` objet.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Array::operator std::vector&lt;value_type&gt; (opérateur)](#array__operator_std__vector_lt__value_type_gt__operator)|Utilise `copy(*this, vector)` pour être converti implicitement en tableau un std ::[vecteur](vector%20Class.md) objet.|  
|[Array::operator (opérateur)](#array__operator___operator)|Retourne la valeur de l’élément spécifié par les paramètres.|  
|[Array::operator [] (opérateur)](#array__operator_at_operator)|Retourne l’élément situé à l’index spécifié.|  
|[Array::operator =, opérateur](#array__operator_eq_operator)|Copie le contenu de l’objet `array` objet dans celui-ci.|  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Array::RANK, constante](#array__rank_constant)|Stocke le rang du tableau.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Array::accelerator_view, données membres](#array__accelerator_view_data_member)|Obtient le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet qui représente l’emplacement où le tableau est alloué. Cette propriété est accessible uniquement sur le processeur.|  
|[Array::associated_accelerator_view, données membres](#array__associated_accelerator_view_data_member)|Obtient le second [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet passé en tant que paramètre lorsqu’une zone de transit est appelé pour instancier le [tableau](../../../parallel/amp/reference/array-class.md) objet.|  
|[Array::cpu_access_type, membre de données](#array__cpu_access_type_data_member)|Obtient le [access_type](access_type%20Enumeration.md) qui représente la façon dont le processeur peut accéder au stockage du tableau.|  
|[Array::Extent, données membres](#array__extent_data_member)|Obtient l’étendue qui définit la forme du tableau.|  
  
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
  
##  <a name="a-namearraydtorarraydestructora-arrayarray-destructor"></a><a name="array___dtorarray_destructor"></a>  tableau :: ~ array, destructeur  
 Détruit le `array` objet.  
  
```  
~array() restrict(cpu);
```  
  
##  <a name="a-namearrayacceleratorviewdatamembera-arrayacceleratorview-data-member"></a><a name="array__accelerator_view_data_member"></a>  Array::accelerator_view, données membres  
 Obtient le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet qui représente l’emplacement où le tableau est alloué. Cette propriété est accessible uniquement sur le processeur.  
  
```  
__declspec(property(get= get_accelerator_view)) Concurrency::accelerator_view accelerator_view;  
```  
  
##  <a name="a-namearrayarrayconstructora-arrayarray-constructor"></a><a name="array__array_constructor"></a>  Array::Array, constructeur  
 Initialise une nouvelle instance de la [array, classe](../../../parallel/amp/reference/array-class.md). Aucun constructeur par défaut pour `array<T,N>`. Tous les constructeurs sont exécutés sur le processeur uniquement. Elles ne peuvent pas être exécutées sur une cible de Direct3D.  
  
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

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av  
    access_type _Cpu_access_type = access_type_auto) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    const Concurrency::extent<_Rank>& _Extent, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1, _InputIterator _Src_first,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
array(
    int _E0,  
    int _E1,  
    int _E2, _InputIterator _Src_first, _InputIterator _Src_last,  
    Concurrency::accelerator_view _Av,  
    Concurrency::accelerator_view _Associated_Av) restrict(cpu);

 
template <
    typename _InputIterator  
>  
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

 
array(
    const array& _Other) restrict(cpu);

 
array(
    array&& _Other) restrict(cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Associated_Av`  
 Un accelerator_view qui spécifie l’emplacement cible par défaut du tableau.  
  
 `_Av`  
 Un [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet qui spécifie l’emplacement du tableau.  
  
 `_Cpu_access_type`  
 L’élément [access_type](access_type%20Enumeration.md)  pour le groupe de l’unité centrale. Ce paramètre a la valeur par défaut `access_type_auto` en laissant le processeur `access_type` détermination à l’exécution. Le processeur réel `access_type` pour le tableau peut être interrogé à l’aide de la `get_cpu_access_type` méthode.  
  
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
  
##  <a name="a-namearrayassociatedacceleratorviewdatamembera-arrayassociatedacceleratorview-data-member"></a><a name="array__associated_accelerator_view_data_member"></a>  Array::associated_accelerator_view, données membres  
 Obtient le second [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet passé en tant que paramètre lorsqu’une zone de transit est appelé pour instancier le [tableau](../../../parallel/amp/reference/array-class.md) objet.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="a-namearraycopytomethoda-arraycopyto-method"></a><a name="array__copy_to_method"></a>  Array::copy_to, méthode  
 Copie le contenu de le [tableau](../../../parallel/amp/reference/array-class.md) à un autre `array`.  
  
```  
void copy_to(
    array<value_type, _Rank>& _Dest) const ;  
 
void copy_to(
    array_view<value_type, _Rank>& _Dest) const ;  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Dest`  
 Le [array_view](../../../parallel/amp/reference/array-view-class.md) objet de destination.  
  
##  <a name="a-namearraycpuaccesstypedatamembera-arraycpuaccesstype-data-member"></a><a name="array__cpu_access_type_data_member"></a>  Array::cpu_access_type, membre de données  
 Obtient l’access_type UC autorisées pour ce tableau.  
  
```  
__declspec(property(get= get_cpu_access_type)) access_type cpu_access_type;  
```  
  
##  <a name="a-namearraydatamethoda-arraydata-method"></a><a name="array__data_method"></a>  Array::Data, méthode  
 Retourne un pointeur vers les données brutes de le [tableau](../../../parallel/amp/reference/array-class.md).  
  
```  
value_type* data() restrict(amp,
    cpu);

 
const value_type* data() const restrict(amp,
    cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers les données brutes du tableau.  
  
##  <a name="a-namearrayextentdatamembera-arrayextent-data-member"></a><a name="array__extent_data_member"></a>  Array::Extent, données membres  
 Obtient le [étendue](../../../parallel/amp/reference/extent-class-cpp-amp.md) objet qui définit la forme de le [tableau](../../../parallel/amp/reference/array-class.md).  
  
```  
__declspec(property(get= get_extent)) Concurrency::extent<_Rank> extent;  
```  
  
##  <a name="a-namearraygetacceleratorviewmethoda-arraygetacceleratorview-method"></a><a name="array__get_accelerator_view_method"></a>  Array::get_accelerator_view, méthode  
 Retourne le [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet qui représente l’emplacement où le [tableau](../../../parallel/amp/reference/array-class.md) objet est alloué. Cette propriété est accessible uniquement sur le processeur.  
  
```  
Concurrency::accelerator_view get_accelerator_view() const;

 
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le `accelerator_view` objet qui représente l’emplacement où le [tableau](../../../parallel/amp/reference/array-class.md) objet est alloué.  
  
##  <a name="a-namearraygetassociatedacceleratorviewmethoda-arraygetassociatedacceleratorview-method"></a><a name="array__get_associated_accelerator_view_method"></a>  Array::get_associated_accelerator_view, méthode  
 Obtient le second [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet passé en tant que paramètre lorsqu’une zone de transit est appelé pour instancier le [tableau](../../../parallel/amp/reference/array-class.md) objet.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const ;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La seconde [accelerator_view](../../../parallel/amp/reference/accelerator-view-class.md) objet passé au constructeur intermédiaire.  
  
##  <a name="a-namearraygetcpuaccesstypemethoda-arraygetcpuaccesstype-method"></a><a name="array__get_cpu_access_type_method"></a>  Array::get_cpu_access_type, méthode  
 Access_type renvoie le processeur qui est autorisée pour ce tableau.  
  
```  
access_type get_cpu_access_type() const restrict(cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
  
##  <a name="a-namearraygetextentmethoda-arraygetextent-method"></a><a name="array__get_extent_method"></a>  Array::get_extent, méthode  
 Retourne le [étendue](../../../parallel/amp/reference/extent-class-cpp-amp.md) objet de le [tableau](../../../parallel/amp/reference/array-class.md).  
  
```  
Concurrency::extent<_Rank> get_extent() const restrict(amp,cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le `extent` objet de le [tableau](../../../parallel/amp/reference/array-class.md).  
  
##  <a name="a-namearrayoperatorstdvectorltvaluetypegtoperatora-arrayoperator-stdvectorltvaluetypegt-operator"></a><a name="array__operator_std__vector_lt__value_type_gt__operator"></a>  Array::operator std::vector&lt;value_type&gt; (opérateur)  
 Utilise `copy(*this, vector)` convertir implicitement le tableau à un objet std::vector.  
  
''' opérateur std::vector \< value_type > () const Restrict (CPU) ;
```  
  
### Parameters  
 `value_type`  
 The data type of the elements of the vector.  
  
### Return Value  
 An object of type `vector<T>` that contains a copy of the data that is contained in the array.  
  
##  <a name="array__operator___operator"></a>  array::operator() Operator  
 Returns the element value that is specified by the parameters.  
  
```  
Value_type & operator() (const index \< _Rank > & _Index) restrict(amp,cpu) ;

 
const value_type & operator() (const index \< _Rank > & _Index) restrict(amp,cpu) const ;

 
Value_type & restrict(amp,cpu) operator() (int _I0, int _I1) ;

 
value_type const & restrict(amp,cpu) const operator() (int _I0, int _I1) ;

 
Value_type & restrict(amp,cpu) operator() (int _I0, int _I1, int _I2) ;

 
value_type const & restrict(amp,cpu) const operator() (int _I0, int _I1, int _I2) ;

 
TypeName details::_Projection_result_type \< value_type, _Rank > :: _Result_type restrict(amp,cpu) de operator() (int _I) ;

 
TypeName details::_Projection_result_type \< value_type, _Rank > :: restrict(amp,cpu) const de _Const_result_type operator() (int _I) ;
```  
  
### Parameters  
 `_Index`  
 The location of the element.  
  
 `_I0`  
 The most significant component of the origin of this section.  
  
 `_I1`  
 The next-to-most-significant component of the origin of this section.  
  
 `_I2`  
 The least significant component of the origin of this section.  
  
 `_I`  
 The location of the element.  
  
### Return Value  
 The element value specified by the parameters.  
  
##  <a name="array__operator_at_operator"></a>  array::operator[] Operator  
 Returns the element that is at the specified index.  
  
```  
[] Value_type & (opérateur) (const index \< _Rank > & _Index) restrict(amp,cpu) ;

 
[] d’opérateur & value_type const (const index \< _Rank > & _Index) restrict(amp,cpu) const ;

 
TypeName details::_Projection_result_type \< value_type, _Rank > :: _Result_type opérateur[](int _I) restrict(amp,cpu) ;

 
TypeName details::_Projection_result_type \< value_type, _Rank > :: _Const_result_type opérateur[](int _I) restrict(amp,cpu) const ;
```  
  
### Parameters  
 `_Index`  
 The index.  
  
 `_I`  
 The index.  
  
### Return Value  
 The element that is at the specified index.  
  
##  <a name="array__operator_eq_operator"></a>  array::operator= Operator  
 Copies the contents of the specified [array](../../../parallel/amp/reference/array-class.md) object.  
  
```  
opérateur & tableau = (tableau const & _Other) Restrict (CPU) ;

 
opérateur & tableau = (tableau & & _Other) Restrict (CPU) ;

 
opérateur & tableau = (array_view const \< value_type const, _Rank > & _Src) Restrict (CPU) ;
```  
  
### Parameters  
 `_Other`  
 The `array` object to copy from.  
  
 `_Src`  
 The `array` object to copy from.  
  
### Return Value  
 A reference to this `array` object.  
  
##  <a name="array__rank_constant"></a>  array::rank Constant  
 Stores the rank of the [array](../../../parallel/amp/reference/array-class.md).  
  
```  
rang d’int const static = _Rank ;  
```  
  
##  <a name="array__section_method"></a>  array::section Method  
 Returns a subsection of the [array](../../../parallel/amp/reference/array-class.md) object that is at the specified origin and, optionally, that has the specified extent.  
  
```  
array_view \< value_type, _Rank > section (const Concurrency::index \< _Rank > & _Section_origin,  
    const Concurrency::extent \< _Rank > & _Section_extent) restrict(amp,cpu) ;

 
array_view \< value_type const, _Rank > section (const Concurrency::index \< _Rank > & _Section_origin,  
    const Concurrency::extent \< _Rank > & _Section_extent) restrict(amp,cpu) const ;

 
array_view \< value_type, _Rank > section (const Concurrency::extent \< _Rank > & _Ext) restrict(amp,cpu) ;

 
array_view \< value_type const, _Rank > section (const Concurrency::extent \< _Rank > & _Ext) restrict(amp,cpu) const ;

 
array_view \< value_type, _Rank > section (const index \< _Rank > & IDX) restrict(amp,cpu) ;

 
array_view \< value_type const, _Rank > section (const index \< _Rank > & IDX) restrict(amp,cpu) const ;

 
array_view \< value_type, 1 > section (int _I0,  
    restrict(amp,cpu) _E0 int) ;

 
array_view \< const value_type, 1 > section (int _I0,  
    restrict(amp,cpu) const int _E0) ;

 
array_view \< value_type, 2 > section (int _I0,  
    int _I1,  
    int _E0,  
    restrict(amp,cpu) _E1 int) ;

 
array_view \< const value_type, 2 > section (int _I0,  
    int _I1,  
    int _E0,  
    restrict(amp,cpu) const int _E1) ;

 
array_view \< value_type, 3 > section (int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    restrict(amp,cpu) _E2 int) ;

 
array_view \< const value_type, 3 > section (int _I0,  
    int _I1,  
    int _I2,  
    int _E0,  
    int _E1,  
    restrict(amp,cpu) const int _E2) ;
```  
  
### Parameters  
 `_E0`  
 The most significant component of the extent of this section.  
  
 `_E1`  
 The next-to-most-significant component of the extent of this section.  
  
 `_E2`  
 The least significant component of the extent of this section.  
  
 `_Ext`  
 The [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md) object that specifies the extent of the section. The origin is 0.  
  
 `_Idx`  
 The [index](../../../parallel/amp/reference/index-class.md) object that specifies the location of the origin. The subsection is the rest of the extent.  
  
 `_I0`  
 The most significant component of the origin of this section.  
  
 `_I1`  
 The next-to-most-significant component of the origin of this section.  
  
 `_I2`  
 The least significant component of the origin of this section.  
  
 `_Rank`  
 The rank of the section.  
  
 `_Section_extent`  
 The [extent](../../../parallel/amp/reference/extent-class-cpp-amp.md) object that specifies the extent of the section.  
  
 `_Section_origin`  
 The [index](../../../parallel/amp/reference/index-class.md) object that specifies the location of the origin.  
  
 `value_type`  
 The data type of the elements that are copied.  
  
### Return Value  
 Returns a subsection of the `array` object that is at the specified origin and, optionally, that has the specified extent. When only the `index` object is specified, the subsection contains all elements in the associated grid that have indexes that are larger than the indexes of the elements in the `index` object.  
  
##  <a name="array__view_as_method"></a>  array::view_as Method  
 Reinterprets this array as an [array_view](../../../parallel/amp/reference/array-view-class.md) of a different rank.  
  
```  
modèle \< int _New_rank  
>  
array_view \< value_type, _New_rank > view_as (const Concurrency::extent \< _New_rank > & _View_extent) restrict(amp,cpu) ;

 
modèle \< int _New_rank  
>  
array_view \< value_type const, _New_rank > view_as (const Concurrency::extent \< _New_rank > & _View_extent) restrict(amp,cpu) const ;
```  
  
### Parameters  
 `_New_rank`  
 The rank of the `extent` object passed as a parameter.  
  
 `_View_extent`  
 The extent that is used to construct the new [array_view](../../../parallel/amp/reference/array-view-class.md) object.  
  
 `value_type`  
 The data type of the elements in both the original [array](../../../parallel/amp/reference/array-class.md) object and the returned `array_view` object.  
  
### Return Value  
 The [array_view](../../../parallel/amp/reference/array-view-class.md) object that is constructed.  
  
## See Also  
 [Concurrency Namespace (C++ AMP)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)
