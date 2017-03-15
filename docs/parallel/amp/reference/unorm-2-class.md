---
title: unorm_2, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator+=
- amp_short_vectors/Concurrency::graphics::unnorm_2::y
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_y
- amp_short_vectors/Concurrency::graphics::unnorm_2::x
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator--
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator*=
- amp_short_vectors/Concurrency::graphics::unnorm_2::xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_y
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator=
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_x
- amp_short_vectors/Concurrency::graphics::unnorm_2::rg
- amp_short_vectors/Concurrency::graphics::unorm_2
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator-=
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator/=
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_xy
- amp_short_vectors/Concurrency::graphics::unnorm_2::set_yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::yx
- amp_short_vectors/Concurrency::graphics::unnorm_2::gr
- amp_short_vectors/Concurrency::graphics::unnorm_2::r
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator-
- amp_short_vectors/Concurrency::graphics::unnorm_2::get_x
- amp_short_vectors/Concurrency::graphics::unnorm_2::g
- amp_short_vectors/Concurrency::graphics::unnorm_2::operator++
dev_langs:
- C++
ms.assetid: 62e88ea7-e29f-4f62-95ce-61a1f39f5e34
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
ms.openlocfilehash: 8c4e7cd3040e9d9d6d3c3a5a915118fbc815aebf
ms.lasthandoff: 02/24/2017

---
# <a name="unorm2-class"></a>unorm_2, classe
Représente un vecteur court des deux nombres normaux non signés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class unorm_2;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[unorm_2 constructeur](#ctor)|Surchargé. Par défaut constructeur initialise tous les éléments à 0.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|unorm_2::get_X (méthode)||  
|unorm_2::get_xy (méthode)||  
|unorm_2::get_y (méthode)||  
|unorm_2::get_yx (méthode)||  
|unorm_2::ref_g (méthode)||  
|unorm_2::ref_r (méthode)||  
|unorm_2::ref_x (méthode)||  
|unorm_2::ref_y (méthode)||  
|unorm_2::set_X (méthode)||  
|unorm_2::set_xy (méthode)||  
|unorm_2::set_y (méthode)||  
|unorm_2::set_yx (méthode)||  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|unorm_2::operator--(opérateur)||  
|unorm_2::operator * =, opérateur||  
|unorm_2::operator / =, opérateur||  
|unorm_2::operator ++ (opérateur)||  
|unorm_2::operator +=, opérateur||  
|unorm_2::operator =, opérateur||  
|unorm_2::operator-= (opérateur)||  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|unorm_2::size, constante||  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|Membre de données unorm_2::g||  
|Membre de données unorm_2::GR||  
|Membre de données unorm_2::r||  
|Membre de données unorm_2::RG||  
|Membre de données unorm_2::x||  
|Membre de données unorm_2::XY||  
|Membre de données unorm_2::y||  
|Membre de données unorm_2::YX||  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `unorm_2`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_short_vectors.h  
  
 **Namespace :** Concurrency::graphics  
  
##  <a name="a-namectora-unorm2"></a><a name="ctor"></a>unorm_2 

 Par défaut constructeur initialise tous les éléments à 0.  
  
```  
unorm_2() restrict(amp,
    cpu);

 
unorm_2(
    unorm _V0,  
    unorm _V1) restrict(amp,
    cpu);

 
unorm_2(
    float _V0,  
    float _V1) restrict(amp,
    cpu);

 
unorm_2(
    unorm _V) restrict(amp,
    cpu);

 
explicit unorm_2(
    float _V) restrict(amp,
    cpu);

 
unorm_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
    const norm_2& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_2(
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
  
##  <a name="a-nameunorm2sizea-size"></a><a name="unorm_2__size"></a>taille 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::Graphics Namespace](concurrency-graphics-namespace.md)

