---
title: unorm_3, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zy
- amp_short_vectors/Concurrency::graphics::unorm_3::zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::operator-=
- amp_short_vectors/Concurrency::graphics::unorm_3::xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::rgb
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yx
- amp_short_vectors/Concurrency::graphics::unorm_3::br
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xyz
- amp_short_vectors/Concurrency::graphics::unorm_3::b
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xyz
- amp_short_vectors/Concurrency::graphics::unorm_3
- amp_short_vectors/Concurrency::graphics::unorm_3::set_z
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zyx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xy
- amp_short_vectors/Concurrency::graphics::unorm_3::x
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::z
- amp_short_vectors/Concurrency::graphics::unorm_3::get_x
- amp_short_vectors/Concurrency::graphics::unorm_3::operator=
- amp_short_vectors/Concurrency::graphics::unorm_3::yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yx
- amp_short_vectors/Concurrency::graphics::unorm_3::gbr
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yxz
- amp_short_vectors/Concurrency::graphics::unorm_3::operator--
- amp_short_vectors/Concurrency::graphics::unorm_3::operator/=
- amp_short_vectors/Concurrency::graphics::unorm_3::brg
- amp_short_vectors/Concurrency::graphics::unorm_3::gb
- amp_short_vectors/Concurrency::graphics::unorm_3::zy
- amp_short_vectors/Concurrency::graphics::unorm_3::set_xzy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::rb
- amp_short_vectors/Concurrency::graphics::unorm_3::gr
- amp_short_vectors/Concurrency::graphics::unorm_3::zx
- amp_short_vectors/Concurrency::graphics::unorm_3::r
- amp_short_vectors/Concurrency::graphics::unorm_3::xyz
- amp_short_vectors/Concurrency::graphics::unorm_3::grb
- amp_short_vectors/Concurrency::graphics::unorm_3::bg
- amp_short_vectors/Concurrency::graphics::unorm_3::get_y
- amp_short_vectors/Concurrency::graphics::unorm_3::g
- amp_short_vectors/Concurrency::graphics::unorm_3::yz
- amp_short_vectors/Concurrency::graphics::unorm_3::yx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_xz
- amp_short_vectors/Concurrency::graphics::unorm_3::set_zxy
- amp_short_vectors/Concurrency::graphics::unorm_3::get_z
- amp_short_vectors/Concurrency::graphics::unorm_3::bgr
- amp_short_vectors/Concurrency::graphics::unorm_3::set_x
- amp_short_vectors/Concurrency::graphics::unorm_3::operator-
- amp_short_vectors/Concurrency::graphics::unorm_3::y
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::get_zx
- amp_short_vectors/Concurrency::graphics::unorm_3::yzx
- amp_short_vectors/Concurrency::graphics::unorm_3::operator++
- amp_short_vectors/Concurrency::graphics::unorm_3::set_yz
- amp_short_vectors/Concurrency::graphics::unorm_3::operator+=
- amp_short_vectors/Concurrency::graphics::unorm_3::xz
- amp_short_vectors/Concurrency::graphics::unorm_3::rg
- amp_short_vectors/Concurrency::graphics::unorm_3::xy
- amp_short_vectors/Concurrency::graphics::unorm_3::operator*=
- amp_short_vectors/Concurrency::graphics::unorm_3::set_y
- amp_short_vectors/Concurrency::graphics::unorm_3::get_yz
- amp_short_vectors/Concurrency::graphics::unorm_3::rbg
dev_langs:
- C++
ms.assetid: ea4e7a17-5256-464c-af28-8b01962564c0
caps.latest.revision: 10
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
ms.openlocfilehash: ce64e15c062f04df6c9f7671bd820ee188af0111
ms.lasthandoff: 02/24/2017

