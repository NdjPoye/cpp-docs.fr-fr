---
title: Extent, classe (C++ AMP) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- extent
- AMP/extent
- AMP/Concurrency::extent::extent
- AMP/Concurrency::extent::contains
- AMP/Concurrency::extent::size
- AMP/Concurrency::extent::tile
- AMP/Concurrency::extent::rank Constant
dev_langs:
- C++
helpviewer_keywords:
- extent structure
ms.assetid: edb5de3d-3935-4dbb-8365-4cc6c4fb0269
caps.latest.revision: 19
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 28c90118eeb83df75f19b49f47ac884bff111b8f
ms.lasthandoff: 03/17/2017

---
# <a name="extent-class-c-amp"></a>extent, classe (C++ AMP)
Représente un vecteur de *N* valeurs entières qui spécifient les limites d’un *N*-espace tridimensionnel qui a une origine de 0. Les valeurs du vecteur sont triés du plus significatif au moins significatif.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
template <int _Rank>  
class extent;  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rank`  
 Le classement de la `extent` objet.  

 ## <a name="requirements"></a>Spécifications  
 **En-tête :** amp.h  
  
 **Espace de noms :** Concurrency  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[Extent, constructeur](#ctor)|Initialise une nouvelle instance de la classe `extent`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[contient](#contains)|Vérifie que le texte spécifié `extent` objet a le rang spécifié.|  
|[size](#size)|Retourne la taille totale linéaire de l’étendue (en unités d’éléments).|  
|[Mosaïque](#tile)|Génère un `tiled_extent` objet avec les extensions de vignette donné par spécifié de dimensions.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[operator-](#operator_min)|Retourne un nouveau `extent` objet qui est créé en soustrayant la `index` éléments correspondant `extent` éléments.|  
|[operator--](#operator_min_min)|Décrémente chaque élément de la `extent` objet.|  
|[operator%=](#operator_mod_eq)|Calcule le modulo (reste) de chaque élément dans le `extent` de l’objet lorsque cet élément est divisé par un nombre.|  
|[operator*=](#operator_star_eq)|Multiplie chaque élément de la `extent` objet par un nombre.|  
|[operator/=](#operator_min_eq)|Divise chaque élément de la `extent` objet par un nombre.|  
|[Extent::operator\[\]](#operator_at)|Retourne l’élément situé à l’index spécifié.|  
|[operator+](#operator_add)|Retourne un nouveau `extent` objet qui est créé en ajoutant le correspondant `index` et `extent` éléments.|  
|[operator++](#operator_add_add)|Incrémente chaque élément de la `extent` objet.|  
|[operator+=](#operator_add_eq)|Ajoute le nombre spécifié pour chaque élément de la `extent` objet.|  
|[operator=](#operator_eq)|Copie le contenu d’un autre `extent` objet dans celui-ci.|  
|[operator-=](#operator_min_eq)|Soustrait le nombre spécifié de chaque élément de la `extent` objet.|  

  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[RANK (constante)](#rank)|Obtient le classement de la `extent` objet.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `extent`  


## <a name="contains"></a>contient 

Indique si le texte spécifié [index](index-class.md) valeur est contenue dans l’objet « étendue ».  
  
### <a name="syntax"></a>Syntaxe  
  
```  
bool contains(const index<rank>& _Index) const restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 Le `index` valeur à tester.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si spécifié `index` valeur est contenue dans le `extent` objet ; sinon, `false`.  
  
##  <a name="ctor"></a>étendue 

Initialise une nouvelle instance de la classe « étendue ».  
  
### <a name="syntax"></a>Syntaxe  
  
```  
extent() restrict(amp,cpu);    
extent(const extent<_Rank>& _Other) restrict(amp,cpu);    
explicit extent(int _I) restrict(amp,cpu);    
extent(int _I0,  int _I1) restrict(amp,cpu);    
extent(int _I0,  int _I1, int _I2) restrict(amp,cpu);    
explicit extent(const int _Array[_Rank])restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Array`  
 Un tableau de `_Rank` entiers qui est utilisé pour créer le nouveau `extent` objet.  
  
 `_I`  
 La longueur de l’étendue.  
  
 `_I0`  
 La longueur de la dimension la plus importante.  
  
 `_I1`  
 La longueur de la dimension suivant-à-plus significatif.  
  
 `_I2`  
 La longueur de la dimension moins significative.  
  
 `_Other`  
 Un `extent` objet sur lequel la nouvelle `extent` objet est basé.  
  
## <a name="remarks"></a>Notes  
 Le constructeur sans paramètre un `extent` objet ayant un rang de trois.  
  
 Si un tableau est utilisé pour construire un `extent` de l’objet, la longueur du tableau doit correspondre au rang de la `extent` objet.  
  
##  <a name="operator_mod_eq"></a>opérateur % = 

Calcule le modulo (reste) de chaque élément de l’extension' ' lorsque cet élément est divisé par un nombre.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
extent<_Rank>& operator%=(int _Rhs) restrict(cpu, direct3d);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rhs`  
 Pour trouver le modulo de nombre.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `extent`.  
  
##  <a name="operator_star_eq"></a>opérateur * = 

Multiplie chaque élément dans l’objet 'extension' par le nombre spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
extent<_Rank>& operator*=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rhs`  
 Le nombre à multiplier.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `extent`.  
  
