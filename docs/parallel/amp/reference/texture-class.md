---
title: texture, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_graphics/Concurrency::graphics::texture
dev_langs:
- C++
ms.assetid: 16e85d4d-e80a-474a-995d-8bf63fbdf34c
caps.latest.revision: 9
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
ms.openlocfilehash: aafb23ac4d366baed37f1cf667984253160af9c3
ms.lasthandoff: 02/24/2017

---
# <a name="texture-class"></a>texture, classe
Une texture est un agrégat de données un `accelerator_view` dans le domaine de l’étendue. Il est une collection de variables, un pour chaque élément dans un domaine de l’étendue. Chaque variable contient une valeur correspondant à un type primitif C++ ( `unsigned int`, `int`, `float`, `double`), un type scalaire ( `norm`, ou `unorm`), ou un type de vecteur court.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
class texture;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `value_type`  
 Le type des éléments de la texture.  
  
 `_Rank`  
 Le classement de la texture.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`scalar_type`|Types scalaires.|  
|`value_type`|Types de valeur.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[texture, constructeur](#ctor)|Initialise une nouvelle instance de la classe `texture`.|  
|[~ texture, destructeur](#ctor)|Détruit le `texture` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[copy_to (méthode)](#copy_to)|Copie le `texture` objet vers la destination, en effectuant une copie complète.|  
|[données (méthode)](#data)|Retourne un pointeur de processeur pour les données brutes de cette texture.|  
|[Get (méthode)](#get)|Retourne la valeur de l’élément à l’index spécifié.|  
|[get_associated_accelerator_view (méthode)](#get_associated_accelerator_view)|Retourne le [accelerator_view](accelerator-view-class.md) qui est la cible par défaut pour cette texture à copier vers.|  
|[get_depth_pitch (méthode)](#get_depth_pitch)|Retourne le nombre d’octets entre chaque tranche de profondeur dans 3D intermédiaire texture sur le processeur.|  
|[get_row_pitch (méthode)](#get_row_pitch)|Retourne le nombre d’octets entre chaque ligne d’un 2D ou la 3D intermédiaire texture sur le processeur.|  
|[Set, méthode](#set)|Définit la valeur de l’élément à l’index spécifié.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[operator() (opérateur)](#operator_call)|Retourne la valeur de l’élément spécifié par les paramètres.|  
|[operator [] (opérateur)](#operator_at)|Retourne l’élément situé à l’index spécifié.|  
|[opérateur =, opérateur](#operator_eq)|Copie le texte spécifié [texture](texture-class.md) objet à celui-ci.|  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[RANK (constante)](#rank)|Obtient le classement de la `texture` objet.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[associated_accelerator_view (donnée membre)](#associated_accelerator_view)|Obtient le [accelerator_view](accelerator-view-class.md) qui est la cible par défaut pour cette texture à copier vers.|  
|[depth_pitch (donnée membre)](#depth_pitch)|Obtient le nombre d’octets entre chaque tranche de profondeur dans une texture 3D intermédiaire sur le processeur.|  
|[row_pitch (donnée membre)](#row_pitch)|Obtient le nombre d’octets entre chaque ligne d’un 2D ou 3D un intermédiaire texture sur le processeur.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `_Texture_base`  
  
 `texture`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_graphics.h  
  
 **Namespace :** Concurrency::graphics  
  
##  <a name="a-namedtora-texture"></a><a name="dtor"></a>~ texture 

 Détruit le `texture` objet.  
  
```  
~texture() restrict(cpu);
```  
  
##  <a name="a-nameassociatedacceleratorviewa-associatedacceleratorview"></a><a name="associated_accelerator_view"></a>associated_accelerator_view 

 Obtient le [accelerator_view](accelerator-view-class.md) qui est la cible par défaut pour cette texture à copier vers.  
  
```  
__declspec(property(get= get_associated_accelerator_view)) Concurrency::accelerator_view associated_accelerator_view;  
```  
  
##  <a name="a-namecopytoa-copyto"></a><a name="copy_to"></a>copy_to 

 Copie le `texture` objet vers la destination, en effectuant une copie complète.  
  
```  
void copy_to(
    texture& _Dest) const;

 
 
void copy_to(
    writeonly_texture_view<value_type, _Rank>& _Dest) const;

 
```  
  
### <a name="parameters"></a>Paramètres  
 `_Dest`  
 L’objet de destination.  
  
 `_Rank`  
 Le classement de la texture.  
  
 `value_type`  
 Le type des éléments de la texture.  
  
##  <a name="a-namedataa-data"></a><a name="data"></a>données 

 Retourne un pointeur de processeur pour les données brutes de cette texture.  
  
```  
void* data() restrict(cpu);

 
const void* data() const restrict(cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers les données brutes de la texture.  
  
##  <a name="a-namedepthpitcha-depthpitch"></a><a name="depth_pitch"></a>depth_pitch 

 Obtient le nombre d’octets entre chaque tranche de profondeur dans une texture 3D intermédiaire sur le processeur.  
  
```  
__declspec(property(get= get_depth_pitch)) unsigned int depth_pitch;  
```  
  
##  <a name="a-namegeta-get"></a><a name="get"></a>Télécharger 

 Retourne la valeur de l’élément à l’index spécifié.  
  
```  
const value_type get(const index<_Rank>& _Index) const restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 L’index de l’élément.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur de l’élément à l’index spécifié.  
  
##  <a name="a-namegetassociatedacceleratorviewa-getassociatedacceleratorview"></a><a name="get_associated_accelerator_view"></a>get_associated_accelerator_view 

 Retourne l’accelerator_view qui est la cible par défaut pour cette texture à copier vers.  
  
```  
Concurrency::accelerator_view get_associated_accelerator_view() const restrict(cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le [accelerator_view](accelerator-view-class.md) qui est la cible par défaut pour cette texture à copier vers.  
  
##  <a name="a-namegetdepthpitcha-getdepthpitch"></a><a name="get_depth_pitch"></a>get_depth_pitch 

 Retourne le nombre d’octets entre chaque tranche de profondeur dans 3D intermédiaire texture sur le processeur.  
  
```  
unsigned int get_depth_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’octets entre chaque tranche de profondeur dans 3D intermédiaire texture sur le processeur.  
  
##  <a name="a-namegetrowpitcha-getrowpitch"></a><a name="get_row_pitch"></a>get_row_pitch 

 Retourne le nombre d’octets entre chaque ligne d’une texture intermédiaire en 2 dimensions, ou entre chaque ligne d’une tranche de la profondeur de texture intermédiaire en 3 dimensions.  
  
```  
unsigned int get_row_pitch() const restrict(cpu);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’octets entre chaque ligne d’une texture intermédiaire en 2 dimensions, ou entre chaque ligne d’une tranche de la profondeur de texture intermédiaire en 3 dimensions.  
  
##  <a name="a-nameoperatorcalla-operator"></a><a name="operator_call"></a>operator() 

 Retourne la valeur de l’élément spécifié par les paramètres.  
  
```  
const value_type operator() (
    const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator() (
    int _I0) const restrict(amp);

 
const value_type operator() (
    int _I0,  
    int _I1) const restrict(amp);

 
const value_type operator() (
    int _I0,  
    int _I1,  
    int _I2) const restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 Index.  
  
 `_I0`  
 Le composant plus significatif de l’index.  
  
 `_I1`  
 Le composant suivant-à-plus significatif de l’index.  
  
 `_I2`  
 Le composant de poids de l’index.  
  
 `_Rank`  
 Le rang de l’index.  
  
### <a name="return-value"></a>Valeur de retour  
 La valeur de l’élément spécifié par les paramètres.  
  
##  <a name="a-nameoperatorata-operator"></a><a name="operator_at"></a>operator] 

 Retourne l’élément situé à l’index spécifié.  
  
```  
const value_type operator[] (const index<_Rank>& _Index) const restrict(amp);

 
const value_type operator[] (int _I0) const restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 Index.  
  
 `_I0`  
 Index.  
  
### <a name="return-value"></a>Valeur de retour  
 L’élément qui est à l’index spécifié.  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>opérateur = 

 Copie le texte spécifié [texture](texture-class.md) objet à celui-ci.  
  
```  
texture& operator= (
    const texture& _Other);

 
texture& operator= (
    texture<value_type, _Rank>&& _Other);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `texture` objet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `texture` objet.  
  
##  <a name="a-nameranka-rank"></a><a name="rank"></a>rang 

 Obtient le classement de la `texture` objet.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-namerowpitcha-rowpitch"></a><a name="row_pitch"></a>row_pitch 

 Obtient le nombre d’octets entre chaque ligne d’un 2D ou 3D un intermédiaire texture sur le processeur.  
  
```  
__declspec(property(get= get_row_pitch)) unsigned int row_pitch;  
```  
  
##  <a name="a-nameseta-set"></a><a name="set"></a>ensemble 

 Définit la valeur de l’élément à l’index spécifié.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 L’index de l’élément.  
  
 `_Rank`  
 Le rang de l’index.  
  
 `value`  
 Nouvelle valeur de l’élément.  
  
##  <a name="a-namectora-texture"></a><a name="ctor"></a>texture 

 Initialise une nouvelle instance de la classe `texture`.  
  
```  
texture(
    const Concurrency::extent<_Rank>& _Ext) restrict(cpu);

 
texture(
    int _E0) restrict(cpu);

 
texture(
    int _E0,  
    int _E1) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    const Concurrency::extent<_Rank>& _Ext, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1,  
    int _E2, _Input_iterator _Src_first, _Input_iterator _Src_last) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    const Concurrency::extent<_Rank>& _Ext, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
template<
    typename _Input_iterator  
>  
texture(
    int _E0,  
    int _E1,  
    int _E2, _Input_iterator _Src_first, _Input_iterator _Src_last,  
    const Concurrency::accelerator_view& _Av) restrict(cpu))  ;  
 
texture(
    int _E0,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av)  ;  
 
texture(
    int _E0,  
    int _E1,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element) restrict(cpu);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av)  ;  
 
texture(
    int _E0,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    int _E0,  
    int _E1,  
    int _E2,  
    _In_ void* _Source,  
    unsigned int _Src_byte_size,  
    unsigned int _Bits_per_scalar_element,  
    const Concurrency::accelerator_view& _Av) restrict(cpu);

 
texture(
    const texture& _Src,  
    const Concurrency::accelerator_view& _Acc_view);

 
texture(
    texture&& _Other);

 
texture(
    const Concurrency::extent<_Rank>& _Ext,   
    unsigned int _Bits_per_scalar_element,   
    const Concurrency::accelerator_view& _Av);

 
texture(
    const texture& _Src);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Acc_view`  
 Le [accelerator_view](accelerator-view-class.md) qui spécifie l’emplacement de la texture.  
  
 `_Av`  
 Le [accelerator_view](accelerator-view-class.md) qui spécifie l’emplacement de la texture.  
  
 `_Associated_av`  
 Accelerator_view qui spécifie une cible privilégiée pour les copies vers ou à partir de cette texture.  
  
 `_Bits_per_scalar_element`  
 Le nombre de bits par chaque élément scalaire de type scalaire sous-jacent de la texture. En général, la valeur prise en charge sont 8, 16, 32 et 64. Si 0 est spécifié, le nombre de bits est identique à la scalar_type sous-jacente. 64 est uniquement valide pour les textures double.  
  
 `_Ext`  
 L’étendue de chaque dimension de la texture.  
  
 `_E0`  
 Le composant plus significatif de la texture.  
  
 `_E1`  
 Le composant suivant-à-plus significatif de la texture.  
  
 `_E2`  
 Le composant moins important de l’étendue de la texture.  
  
 `_Input_iterator`  
 Le type de l’entrée interator.  
  
 `_Mipmap_levels`  
 Le nombre de niveaux de mipmap dans la texture sous-jacente. Si 0 est spécifié, la texture aura la gamme complète des niveaux de mipmap jusqu'à la plus petite taille possible pour l’étendue spécifiée.  
  
 `_Rank`  
 Le rang de l’étendue.  
  
 `_Source`  
 Pointeur vers un tampon de l’hôte.  
  
 `_Src`  
 Texture à copier.  
  
 `_Src_byte_size`  
 Le nombre d’octets dans la mémoire tampon source.  
  
 `_Src_first`  
 Un itérateur de début dans le conteneur source.  
  
 `_Src_last`  
 Un itérateur de fin dans le conteneur source.  
  
 `_Other`  
 Autre source de données.  
  
 `_Rank`  
 Le classement de la section.  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::Graphics Namespace](concurrency-graphics-namespace.md)

