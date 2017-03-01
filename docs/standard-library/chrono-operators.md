---
title: "&lt;chrono&gt;, opérateurs | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5a19267-4684-40c1-b7a9-cc1012b058f3
caps.latest.revision: 8
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: c2ea4241ef1db4989caf8cdc6a16044d9c9381f6
ms.lasthandoff: 02/24/2017

---
# <a name="ltchronogt-operators"></a>&lt;chrono&gt;, opérateurs
||||  
|-|-|-|  
|[opérateur modulo](#operator_modulo)|[operator!=](#operator_neq)|[operator&gt;](#operator_gt_)|  
|[operator&gt;=](#operator_gt__eq)|[operator&lt;](#operator_lt_)|[operator&lt;=](#operator_lt__eq)|  
|[operator*](#operator_star)|[operator+](#operator_add)|[operator-](#operator-)|  
|[operator/](#operator_)|[operator==](#operator_eq_eq)|  
  
##  <a name="a-nameoperator-a--operator-"></a><a name="operator-"></a>  operator-  
 Opérateur de soustraction ou de négation des objets [duration](../standard-library/duration-class.md) et [time_point](../standard-library/time-point-class.md).  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type 
   operator-(
       const duration<Rep1, Period1>& Left, 
       cconst duration<Rep2, Period2>& Right);
 
template <class Clock, class Duration1, class Rep2, class Period2>  
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type  
   operator-(
       const time_point<Clock, Duration1>& Time, 
       const duration<Rep2, Period2>& Dur);

 
template <class Clock, class Duration1, class Duration2>  
constexpr typename common_type<Duration1, Duration2>::type 
   operator-(
       const time_point<Clock, Duration1>& Left, 
       const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet `duration` ou `time_point` gauche.  
  
 `Right`  
 Objet `duration` ou `time_point` droit.  
  
 `Time`  
 Objet `time_point`.  
  
 `Dur`  
 Objet `duration`.  
  
### <a name="return-value"></a>Valeur de retour  
 La première fonction retourne un objet `duration` dont la longueur de l'intervalle est la différence entre les intervalles de temps des deux arguments.  
  
 La deuxième fonction retourne un objet `time_point` qui représente un point dans le temps qui est déplacé, selon la négation de l'intervalle de temps représenté par `Dur`, à partir du point dans le temps spécifié par `Time`.  
  
 La troisième fonction retourne un objet `duration` qui représente l'intervalle de temps entre `Left` et `Right`.  
  
##  <a name="a-nameoperatorneqa--operator"></a><a name="operator_neq"></a>  operator!=  
 Opérateur d’inégalité des objets [duration](../standard-library/duration-class.md) ou [time_point](../standard-library/time-point-class.md).  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator!=(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);

 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator!=(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet `duration` ou `time_point` gauche.  
  
 `Right`  
 Objet `duration` ou `time_point` droit.  
  
### <a name="return-value"></a>Valeur de retour  
 Chaque fonction retourne `!(Left == Right)`.  
  
##  <a name="a-nameoperatorstara--operator"></a><a name="operator_star"></a>  operator*  
 Opérateur de multiplication des objets [duration](../standard-library/chrono-operators.md#operator_star).  
  
```  
template <class Rep1, class Period1, class Rep2>  
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1> 
   operator*(
      const duration<Rep1, Period1>& Dur, 
      const Rep2& Mult);

 
template <class Rep1, class Rep2, class Period2>  
constexpr duration<typename common_type<Rep1, Rep2>::type, Period2> 
   operator*(
       const Rep1& Mult,
       const duration<Rep2, 
       Period2>& Dur);
```  
  
### <a name="parameters"></a>Paramètres  
 `Dur`  
 Objet `duration`.  
  
 `Mult`  
 Valeur intégrale.  
  
### <a name="return-value"></a>Valeur de retour  
 Chaque fonction retourne un objet `duration` dont la longueur de l'intervalle est égale à `Mult` multiplié par la longueur de `Dur`.  
  
 À moins que `is_convertible<Rep2, common_type<Rep1, Rep2>>`*ne contienne la valeur true*, la première fonction ne participe pas à la résolution de surcharge. Pour plus d’informations, consultez [<type_traits>](../standard-library/type-traits.md).  
  
 À moins que `is_convertible<Rep1, common_type<Rep1, Rep2>>`*ne contienne la valeur true*, la deuxième fonction ne participe pas à la résolution de surcharge. Pour plus d’informations, consultez [<type_traits>](../standard-library/type-traits.md).  
  
##  <a name="a-nameoperatora--operator"></a><a name="operator_"></a>  operator/  
 Opérateur de division des objets [duration](../standard-library/chrono-operators.md#operator_star).  
  
```  
template <class Rep1, class Period1, class Rep2>  
constexpr duration<typename common_type<Rep1, Rep2>::type, Period1> 
   operator/(
     const duration<Rep1, Period1>& Dur,  
     const Rep2& Div);

 
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr typename common_type<Rep1, Rep2>::type 
   operator/(
     const duration<Rep1, Period1>& Left,  
     const duration<Rep2, Period2>& Right);
```  
  
### <a name="parameters"></a>Paramètres  
 `Dur`  
 Objet `duration`.  
  
 `Div`  
 Valeur intégrale.  
  
 `Left`  
 Objet gauche `duration`.  
  
 `Right`  
 Objet droit `duration`.  
  
### <a name="return-value"></a>Valeur de retour  
 Le premier opérateur retourne un objet de durée dont l'intervalle de longueur est la longueur de `Dur` divisée par la valeur `Div`.  
  
 Le deuxième opérateur retourne le rapport des longueurs d'intervalle de `Left` et de `Right`.  
  
 À moins que `is_convertible<Rep2, common_type<Rep1, Rep2>>`*ne contienne la valeur true* et que `Rep2` ne soit pas une instanciation de `duration`, le premier opérateur ne participe pas à la résolution de surcharge. Pour plus d’informations, consultez [<type_traits>](../standard-library/type-traits.md).  
  
##  <a name="a-nameoperatoradda--operator"></a><a name="operator_add"></a>  operator+  
 Ajoute des objets [duration](../standard-library/duration-class.md) et [time_point](../standard-library/time-point-class.md).  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr typename common_type<duration<Rep1, Period1>, duration<Rep2, Period2>>::type 
   operator+(
      const duration<Rep1, Period1>& Left,  
      const duration<Rep2, Period2>& Right);

 
template <class Clock, class Duration1, class Rep2, class Period2>  
constexpr time_point<Clock, typename common_type<Duration1, duration<Rep2, Period2>>::type>
   operator+(
      const time_point<Clock, Duration1>& Time,  
      const duration<Rep2, Period2>& Dur);

 
template <class Rep1, class Period1, class Clock, class Duration2>  
time_point<Clock, constexpr typename common_type<duration<Rep1, Period1>, Duration2>::type>
   operator+(
      const duration<Rep1, Period1>& Dur,  
      const time_point<Clock, Duration2>& Time);
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet `duration` ou `time_point` gauche.  
  
 `Right`  
 Objet `duration` ou `time_point` droit.  
  
 `Time`  
 Objet `time_point`.  
  
 `Dur`  
 Objet `duration`.  
  
### <a name="return-value"></a>Valeur de retour  
 La première fonction retourne un objet `duration` dont l'intervalle de temps est égal à la somme des intervalles de `Left` et de `Right`.  
  
 Les deuxième et troisième fonctions retournent un objet `time_point` qui représente un point dans le temps qui est déplacé, selon l'intervalle `Dur`, à partir du point dans le temps `Time`.  
  
##  <a name="a-nameoperatorlta--operatorlt"></a><a name="operator_lt_"></a>  operator&lt;  
 Détermine si un objet [duration](../standard-library/duration-class.md) ou [time_point](../standard-library/time-point-class.md) est inférieur à un autre objet `duration` ou `time_point`.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator<(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);

 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator<(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet `duration` ou `time_point` gauche.  
  
 `Right`  
 Objet `duration` ou `time_point` droit.  
  
### <a name="return-value"></a>Valeur de retour  
 La première fonction retourne `true` si la longueur de l'intervalle de `Left` est inférieure à la longueur de l'intervalle de `Right`. Sinon, la fonction retourne `false`.  
  
 La deuxième fonction retourne `true` si `Left` précède `Right`. Sinon, la fonction retourne `false`.  
  
##  <a name="a-nameoperatorlteqa--operatorlt"></a><a name="operator_lt__eq"></a>  operator&lt;=  
 Détermine si un objet [duration](../standard-library/duration-class.md) ou [time_point](../standard-library/time-point-class.md) est inférieur ou égal à un autre objet `duration` ou `time_point`.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator<=(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);
 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator<=(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet `duration` ou `time_point` gauche.  
  
 `Right`  
 Objet `duration` ou `time_point` droit.  
  
### <a name="return-value"></a>Valeur de retour  
 Chaque fonction retourne `!(Right < Left)`.  
  
##  <a name="a-nameoperatoreqeqa--operator"></a><a name="operator_eq_eq"></a>  operator==  
 Détermine si deux objets `duration` représentent des intervalles de temps de même longueur ou si deux objets `time_point` représentent le même point dans le temps.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator==(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);
 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator==(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet `duration` ou `time_point` gauche.  
  
 `Right`  
 Objet `duration` ou `time_point` droit.  
  
### <a name="return-value"></a>Valeur de retour  
 La première fonction retourne `true` si `Left` et `Right` représentent des intervalles de temps de même longueur. Sinon, la fonction retourne `false`.  
  
 La deuxième fonction retourne `true` si `Left` et `Right` représentent le même point dans le temps. Sinon, la fonction retourne `false`.  
  
##  <a name="a-nameoperatorgta--operatorgt"></a><a name="operator_gt_"></a>  operator&gt;  
 Détermine si un objet [duration](../standard-library/duration-class.md) ou [time_point](../standard-library/time-point-class.md) est supérieur à un autre objet `duration` ou `time_point`.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator>(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);
 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator>(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet `duration` ou `time_point` gauche.  
  
 `Right`  
 Objet `duration` ou `time_point` droit.  
  
### <a name="return-value"></a>Valeur de retour  
 Chaque fonction retourne `Right < Left`.  
  
##  <a name="a-nameoperatorgteqa--operatorgt"></a><a name="operator_gt__eq"></a>  operator&gt;=  
 Détermine si un objet [duration](../standard-library/duration-class.md) ou [time_point](../standard-library/time-point-class.md) est supérieur ou égal à un autre objet `duration` ou `time_point`.  
  
```  
template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr bool operator>=(
    const duration<Rep1, Period1>& Left,  
    const duration<Rep2, Period2>& Right);
 
template <class Clock, class Duration1, class Duration2>  
constexpr bool operator>=(
    const time_point<Clock, Duration1>& Left,  
    const time_point<Clock, Duration2>& Right);
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet `duration` ou `time_point` gauche.  
  
 `Right`  
 Objet `duration` ou `time_point` droit.  
  
### <a name="return-value"></a>Valeur de retour  
 Chaque fonction retourne `!(Left < Right)`.  
  
##  <a name="a-nameoperatormoduloa--operator-modulo"></a><a name="operator_modulo"></a>  opérateur modulo  
 Opérateur pour les opérations modulo sur des objets [duration](../standard-library/duration-class.md).  
  
```  
template <class Rep1, class Period1, class Rep2>  
constexpr duration<Rep1, Period1, Rep2>::type 
   operator%(
      const duration<Rep1, Period1>& Dur,  
      const Rep2& Div);

template <class Rep1, class Period1, class Rep2, class Period2>  
constexpr typename common_type<duration<Rep1, _Period1>, duration<Rep2, Period2>>::type
   operator%(
     const duration<Rep1, Period1>& Left,  
     const duration<Rep2, Period2>& Right);
```  
  
### <a name="parameters"></a>Paramètres  
 `Dur`  
 Objet `duration`.  
  
 `Div`  
 Valeur intégrale.  
  
 `Left`  
 Objet gauche `duration`.  
  
 `Right`  
 Objet droit `duration`.  
  
### <a name="return-value"></a>Valeur de retour  
 La première fonction retourne un objet `duration` dont la longueur d'intervalle est `Dur` modulo `Div`.  
  
 La deuxième fonction retourne une valeur qui représente `Left` modulo `Right`.  
  
## <a name="see-also"></a>Voir aussi  
 [\<chrono>](../standard-library/chrono.md)


