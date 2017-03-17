---
title: "Opérateurs d’espace de noms d’accès concurrentiel (AMP) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: 
dev_langs:
- C++
ms.assetid: 77f1ae17-1eb2-480d-8fe5-66d4c24bb91e
caps.latest.revision: 9
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 22ba62ab8b3b4f9d14953dbab3edd8228ea85193
ms.openlocfilehash: 676f3e836082dc3286a45f8d59db83c969964058
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-operators-amp"></a>Opérateurs d’espace de noms d’accès concurrentiel (AMP)
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator%](#operator_mod)|[operator*](#operator_star)|  
|[operator+](#operator_add)|[operator-](#operator-)|[operator/](#operator_div)|  
|[operator==](#operator_eq_eq)|  
  
##  <a name="operator_eq_eq"></a>  operator==   
 Détermine si les arguments spécifiés sont égaux.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
bool operator== (
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rank`  
 Le rang du tuple arguments.  
  
 `_Lhs`  
 Une des tuples à comparer.  
  
 `_Rhs`  
 Une des tuples à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si les tuples sont identiques ; dans le cas contraire, `false`.  
  
##  <a name="operator_neq"></a>  operator!=   
 Détermine si les arguments spécifiés ne sont pas égales.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
bool operator!= (
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rank`  
 Le rang du tuple arguments.  
  
 `_Lhs`  
 Une des tuples à comparer.  
  
 `_Rhs`  
 Une des tuples à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si les tuples ne sont pas égales ; dans le cas contraire, `false`.  
  
##  <a name="operator_add"></a>  operator+   

 Calcule la somme de component-wise des arguments spécifiés.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
class _Tuple_type> _Tuple_type<_Rank>   operator+(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rank`  
 Le rang du tuple arguments.  
  
 `_Lhs`  
 Un des arguments à ajouter.  
  
 `_Rhs`  
 Un des arguments à ajouter.  
  
### <a name="return-value"></a>Valeur de retour  
 Component-wise somme des arguments spécifiés.  
  
##  <a name="operator-"></a>  operator-   

 Calcule la différence component-wise entre les arguments spécifiés.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator-(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rank`  
 Le rang du tuple arguments.  
  
 `_Lhs`  
 L’argument à soustraire.  
  
 `_Rhs`  
 L’argument à soustraire.  
  
### <a name="return-value"></a>Valeur de retour  
 La différence component-wise entre les arguments spécifiés.  
  
##  <a name="operator_star"></a>  operator*   

 Calcule le produit component-wise des arguments spécifiés.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator*(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator*(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp, cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rank`  
 Le rang du tuple arguments.  
  
 `_Lhs`  
 Une des tuples à multiplier.  
  
 `_Rhs`  
 Une des tuples à multiplier.  
  
### <a name="return-value"></a>Valeur de retour  
 Le produit component-wise des arguments spécifiés.  
  

##  <a name="operator_div"></a>  operator/   
 Calcule le quotient component-wise des arguments spécifiés.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator/(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator/(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rank`  
 Le rang du tuple arguments.  
  
 `_Lhs`  
 Le tuple à diviser.  
  
 `_Rhs`  
 Le tuple par laquelle diviser.  
  
### <a name="return-value"></a>Valeur de retour  
 Quotient component-wise des arguments spécifiés.  
  
##  <a name="operator_mod"></a>  operator%   

 Calcule le modulo du premier argument spécifié par le deuxième argument spécifié.  
  
```  
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator%(
    const _Tuple_type<_Rank>& _Lhs,  
    typename _Tuple_type<_Rank>::value_type _Rhs) restrict(amp,cpu);

 
template <
    int _Rank,  
    template <int> class _Tuple_type  
>  
_Tuple_type<_Rank>   operator%(
    typename _Tuple_type<_Rank>::value_type _Lhs,  
    const _Tuple_type<_Rank>& _Rhs) restrict(amp,cpu);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Rank`  
 Le rang du tuple arguments.  
  
 `_Lhs`  
 Le tuple à partir de laquelle le modulo est calculée.  
  
 `_Rhs`  
 Le tuple à modulo par.  
  
### <a name="return-value"></a>Valeur de retour  
 Le résultat premier argument spécifié du modulo de la deuxième argument spécifié.  
  
## <a name="see-also"></a>Voir aussi  
 [Accès concurrentiel Namespace](concurrency-namespace-cpp-amp.md)

