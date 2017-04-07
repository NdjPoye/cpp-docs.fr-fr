---
title: index, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- AMP/index
- AMP/Concurrency::index::index
- AMP/Concurrency::index::rank
dev_langs:
- C++
helpviewer_keywords:
- index structure
ms.assetid: cbe79b08-0ba7-474c-9828-f1a71da39eb3
caps.latest.revision: 20
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
ms.openlocfilehash: 52c19da3cb8de10c3963ca3b795cac1babb3dc7a
ms.lasthandoff: 03/17/2017

---
# <a name="index-class"></a>index, classe
Définit un *N*-dimensionnel index pographics-cpp-amp.md.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <int _Rank>  
class index;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `_Rank`  
 Le classement, ou le nombre de dimensions.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[index, constructeur](#ctor)|Initialise une nouvelle instance de la classe `index`.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[operator--](#operator--)|Décrémente chaque élément de la `index` objet.|  
|[operator(MOD) =](#operator_mod_eq)|Calcule le modulo (reste) de chaque élément dans le `index` de l’objet lorsque cet élément est divisé par un nombre.|  
|[operator*=](#operator_star_eq)|Multiplie chaque élément de la `index` objet par un nombre.|  
|[operator/=](#operator_div_eq)|Divise chaque élément de la `index` objet par un nombre.|  
|[index::operator\[\]](#operator_at)|Retourne l’élément situé à l’index spécifié.|  
|[operator++](#operator_add_add)|Incrémente chaque élément de la `index` objet.|  
|[operator+=](#operator_add_eq)|Ajoute le nombre spécifié pour chaque élément de la `index` objet.|  
|[operator=](#operator_eq)|Copie le contenu de l’objet `index` objet dans celui-ci.|  
|[operator-=](#operator_-_eq)|Soustrait le nombre spécifié de chaque élément de la `index` objet.|  

  
### <a name="public-constants"></a>Constantes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[RANK (constante)](#rank)|Stocke le rang de la `index` objet.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `index`  
  
## <a name="remarks"></a>Remarques  
 Le `index` structure représente un vecteur de coordonnées *N* entiers qui spécifie une position unique dans une *N*-espace&3;D. Les valeurs du vecteur sont triés du plus significatif au moins significatif. Vous pouvez récupérer les valeurs des composants à l’aide de [opérateur =](#operator_eq).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** amp.h  
  
 **Espace de noms :** Concurrency  


## <a name="index_ctor"></a>index, constructeur
Initialise une nouvelle instance de la classe d’index.

```  
index() restrict(amp,cpu);

index(
   const index<_Rank>& _Other
) restrict(amp,cpu);

explicit index(
   int _I
) restrict(amp,cpu);

index(
   int _I0,
   int _I1
) restrict(amp,cpu);

index(
   int _I0,
   int _I1,
   int _I2
) restrict(amp,cpu);

explicit index(
   const int _Array[_Rank]
) restrict(amp,cpu);
``` 

### <a name="parameters"></a>Paramètres

_ARRAY  
Un tableau unidimensionnel avec les valeurs de classement.  
_I  
Position d’index dans un index de dimension.  
_I0  
La longueur de la dimension la plus importante.  
_I1  
La longueur de la dimension suivant-à-plus significatif.  
_I2  
La longueur de la dimension moins significative.  
_Other  
Objet index sur lequel est basé le nouvel objet index.  

## <a name="operator--"></a>opérateur--
Décrémente chaque élément de l’objet index.  
```  
index<_Rank>& operator--() restrict(amp,cpu);  

index operator--(
   int
) restrict(amp,cpu);
```  
### <a name="return-values"></a>Valeurs de retour
Pour l’opérateur de l’objet index (* cela). Pour l’opérateur de suffixe, un nouvel objet index.

## <a name="operator_mod_eq"></a>operator(MOD) =   
Calcule le modulo (reste) de chaque élément dans l’objet index lorsque cet élément est divisé par le nombre spécifié.

```  
index<_Rank>& operator%=(
   int _Rhs
) restrict(cpu, amp);
```  
### <a name="parameters"></a>Paramètres
_Rhs le nombre à diviser par pour trouver le modulo.
Valeur de retour l’objet index.

## <a name="operator_star_eq"></a>opérateur * =   
Multiplie chaque élément dans l’objet index par le nombre spécifié.
```
index<_Rank>& operator*=(
   int _Rhs
) restrict(amp,cpu);
```

### <a name="parameters"></a>Paramètres
_Rhs le nombre à multiplier.

## <a name="operator_div_eq"></a>/ = (opérateur) 
Divise chaque élément dans l’objet index par le nombre spécifié.

```
index<_Rank>& operator/=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Paramètres
_Rhs le nombre à diviser par.

## <a name="operator_at"></a>  operator\[\]  
Retourne le composant de l’index à l’emplacement spécifié.

```
int operator[] (
   unsigned _Index
) const restrict(amp,cpu);

int& operator[] (
   unsigned _Index
) restrict(amp,cpu);
```

### <a name="parameters"></a>Paramètres
_Index un entier compris entre 0 et le rang moins 1.

### <a name="return-value"></a>Valeur de retour
L’élément qui est à l’index spécifié.

### <a name="remarks"></a>Notes
L’exemple suivant affiche les valeurs de composant de l’index.
```  
// Prints 1 2 3.
concurrency::index<3> idx(1, 2, 3);
std::cout << idx[0] << "\n";
std::cout << idx[1] << "\n";
std::cout << idx[2] << "\n";
```

## <a name="operator_add_add"></a>operator ++   
Incrémente chaque élément de l’objet index.
```  
index<_Rank>& operator++() restrict(amp,cpu);

index<_Rank> operator++(
   int
) restrict(amp,cpu);
```  
### <a name="return-value"></a>Valeur de retour
Pour l’opérateur de l’objet index (* cela). Pour l’opérateur de suffixe, un nouvel objet index.

## <a name="operator_add_eq"></a>opérateur +=   
Ajoute le nombre spécifié pour chaque élément de l’objet index.
```  
index<_Rank>& operator+=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator+=(
   int _Rhs
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Paramètres
_Rhs le numéro à ajouter.

### <a name="return-value"></a>Valeur de retour
L’objet index.

## <a name="operator_eq"></a>  operator=   
Copie le contenu de l’objet de l’index spécifié dans celle-ci.
```  
index<_Rank>& operator=(
   const index<_Rank>& _Other
) restrict(amp,cpu);
``` 
### <a name="parameters"></a>Paramètres
L’objet index à copier à partir de _Other.

### <a name="return-value"></a>Valeur de retour
Une référence à cet objet index.

## <a name="operator_-_eq"></a>opérateur =
Soustrait le nombre spécifié de chaque élément de l’objet index.
```  
index<_Rank>& operator-=(
   const index<_Rank>& _Rhs
) restrict(amp,cpu);

index<_Rank>& operator-=(
   int _Rhs
) restrict(amp,cpu);
```  
### <a name="parameters"></a>Paramètres
_Rhs le nombre à soustraire.

### <a name="return-value"></a>Valeur de retour
L’objet index.   

## <a name="rank"></a>Rang  
  Obtient le classement de l’objet index.
```
static const int rank = _Rank;
``` 
## <a name="see-also"></a>Voir aussi  
 [Concurrency, espace de noms (C++ AMP)](concurrency-namespace-cpp-amp.md)