## <a name="operator_add"></a>+ (opérateur) 

Retourne un nouveau `extent` objet créé en ajoutant le correspondant `index` et `extent` éléments.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
extent<_Rank> operator+(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rhs`  
 Le `index` objet qui contient les éléments à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
 Nouvel objet `extent`.  
  
##  <a name="operator_add_add"></a>operator ++ 

Incrémente chaque élément de l’objet « étendue ».  
  
### <a name="syntax"></a>Syntaxe  
  
```  
extent<_Rank>& operator++() restrict(amp,cpu);    
extent<_Rank> operator++(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pour l’opérateur de la `extent` objet (`*this`). Pour l’opérateur de suffixe, un nouveau `extent` objet.  
  
##  <a name="operator_add_eq"></a>opérateur += 

Ajoute le nombre spécifié pour chaque élément de l’objet « étendue ».  
  
### <a name="syntax"></a>Syntaxe  
  
```  
extent<_Rank>& operator+=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator+=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rhs`  
 Le nombre, l’index ou étendue à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `extent` obtenu.  
  
##  <a name="operator_min"></a>-(opérateur) 

Crée un objet `extent` objet en soustrayant chaque élément spécifié `index` objet à partir de l’élément correspondant dans cette `extent` objet.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
extent<_Rank> operator-(const index<_Rank>& _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rhs`  
 Le `index` objet qui contient les éléments à soustraire.  
  
### <a name="return-value"></a>Valeur de retour  
 Nouvel objet `extent`.  
  
##  <a name="operator_min_min"></a>opérateur-- 

Décrémente chaque élément dans l’objet « étendue ».  
  
### <a name="syntax"></a>Syntaxe  
  
```  
extent<_Rank>& operator--() restrict(amp,cpu);    
extent<_Rank> operator--(int)restrict(amp,cpu);  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pour l’opérateur de la `extent` objet (`*this`). Pour l’opérateur de suffixe, un nouveau `extent` objet.  
  
##  <a name="operator_div_eq"></a>/ = (opérateur) 

Divise chaque élément dans l’objet 'extension' par le nombre spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
extent<_Rank>& operator/=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rhs`  
 Le nombre à diviser par.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `extent`.  
  
##  <a name="operator_min_eq"></a>opérateur = 

Soustrait le nombre spécifié de chaque élément de l’objet « étendue ».  
  
### <a name="syntax"></a>Syntaxe  
  
```  
extent<_Rank>& operator-=(const extent<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(const index<_Rank>& _Rhs) restrict(amp,cpu);    
extent<_Rank>& operator-=(int _Rhs) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rhs`  
 Nombre à soustraire.  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `extent` obtenu.  
  
##  <a name="operator_eq"></a>opérateur = 

Copie le contenu d’un autre objet de « étendue » dans celle-ci.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
extent<_Rank>& operator=(const extent<_Rank>& _Other) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Other`  
 Le `extent` objet d’origine.  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à ce `extent` objet.  
  
##  <a name="operator_at"></a>Extent::operator\[\] 
Retourne l’élément situé à l’index spécifié.  
  
### <a name="syntax"></a>Syntaxe  
  
```  
int operator[](unsigned int _Index) const restrict(amp,cpu);    
int& operator[](unsigned int _Index) restrict(amp,cpu);  
```  
  
### <a name="parameters"></a>Paramètres  
 `_Index`  
 Nombre entier compris entre 0 et le rang moins 1.  
  
### <a name="return-value"></a>Valeur de retour  
 L’élément qui est à l’index spécifié.  
  
##  <a name="rank_constant"></a>rang 

Stocke le rang de l’objet « étendue ».  
  
### <a name="syntax"></a>Syntaxe  
  
```  
static const int rank = _Rank;  
```  
  
##  <a name="size"></a>taille 

Retourne la taille totale linéaire de la `extent` objet (en unités d’éléments).  
  
### <a name="syntax"></a>Syntaxe  

```  
unsigned int size() const restrict(amp,cpu);  
```  
  
## <a name="tile"></a>Mosaïque 

Produit un objet tiled_extent avec les dimensions de la mosaïque.

```
template <int _Dim0>
tiled_extent<_Dim0> tile() const ;

template <int _Dim0, int _Dim1>
tiled_extent<_Dim0, _Dim1> tile() const ;

template <int _Dim0, int _Dim1, int _Dim2>
tiled_extent<_Dim0, _Dim1, _Dim2> tile() const ;
```  
### <a name="parameters"></a>Paramètres
`_Dim0`Le composant plus significatif de l’étendue en mosaïque.
`_Dim1`Le composant suivant-à-plus significatif de l’étendue en mosaïque.
`_Dim2`Le composant moins important de l’étendue en mosaïque.


  
## <a name="see-also"></a>Voir aussi  
 [Concurrency, espace de noms (C++ AMP)](concurrency-namespace-cpp-amp.md)

