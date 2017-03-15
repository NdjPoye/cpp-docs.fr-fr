---
title: "Concurrency, espace de noms opérateurs | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 7fc7b500d882bb4e023904a147a7736996b5c5de
ms.lasthandoff: 02/24/2017

---
# <a name="concurrency-namespace-operators"></a>Concurrency, espace de noms opérateurs
||||  
|-|-|-|  
|[opérateur ! =, opérateur](#operator_neq)|[opérateur&amp; &amp; (opérateur)](#operator_amp_amp)|[opérateur&gt; (opérateur)](#operator_gt)|  
|[opérateur&gt;=, opérateur](#operator_gt_eq)|[opérateur&lt; (opérateur)](#operator_lt)|[opérateur&lt;=, opérateur](#operator_lt_eq)|  
|[opérateur ==, opérateur](#operator_eq_eq)|[operator|| Operator](#operator_lor)|  
  
##  <a name="a-nameoperatorlora--operator124124-operator"></a><a name="operator_lor"></a>opérateur || (Opérateur)  
 Crée une tâche qui s’effectue correctement quand l’une des tâches fournies en tant qu’arguments s’effectue correctement.  
  
```  
template<
    typename _ReturnType  
>  
task<_ReturnType>   operator||(
    const task<_ReturnType>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>   operator||(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>   operator||(
    const task<_ReturnType>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
inline task<void>   operator||(
    const task<void>& _Lhs,  
    const task<void>& _Rhs);
```  
  
### <a name="parameters"></a>Paramètres  
 `_ReturnType`  
 Type de la tâche retournée.  
  
 `_Lhs`  
 Première tâche à associer à la tâche obtenue.  
  
 `_Rhs`  
 Seconde tâche à associer à la tâche obtenue.  
  
### <a name="return-value"></a>Valeur de retour  
 Une tâche se termine avec succès lorsqu’une des tâches d’entrée a abouti. Si les tâches d'entrée sont de type `T`, le résultat de cette fonction sera `task<std::vector<T>`. Si les tâches d'entrée sont de type `void`, la tâche de sortie sera également `task<void>`.  
  
### <a name="remarks"></a>Remarques  
 Si les deux tâches sont annulées ou lever des exceptions, la tâche retournée se terminera dans l’état annulé, et l’une des exceptions, si vous les rencontrez, sera levée lorsque vous appelez `get()` ou `wait()` sur la tâche.  
  
##  <a name="a-nameoperatorampampa--operatorampamp-operator"></a><a name="operator_amp_amp"></a>opérateur&amp; &amp; (opérateur)  
 Crée une tâche qui s’effectue correctement lorsque les deux tâches fournies comme arguments se déroulent correctement.  
  
```  
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<_ReturnType>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<_ReturnType>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<_ReturnType>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
template<
    typename _ReturnType  
>  
task<std::vector<_ReturnType>>    operator&&(
    const task<std::vector<_ReturnType>>& _Lhs,  
    const task<std::vector<_ReturnType>>& _Rhs);

 
inline task<void>    operator&&(
    const task<void>& _Lhs,  
    const task<void>& _Rhs);
```  
  
### <a name="parameters"></a>Paramètres  
 `_ReturnType`  
 Type de la tâche retournée.  
  
 `_Lhs`  
 Première tâche à associer à la tâche obtenue.  
  
 `_Rhs`  
 Seconde tâche à associer à la tâche obtenue.  
  
### <a name="return-value"></a>Valeur de retour  
 Tâche qui s’effectue correctement lorsque les deux tâches d’entrée se sont correctement déroulées. Si les tâches d'entrée sont de type `T`, le résultat de cette fonction sera `task<std::vector<T>>`. Si les tâches d'entrée sont de type `void`, la tâche de sortie sera également `task<void>`.  
  
### <a name="remarks"></a>Remarques  
 Si une des tâches est annulée ou lève une exception, la tâche retournée se terminera prématurément, à l'état Annulé, et l'exception, s'il y en a une, sera levée si vous appelez `get()` ou `wait()` pour cette tâche.  
  
##  <a name="a-nameoperatoreqeqa--operator-operator"></a><a name="operator_eq_eq"></a>opérateur ==, opérateur  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur est égal à l'objet `concurrent_vector` situé à droite.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator== (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données des éléments stockés dans les vecteurs simultanés.  
  
 `A1`  
 Le type d’allocateur du premier `concurrent_vector` objet.  
  
 `A2`  
 Le type d’allocateur du deuxième `concurrent_vector` objet.  
  
 `_A`  
 Objet de type `concurrent_vector`.  
  
 `_B`  
 Objet de type `concurrent_vector`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le vecteur simultané sur le côté gauche de l’opérateur est égal au vecteur simultané sur le côté droit de l’opérateur. dans le cas contraire `false`.  
  
### <a name="remarks"></a>Remarques  
 Deux vecteurs simultanés sont égaux s’ils ont le même nombre d’éléments et de leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
 Cette méthode n’est pas en ce qui concerne les autres méthodes qui pourraient modifier un des vecteurs simultanés concurrentiel `_A` ou `_B`.  
  
##  <a name="a-nameoperatorneqa--operator-operator"></a><a name="operator_neq"></a>opérateur ! =, opérateur  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur n'est pas égal à l'objet `concurrent_vector` situé à droite.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator!= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données des éléments stockés dans les vecteurs simultanés.  
  
 `A1`  
 Le type d’allocateur du premier `concurrent_vector` objet.  
  
 `A2`  
 Le type d’allocateur du deuxième `concurrent_vector` objet.  
  
 `_A`  
 Objet de type `concurrent_vector`.  
  
 `_B`  
 Objet de type `concurrent_vector`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si les vecteurs simultanés ne sont pas égales ; `false` si les vecteurs simultanés sont égaux.  
  
### <a name="remarks"></a>Remarques  
 Deux vecteurs simultanés sont égaux s’ils ont le même nombre d’éléments et de leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
 Cette méthode n’est pas en ce qui concerne les autres méthodes qui pourraient modifier un des vecteurs simultanés concurrentiel `_A` ou `_B`.  
  
##  <a name="a-nameoperatorlta--operatorlt-operator"></a><a name="operator_lt"></a>opérateur&lt; (opérateur)  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur est inférieur à l'objet `concurrent_vector` situé à droite.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator<(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données des éléments stockés dans les vecteurs simultanés.  
  
 `A1`  
 Le type d’allocateur du premier `concurrent_vector` objet.  
  
 `A2`  
 Le type d’allocateur du deuxième `concurrent_vector` objet.  
  
 `_A`  
 Objet de type `concurrent_vector`.  
  
 `_B`  
 Objet de type `concurrent_vector`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le vecteur simultané sur le côté gauche de l’opérateur est inférieur au vecteur simultané sur le côté droit de l’opérateur. dans le cas contraire `false`.  
  
### <a name="remarks"></a>Notes  
 Le comportement de cet opérateur est identique à l’opérateur équivalent pour la `vector` de classe dans le `std` espace de noms.  
  
 Cette méthode n’est pas en ce qui concerne les autres méthodes qui pourraient modifier un des vecteurs simultanés concurrentiel `_A` ou `_B`.  
  
##  <a name="a-nameoperatorlteqa--operatorlt-operator"></a><a name="operator_lt_eq"></a>opérateur&lt;=, opérateur  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur est inférieur ou égal à l'objet `concurrent_vector` situé à droite.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator<= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données des éléments stockés dans les vecteurs simultanés.  
  
 `A1`  
 Le type d’allocateur du premier `concurrent_vector` objet.  
  
 `A2`  
 Le type d’allocateur du deuxième `concurrent_vector` objet.  
  
 `_A`  
 Objet de type `concurrent_vector`.  
  
 `_B`  
 Objet de type `concurrent_vector`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le vecteur simultané sur le côté gauche de l’opérateur est inférieur ou égal au vecteur simultané sur le côté droit de l’opérateur. dans le cas contraire `false`.  
  
### <a name="remarks"></a>Remarques  
 Le comportement de cet opérateur est identique à l’opérateur équivalent pour la `vector` de classe dans le `std` espace de noms.  
  
 Cette méthode n’est pas en ce qui concerne les autres méthodes qui pourraient modifier un des vecteurs simultanés concurrentiel `_A` ou `_B`.  
  
##  <a name="a-nameoperatorgta--operatorgt-operator"></a><a name="operator_gt"></a>opérateur&gt; (opérateur)  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur est supérieur à l'objet `concurrent_vector` situé à droite.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator>(
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données des éléments stockés dans les vecteurs simultanés.  
  
 `A1`  
 Le type d’allocateur du premier `concurrent_vector` objet.  
  
 `A2`  
 Le type d’allocateur du deuxième `concurrent_vector` objet.  
  
 `_A`  
 Objet de type `concurrent_vector`.  
  
 `_B`  
 Objet de type `concurrent_vector`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le vecteur simultané sur le côté gauche de l’opérateur est supérieur au vecteur simultané sur le côté droit de l’opérateur. dans le cas contraire `false`.  
  
### <a name="remarks"></a>Notes  
 Le comportement de cet opérateur est identique à l’opérateur équivalent pour la `vector` de classe dans le `std` espace de noms.  
  
 Cette méthode n’est pas en ce qui concerne les autres méthodes qui pourraient modifier un des vecteurs simultanés concurrentiel `_A` ou `_B`.  
  
##  <a name="a-nameoperatorgteqa--operatorgt-operator"></a><a name="operator_gt_eq"></a>opérateur&gt;=, opérateur  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur est supérieur ou égal à l'objet `concurrent_vector` situé à droite.  
  
```  
template<
    typename T,  
    class A1,  
    class A2  
>  
inline bool operator>= (
    const concurrent_vector<T, A1>& _A,  
    const concurrent_vector<T, A2>& _B);
```  
  
### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données des éléments stockés dans les vecteurs simultanés.  
  
 `A1`  
 Le type d’allocateur du premier `concurrent_vector` objet.  
  
 `A2`  
 Le type d’allocateur du deuxième `concurrent_vector` objet.  
  
 `_A`  
 Objet de type `concurrent_vector`.  
  
 `_B`  
 Objet de type `concurrent_vector`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true`Si le vecteur simultané sur le côté gauche de l’opérateur est supérieur ou égal au vecteur simultané sur le côté droit de l’opérateur. dans le cas contraire `false`.  
  
### <a name="remarks"></a>Notes  
 Le comportement de cet opérateur est identique à l’opérateur équivalent pour la `vector` de classe dans le `std` espace de noms.  
  
 Cette méthode n’est pas en ce qui concerne les autres méthodes qui pourraient modifier un des vecteurs simultanés concurrentiel `_A` ou `_B`.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

