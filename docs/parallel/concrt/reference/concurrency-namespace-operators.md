---
title: "Concurrency, espace de noms opérateurs | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::operator!=
- concrt/concurrency:[operator&amp;&amp
- concrt/concurrency:[operator&amp;&amp
dev_langs:
- C++
ms.assetid: 8e373f23-fc8e-49f7-82e6-ba0c57b822f8
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 322c95da1774cb0b1d621a46c74125f435ebfbc4
ms.lasthandoff: 03/17/2017

---
# <a name="concurrency-namespace-operators"></a>Concurrency, espace de noms opérateurs
||||  
|-|-|-|  
|[operator!=](#operator_neq)|[operator&amp;&amp;](#operator_amp_amp)|[operator&gt;](#operator_gt)|  
|[operator&gt;=](#operator_gt_eq)|[operator&lt;](#operator_lt)|[operator&lt;=](#operator_lt_eq)|  
|[operator==](#operator_eq_eq)|[operator||](#operator_lor)|  
  
##  <a name="operator_lor"></a>opérateur || (Opérateur)  
 Crée une tâche qui s’effectue correctement quand l’une des tâches fournies en tant qu’arguments s’effectue correctement.  
  
```  
template<typename ReturnType>  
task<ReturnType> operator||(
    const task<ReturnType>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>> operator||(
    const task<std::vector<ReturnType>>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>> operator||(
    const task<ReturnType>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
inline task<void> operator||(
    const task<void>& lhs,  
    const task<void>& rhs);
```  
  
### <a name="parameters"></a>Paramètres  
 `ReturnType`  
 Type de la tâche retournée.  
  
 `lhs`  
 Première tâche à associer à la tâche obtenue.  
  
 `rhs`  
 Seconde tâche à associer à la tâche obtenue.  
  
### <a name="return-value"></a>Valeur de retour  
 Une tâche se termine avec succès lorsqu’une des tâches d’entrée a abouti. Si les tâches d'entrée sont de type `T`, le résultat de cette fonction sera `task<std::vector<T>`. Si les tâches d'entrée sont de type `void`, la tâche de sortie sera également `task<void>`.  
  
### <a name="remarks"></a>Remarques  
 Si les deux tâches sont annulées ou lever des exceptions, la tâche retournée se terminera dans l’état annulé, et l’une des exceptions, si vous les rencontrez, sera levée lorsque vous appelez `get()` ou `wait()` sur la tâche.  
  
##  <a name="operator_amp_amp"></a>opérateur&amp; &amp; (opérateur)  
 Crée une tâche qui s’effectue correctement lorsque les deux tâches fournies comme arguments se déroulent correctement.  
  
```  
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,  
    const task<ReturnType>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<ReturnType>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
template<typename ReturnType>  
task<std::vector<ReturnType>>  operator&&(
    const task<std::vector<ReturnType>>& lhs,  
    const task<std::vector<ReturnType>>& rhs);

 
inline task<void>  operator&&(
    const task<void>& lhs,  
    const task<void>& rhs);
```  
  
### <a name="parameters"></a>Paramètres  
 `ReturnType`  
 Type de la tâche retournée.  
  
 `lhs`  
 Première tâche à associer à la tâche obtenue.  
  
 `rhs`  
 Seconde tâche à associer à la tâche obtenue.  
  
### <a name="return-value"></a>Valeur de retour  
 Tâche qui s’effectue correctement lorsque les deux tâches d’entrée se sont correctement déroulées. Si les tâches d'entrée sont de type `T`, le résultat de cette fonction sera `task<std::vector<T>>`. Si les tâches d'entrée sont de type `void`, la tâche de sortie sera également `task<void>`.  
  
### <a name="remarks"></a>Remarques  
 Si une des tâches est annulée ou lève une exception, la tâche retournée se terminera prématurément, à l'état Annulé, et l'exception, s'il y en a une, sera levée si vous appelez `get()` ou `wait()` pour cette tâche.  
  
##  <a name="operator_eq_eq"></a>opérateur ==, opérateur  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur est égal à l'objet `concurrent_vector` situé à droite.  
  
```  
template<typename T, class A1, class A2>  
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
  
### <a name="remarks"></a>Notes  
 Deux vecteurs simultanés sont égaux s’ils ont le même nombre d’éléments et de leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
 Cette méthode n’est pas en ce qui concerne les autres méthodes qui pourraient modifier un des vecteurs simultanés concurrentiel `_A` ou `_B`.  
  
##  <a name="operator_neq"></a>opérateur ! =, opérateur  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur n'est pas égal à l'objet `concurrent_vector` situé à droite.  
  
```  
template<typename T, class A1, class A2>  
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
  
### <a name="remarks"></a>Notes  
 Deux vecteurs simultanés sont égaux s’ils ont le même nombre d’éléments et de leurs éléments respectifs ont les mêmes valeurs. Sinon, elles sont inégales.  
  
 Cette méthode n’est pas en ce qui concerne les autres méthodes qui pourraient modifier un des vecteurs simultanés concurrentiel `_A` ou `_B`.  
  
##  <a name="operator_lt"></a>opérateur&lt; (opérateur)  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur est inférieur à l'objet `concurrent_vector` situé à droite.  
  
```  
template<typename T, class A1, class A2>  
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
  
### <a name="remarks"></a>Remarques  
 Le comportement de cet opérateur est identique à l’opérateur équivalent pour la `vector` de classe dans le `std` espace de noms.  
  
 Cette méthode n’est pas en ce qui concerne les autres méthodes qui pourraient modifier un des vecteurs simultanés concurrentiel `_A` ou `_B`.  
  
##  <a name="operator_lt_eq"></a>opérateur&lt;=, opérateur  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur est inférieur ou égal à l'objet `concurrent_vector` situé à droite.  
  
```  
template<typename T, class A1, class A2>  
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
  
##  <a name="operator_gt"></a>opérateur&gt; (opérateur)  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur est supérieur à l'objet `concurrent_vector` situé à droite.  
  
```  
template<typename T, class A1, class A2>  
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
  
##  <a name="operator_gt_eq"></a>opérateur&gt;=, opérateur  
 Teste si l'objet `concurrent_vector` situé à gauche de l'opérateur est supérieur ou égal à l'objet `concurrent_vector` situé à droite.  
  
```  
template<typename T, class A1, class A2>  
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
  
### <a name="remarks"></a>Remarques  
 Le comportement de cet opérateur est identique à l’opérateur équivalent pour la `vector` de classe dans le `std` espace de noms.  
  
 Cette méthode n’est pas en ce qui concerne les autres méthodes qui pourraient modifier un des vecteurs simultanés concurrentiel `_A` ou `_B`.  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)

