---
title: writeonly_texture_view, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- amp_graphics/Concurrency::graphics::writeonly_texture_view
dev_langs:
- C++
ms.assetid: 8d117ad3-0a1c-41ae-b29c-7c95fdd4d04d
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
ms.openlocfilehash: a40aa0cb433b6daee19af7fdea7c6421b61c1b4c
ms.lasthandoff: 02/24/2017

---
# <a name="writeonlytextureview-class"></a>writeonly_texture_view, classe
Fournit l’accès writeonly une texture.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view;  
 
template <
    typename value_type,  
    int _Rank  
>  
class writeonly_texture_view<value_type, _Rank> : public details::_Texture_base<value_type, _Rank>;  
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
|`scalar_type`||  
|`value_type`|Le type des éléments de la texture.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[writeonly_texture_view, constructeur](#ctor)|Initialise une nouvelle instance de la classe `writeonly_texture_view`.|  
|[~ writeonly_texture_view, destructeur](#ctor)|Détruit le `writeonly_texture_view` objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Set, méthode](#set)|Définit la valeur de l’élément à l’index spécifié.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[opérateur =, opérateur](#operator_eq)|Copie le texte spécifié `writeonly_texture_view` objet à celui-ci.|  
  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[RANK (constante)](#rank)|Obtient le classement de la `writeonly_texture_view` objet.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `_Texture_base`  
  
 `writeonly_texture_view`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp_graphics.h  
  
 **Namespace :** Concurrency::graphics  
  
##  <a name="a-namedtora-writeonlytextureview"></a><a name="dtor"></a>~ writeonly_texture_view 

 Détruit le `writeonly_texture_view` objet.  
  
```  
~writeonly_texture_view() restrict(amp,cpu);
```  
  
##  <a name="a-nameoperatoreqa-operator"></a><a name="operator_eq"></a>opérateur = 

 Copie le texte spécifié `writeonly_texture_view` objet à celui-ci.  
  
```  
writeonly_texture_view<value_type, _Rank>& operator= (
    const writeonly_texture_view<value_type, _Rank>& _Other) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 `writeonly_texture_view`objet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `writeonly_texture_view` objet.  
  
##  <a name="a-nameranka-rank"></a><a name="rank"></a>rang 

 Obtient le classement de la `writeonly_texture_view` objet.  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="a-nameseta-set"></a><a name="set"></a>ensemble 

 Définit la valeur de l’élément à l’index spécifié.  
  
```  
void set(
    const index<_Rank>& _Index,  
    const value_type& value) const restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 L’index de l’élément.  
  
 `value`  
 Nouvelle valeur de l’élément.  
  
##  <a name="a-namectora-writeonlytextureview"></a><a name="ctor"></a>writeonly_texture_view 

 Initialise une nouvelle instance de la classe `writeonly_texture_view`.  
  
```  
writeonly_texture_view(
    texture<value_type, 
    _Rank>& _Src) restrict(amp);

 
writeonly_texture_view(
    const writeonly_texture_view<value_type,  
    _Rank>& _Src) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rank`  
 Le classement de la texture.  
  
 `value_type`  
 Le type des éléments de la texture.  
  
 `_Src`  
 La texture qui est utilisée pour créer le `writeonly_texture_view`.  
  
## <a name="see-also"></a>Voir aussi  
 [Concurrency::Graphics Namespace](concurrency-graphics-namespace.md)

