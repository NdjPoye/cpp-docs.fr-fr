---
title: tiled_extent, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp/Concurrency::tiled_extent
dev_langs:
- C++
ms.assetid: 671ecaf8-c7b0-4ac8-bbdc-e30bd92da7c0
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
ms.openlocfilehash: c2f7ebdb9c82ae24cf74064e710ddfb177670359
ms.lasthandoff: 02/24/2017

---
# <a name="tiledextent-class"></a>tiled_extent, classe
A `tiled_extent` objet est un `extent` objet d’un à trois dimensions qui divise l’espace d’étendue en une, deux ou les vignettes en trois dimensions.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
template <
    int _Dim0,  
    int _Dim1,  
    int _Dim2  
>  
class tiled_extent : public Concurrency::extent<3>;  
 
template <
    int _Dim0,  
    int _Dim1  
>  
class tiled_extent<_Dim0, _Dim1, 0> : public Concurrency::extent<2>;  
 
template <
    int _Dim0  
>  
class tiled_extent<_Dim0, 0, 0> : public Concurrency::extent<1>;  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Dim0`  
 La longueur de la dimension la plus importante.  
  
 `_Dim1`  
 La longueur de la dimension importante suivant à la plupart des.  
  
 `_Dim2`  
 La longueur de la dimension moins significative.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[tiled_extent, constructeur](#ctor)|Initialise une nouvelle instance de la classe `tiled_extent`.|  

  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[get_tile_extent (méthode)](#tiled_extent__get_tile_extent)|Retourne un `extent` objet qui capture les valeurs de la `tiled_extent` arguments template `_Dim0`, `_Dim1`, et `_Dim2`.|  
|[Méthode de remplissage](#tiled_extent__pad)|Retourne un nouveau `tiled_extent` objet avec les extensions ajustée d’être divisible par les dimensions de la mosaïque.|  
|[Méthode TRUNCATE](#tiled_extent__truncate)|Retourne un nouveau `tiled_extent` objet avec extensions ajustée vers le bas pour être divisible par les dimensions de la mosaïque.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[opérateur =, opérateur](#operator_eq)|Copie le contenu de l’objet `tiled_index` objet dans celui-ci.|  

  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[tile_dim0 (constante)](#tiled_extent__tile_dim0)|Stocke la longueur de la dimension la plus importante.|  
|[tile_dim1 (constante)](#tiled_extent__tile_dim1)|Stocke la longueur de la dimension importante suivant au plus.|  
|[tile_dim2 (constante)](#tiled_extent__tile_dim2)|Stocke la longueur de la dimension moins significative.|  

  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[tile_extent (donnée membre)](#tiled_extent__tile_extent)|Obtient un `extent` objet qui capture les valeurs de la `tiled_extent` arguments template `_Dim0`, `_Dim1`, et `_Dim2`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `extent`  
  
 `tiled_extent`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp.h  
  
 **Espace de noms :** Concurrency  

## <a name="tiled_extent__ctor"></a> tiled_extent, constructeur  
Initialise une nouvelle instance de la classe `tiled_extent`.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
tiled_extent();  
  
tiled_extent(  
    const Concurrency::extent<rank>& _Other );  
  
tiled_extent(  
    const tiled_extent& _Other );  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `extent` ou `tiled_extent` objet à copier.  
  

  

## <a name="tiled_extent__get_tile_extent"></a> get_tile_extent   
Retourne un `extent` objet qui capture les valeurs de la `tiled_extent` arguments template `_Dim0`, `_Dim1`, et `_Dim2`.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
Concurrency::extent<rank> get_tile_extent() const restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `extent` objet qui capture les dimensions de ce `tiled_extent` instance.  
  

## <a name="tiled_extent__pad"></a>  pad   
Retourne un nouveau `tiled_extent` objet avec les extensions ajustée d’être divisible par les dimensions de la mosaïque.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
tiled_extent pad() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 La nouvelle `tiled_extent` objet par valeur. 
## <a name="tiled_extent__truncate"></a> truncate   
Retourne un nouveau `tiled_extent` objet avec extensions ajustée vers le bas pour être divisible par les dimensions de la mosaïque.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
tiled_extent truncate() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un nouveau `tiled_extent` objet avec extensions ajustée vers le bas pour être divisible par les dimensions de la mosaïque.  

## <a name="tiled_extent__operator_eq"></a> opérateur =   
Copie le contenu de l’objet `tiled_index` objet dans celui-ci.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
tiled_extent&  operator= (  
    const tiled_extent& _Other ) restrict (amp, cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `tiled_index` objet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `tiled_index` instance.  

## <a name="tiled_extent__tile_dim0"></a> tile_dim0   
Stocke la longueur de la dimension la plus importante.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
static const int tile_dim0 = _Dim0;  
```  
  
## <a name="tiled_extent__tile_dim1"></a> tile_dim1   
Stocke la longueur de la dimension importante suivant au plus.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
static const int tile_dim1 = _Dim1;  
```  
## <a name="tiled_extent__tile_dim2"></a> tile_dim2   
Stocke la longueur de la dimension moins significative.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
static const int tile_dim2 = _Dim2;  
```  
## <a name="tiled_extent__tile_extent"></a> tile_extent   
  Obtient un `extent` objet qui capture les valeurs de la `tiled_extent` arguments template `_Dim0`, `_Dim1`, et `_Dim2`.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
__declspec(property(get= get_tile_extent)) Concurrency::extent<rank> tile_extent;  
```  
  
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace (C++ AMP)](concurrency-namespace-cpp-amp.md)