---
# <a name="unorm3-class"></a>unorm_3, classe
Représente un vecteur court de trois nombres normaux non signés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class unorm_3;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[unorm_3 constructeur](#ctor)|Surchargé. Par défaut constructeur initialise tous les éléments à 0.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|unorm_3::get_X (méthode)||  
|unorm_3::get_xy (méthode)||  
|unorm_3::get_xyz (méthode)||  
|unorm_3::get_xz (méthode)||  
|unorm_3::get_xzy (méthode)||  
|unorm_3::get_y (méthode)||  
|unorm_3::get_yx (méthode)||  
|unorm_3::get_yxz (méthode)||  
|unorm_3::get_yz (méthode)||  
|unorm_3::get_yzx (méthode)||  
|unorm_3::get_z (méthode)||  
|unorm_3::get_zx (méthode)||  
|unorm_3::get_zxy (méthode)||  
|unorm_3::get_zy (méthode)||  
|unorm_3::get_zyx (méthode)||  
|Unorm_3::ref_b (méthode)||  
|Unorm_3::ref_g (méthode)||  
|Unorm_3::ref_r (méthode)||  
|Unorm_3::ref_x (méthode)||  
|Unorm_3::ref_y (méthode)||  
|Unorm_3::ref_z (méthode)||  
|unorm_3::set_X (méthode)||  
|unorm_3::set_xy (méthode)||  
|unorm_3::set_xyz (méthode)||  
|unorm_3::set_xz (méthode)||  
|unorm_3::set_xzy (méthode)||  
|unorm_3::set_y (méthode)||  
|unorm_3::set_yx (méthode)||  
|unorm_3::set_yxz (méthode)||  
|unorm_3::set_yz (méthode)||  
|unorm_3::set_yzx (méthode)||  
|unorm_3::set_z (méthode)||  
|unorm_3::set_zx (méthode)||  
|unorm_3::set_zxy (méthode)||  
|unorm_3::set_zy (méthode)||  
|unorm_3::set_zyx (méthode)||  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|unorm_3::operator--(opérateur)||  
|unorm_3::operator * =, opérateur||  
|unorm_3::operator / =, opérateur||  
|unorm_3::operator ++ (opérateur)||  
|unorm_3::operator +=, opérateur||  
|unorm_3::operator =, opérateur||  
|unorm_3::operator-= (opérateur)||  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[taille (constante)](#unorm_3__size)||  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|Membre de données unorm_3::b||  
|Membre de données unorm_3::BG||  
|Membre de données unorm_3::BGR||  
|Membre de données unorm_3::br||  
|Membre de données unorm_3::brg||  
|Membre de données unorm_3::g||  
|Membre de données unorm_3::GB||  
|Membre de données unorm_3::GBR||  
|Membre de données unorm_3::GR||  
|Membre de données unorm_3::grb||  
|Membre de données unorm_3::r||  
|Membre de données unorm_3::RB||  
|Membre de données unorm_3::rbg||  
|Membre de données unorm_3::RG||  
|Membre de données unorm_3::RGB||  
|Membre de données unorm_3::x||  
|Membre de données unorm_3::XY||  
|Membre de données unorm_3::XYZ||  
|Membre de données unorm_3::XZ||  
|Membre de données unorm_3::xzy||  
|Membre de données unorm_3::y||  
|Membre de données unorm_3::YX||  
|Membre de données unorm_3::yxz||  
|Membre de données unorm_3::YZ||  
|Membre de données unorm_3::yzx||  
|Membre de données unorm_3::z||  
|Membre de données unorm_3::ZX||  
|Membre de données unorm_3::zxy||  
|Membre de données unorm_3::ZY||  
|Membre de données unorm_3::ZYX||  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `unorm_3`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_short_vectors.h  
  
 **Namespace :** Concurrency::graphics  
  
##  <a name="a-namectora-unorm3"></a><a name="ctor"></a>unorm_3 

 Par défaut constructeur initialise tous les éléments à 0.  
  
```  
unorm_3() restrict(amp,
    cpu);

 
unorm_3(
    unorm _V0,  
    unorm _V1,  
    unorm _V2) restrict(amp,
    cpu);

 
unorm_3(
    float _V0,  
    float _V1,  
    float _V2) restrict(amp,
    cpu);

 
unorm_3(
    unorm _V) restrict(amp,
    cpu);

 
explicit unorm_3(
    float _V) restrict(amp,
    cpu);

 
unorm_3(
    const unorm_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const uint_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const int_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const float_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const norm_3& _Other) restrict(amp,
    cpu);

 
explicit inline unorm_3(
    const double_3& _Other) restrict(amp,
    cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_V0`  
 La valeur pour initialiser l’élément 0.  
  
 `_V1`  
 La valeur pour initialiser l’élément 1.  
  
 `_V2`  
 La valeur pour initialiser l’élément 2.  
  
 `_V`  
 La valeur pour l’initialisation.  
  
 `_Other`  
 Objet utilisé pour initialiser.  
  
##  <a name="a-nameunorm3sizea-size"></a><a name="unorm_3__size"></a>taille 

```  
static const int size = 3;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::Graphics Namespace](concurrency-graphics-namespace.md)

