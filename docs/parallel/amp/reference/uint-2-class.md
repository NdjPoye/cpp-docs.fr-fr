---
title: uint_2, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_short_vectors/Concurrency::graphics::uint_2::set_xy
- amp_short_vectors/Concurrency::graphics::uint_2::y
- amp_short_vectors/Concurrency::graphics::uint_2::gr
- amp_short_vectors/Concurrency::graphics::uint_2::operator-
- amp_short_vectors/Concurrency::graphics::uint_2::get_x
- amp_short_vectors/Concurrency::graphics::uint_2::operator-=
- amp_short_vectors/Concurrency::graphics::uint_2::r
- amp_short_vectors/Concurrency::graphics::uint_2::yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator--
- amp_short_vectors/Concurrency::graphics::uint_2::set_yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator=
- amp_short_vectors/Concurrency::graphics::uint_2::set_x
- amp_short_vectors/Concurrency::graphics::uint_2::operator+=
- amp_short_vectors/Concurrency::graphics::uint_2::get_y
- amp_short_vectors/Concurrency::graphics::uint_2::xy
- amp_short_vectors/Concurrency::graphics::uint_2::x
- amp_short_vectors/Concurrency::graphics::uint_2::get_xy
- amp_short_vectors/Concurrency::graphics::uint_2::set_y
- amp_short_vectors/Concurrency::graphics::uint_2
- amp_short_vectors/Concurrency::graphics::uint_2::operator*=
- amp_short_vectors/Concurrency::graphics::uint_2::get_yx
- amp_short_vectors/Concurrency::graphics::uint_2::operator/=
- amp_short_vectors/Concurrency::graphics::uint_2::g
- amp_short_vectors/Concurrency::graphics::uint_2::operator++
- amp_short_vectors/Concurrency::graphics::uint_2::rg
dev_langs:
- C++
ms.assetid: 9fcc9129-72b1-4da7-9012-4d3be15f1c52
caps.latest.revision: 11
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 1116be21d4f65b67ab967b7acedf4859df54a6e7
ms.lasthandoff: 02/24/2017

---
# <a name="uint2-class"></a>uint_2, classe
Représente un vecteur court des deux entiers non signés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class uint_2;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`value_type`||  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[uint_2 constructeur](#ctor)|Surchargé. Par défaut constructeur initialise tous les éléments à 0.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|uint_2::get_X (méthode)||  
|uint_2::get_xy (méthode)||  
|uint_2::get_y (méthode)||  
|uint_2::get_yx (méthode)||  
|uint_2::ref_g_Method||  
|uint_2::ref_r_Method||  
|uint_2::ref_x_Method||  
|uint_2::ref_y_Method||  
|uint_2::set_X (méthode)||  
|uint_2::set_xy (méthode)||  
|uint_2::set_y (méthode)||  
|uint_2::set_yx (méthode)||  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|uint_2::operator--(opérateur)||  
|uint_2::operator % =, opérateur||  
|uint_2::operator < =, opérateur||  
|uint_2::operator * =, opérateur||  
|uint_2::operator / =, opérateur||  
|uint_2::operator ^ =, opérateur||  
|uint_2::operator | =, opérateur||  
|uint_2::operator ~ (opérateur)||  
|uint_2::operator ++ (opérateur)||  
|uint_2::operator +=, opérateur||  
|uint_2::operator\<=, opérateur||  
|uint_2::operator =, opérateur||  
|uint_2::operator-= (opérateur)||  
|uint_2::operator >> =, opérateur||  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[taille (constante)](#uint_2__size)||  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|Membre de données uint_2::g||  
|Membre de données uint_2::GR||  
|Membre de données uint_2::r||  
|Membre de données uint_2::RG||  
|Membre de données uint_2::x||  
|Membre de données uint_2::XY||  
|Membre de données uint_2::y||  
|Membre de données uint_2::YX||  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `uint_2`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_short_vectors.h  
  
 **Namespace :** Concurrency::graphics  
  
##  <a name="a-namectora-uint2"></a><a name="ctor"></a>uint_2 

 Par défaut constructeur initialise tous les éléments à 0.  
  
```  
uint_2() restrict(amp,
    cpu);

 
uint_2(
    unsigned int _V0,  
    unsigned int _V1) restrict(amp,
    cpu);

 
uint_2(
    unsigned int _V) restrict(amp,
    cpu);

 
uint_2(
    const uint_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const int_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const float_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const unorm_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
    const norm_2& _Other) restrict(amp,
    cpu);

 
explicit inline uint_2(
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
  
##  <a name="a-nameuint2sizea-size"></a><a name="uint_2__size"></a>taille 

```  
static const int size = 2;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::Graphics Namespace](concurrency-graphics-namespace.md)

