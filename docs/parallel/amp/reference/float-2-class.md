---
title: float_2, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::float_2::yx
- amp_short_vectors/Concurrency::graphics::float_2::operator-=
- amp_short_vectors/Concurrency::graphics::float_2::operator++
- amp_short_vectors/Concurrency::graphics::float_2::operator-
- amp_short_vectors/Concurrency::graphics::float_2::r
- amp_short_vectors/Concurrency::graphics::float_2::get_yx
- amp_short_vectors/Concurrency::graphics::float_2::get_xy
- amp_short_vectors/Concurrency::graphics::float_2::operator/=
- amp_short_vectors/Concurrency::graphics::float_2::set_yx
- amp_short_vectors/Concurrency::graphics::float_2::x
- amp_short_vectors/Concurrency::graphics::float_2::get_y
- amp_short_vectors/Concurrency::graphics::float_2::operator+=
- amp_short_vectors/Concurrency::graphics::float_2::gr
- amp_short_vectors/Concurrency::graphics::float_2::operator=
- amp_short_vectors/Concurrency::graphics::float_2::set_x
- amp_short_vectors/Concurrency::graphics::float_2::operator--
- amp_short_vectors/Concurrency::graphics::float_2::get_x
- amp_short_vectors/Concurrency::graphics::float_2::operator*=
- amp_short_vectors/Concurrency::graphics::float_2::rg
- amp_short_vectors/Concurrency::graphics::float_2::set_xy
- amp_short_vectors/Concurrency::graphics::float_2::xy
- amp_short_vectors/Concurrency::graphics::float_2
- amp_short_vectors/Concurrency::graphics::float_2::set_y
- amp_short_vectors/Concurrency::graphics::float_2::y
- amp_short_vectors/Concurrency::graphics::float_2::g
dev_langs:
- C++
ms.assetid: b3ebd48e-f8c8-4f00-a640-357f702f0cae
caps.latest.revision: 11
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
ms.openlocfilehash: 05707bd43a8f9b89a93c0da0011c46d67361fc84
ms.lasthandoff: 02/24/2017

---
# <a name="float2-class"></a>float_2, classe
Représente un vecteur court des deux nombres à virgule flottante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class float_2;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[float_2 constructeur](#ctor)|Surchargé. Par défaut constructeur initialise tous les éléments à 0.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|float_2::get_X (méthode)||  
|float_2::get_xy (méthode)||  
|float_2::get_y (méthode)||  
|float_2::get_yx (méthode)||  
|float_2::ref_g (méthode)||  
|float_2::ref_r (méthode)||  
|float_2::ref_x (méthode)||  
|float_2::ref_y (méthode)||  
|float_2::set_X (méthode)||  
|float_2::set_xy (méthode)||  
|float_2::set_y (méthode)||  
|float_2::set_yx (méthode)||  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|float_2::operator-(opérateur)||  
|float_2::operator--(opérateur)||  
|float_2::operator * =, opérateur||  
|float_2::operator / =, opérateur||  
|float_2::operator ++ (opérateur)||  
|float_2::operator +=, opérateur||  
|float_2::operator =, opérateur||  
|float_2::operator-= (opérateur)||  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[taille (constante)](#float_2__size)||  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|Membre de données float_2::g||  
|Membre de données float_2::GR||  
|Membre de données float_2::r||  
|Membre de données float_2::RG||  
|Membre de données float_2::x||  
|Membre de données float_2::XY||  
|Membre de données float_2::y||  
|Membre de données float_2::YX||  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `float_2`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_short_vectors.h  
  
 **Namespace :** Concurrency::graphics  
  
##  <a name="a-namectora-float2"></a><a name="ctor"></a>float_2 

 Par défaut constructeur initialise tous les éléments à 0.  
  
```  
float_2() restrict(amp,
    cpu);

 
float_2(
    float _V0,  
    float _V1) restrict(amp,
    cpu);

 
float_2(
    float _V) restrict(amp,
    cpu);

 
float_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const norm_2& _Other) restrict(amp,
    cpu);

 
explicit inline float_2(
    const double_2& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_V0`  
 La valeur pour initialiser l’élément 0.  
  
 `_V1`  
 La valeur pour initialiser l’élément 1.  
  
 `_V`  
 La valeur pour l’initialisation.  
  
 `_Other`  
 Objet utilisé pour initialiser.  
  
##  <a name="a-namefloat2sizea-size"></a><a name="float_2__size"></a>taille 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::Graphics Namespace](concurrency-graphics-namespace.md)

