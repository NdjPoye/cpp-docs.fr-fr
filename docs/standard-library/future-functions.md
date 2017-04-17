---
title: '&lt;future&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e3acc1e-736a-42dc-ade2-b2fe69aa96bc
caps.latest.revision: 11
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 57a9e0ba45c363d126ef44dc80eeb13d72b3733d
ms.lasthandoff: 02/24/2017

---
# <a name="ltfuturegt-functions"></a>&lt;future&gt;, fonctions
||||  
|-|-|-|  
|[async](#async_function)|[future_category](#future_category_function)|[make_error_code](#make_error_code_function)|  
|[make_error_condition](#make_error_condition_function)|[swap](#swap_function)|  
  
##  <a name="a-nameasyncfunctiona--async"></a><a name="async_function"></a>  async  
 Représente un *fournisseur asynchrone*.  
  
```
template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(Fn&& fn, ArgTypes&&... args);

template <class Fn, class... ArgTypes>
future<typename result_of<Fn(ArgTypes...)>::type>
    async(launch policy, Fn&& fn, ArgTypes&&... args);
```  
  
### <a name="parameters"></a>Paramètres  
 `policy`  
 Valeur [launch](../standard-library/future-enums.md#launch_enumeration).  
  
### <a name="remarks"></a>Notes  
 Définitions des abréviations :  
  
|||  
|-|-|  
|*dfn*|Résultat de l’appel de `decay_copy(forward<Fn>(fn))`.|  
|*dargs*|Résultats des appels `decay_copy(forward<ArgsTypes>(args…))`.|  
|*Ty*|Le type `result_of<Fn(ArgTypes…)>::type`.|  
  
 La première fonction de modèle retourne `async(launch::any, fn, args…)`.  
  
 La deuxième fonction retourne un objet `future<Ty>` dont l’*état asynchrone associé* contient un résultat en plus des valeurs de *dfn* et *dargs* et d’un objet de thread pour gérer un thread d’exécution séparé.  
  
 À moins que `decay<Fn>::type` ne soit un type autre que launch, la deuxième fonction ne participe pas à la résolution de surcharge.  
  
 Si `policy` est `launch::any`, la fonction peut choisir `launch::async` ou `launch::deferred`. Dans cette implémentation, la fonction utilise `launch::async`.  
  
 Si `policy` est `launch::async`, la fonction crée un thread qui évalue `INVOKE(dfn, dargs..., Ty)`. La fonction retourne une valeur après avoir créé le thread sans attendre les résultats. Si le système ne peut pas démarrer de nouveau thread, la fonction lève un [system_error](../standard-library/system-error-class.md) dont le code d’erreur est `resource_unavailable_try_again`.  
  
 Si `policy` est `launch::deferred`, la fonction marque son état asynchrone associé comme contenant une *fonction différée* et retourne une valeur. Le premier appel à toute fonction non chronométrée qui attend que l’état asynchrone associé soit prêt appelle la fonction différée en évaluant `INVOKE(dfn, dargs..., Ty)`.  
  
 Dans tous les cas, l’état asynchrone associé de l’objet `future` n’est pas défini sur *prêt* avant la fin de l’évaluation de `INVOKE(dfn, dargs…, Ty)`, en levant une exception ou en retournant normalement une valeur. Le résultat de l’état asynchrone associé est une exception, s’il en a été levée une, ou toute valeur retournée par l’évaluation.  
  
> [!NOTE]
>  Pour un `future` (ou le dernier [shared_future](../standard-library/shared-future-class.md)) attaché à une tâche démarrée avec `std::async`, le destructeur se bloque si la tâche n’est pas terminée ; autrement dit, il se bloque si ce thread n’a pas encore appelé `.get()` ou `.wait()` et que la tâche est encore en cours d’exécution. Si un `future` obtenu à partir de `std::async` est déplacé en dehors de la portée locale, un autre code qui l’utilise doit être conscient que son destructeur peut empêcher l’état partagé d’être prêt.  
  
 La pseudo-fonction `INVOKE` est définie dans [\<functional>](../standard-library/functional.md).  
  
##  <a name="a-namefuturecategoryfunctiona--futurecategory"></a><a name="future_category_function"></a>  future_category  
 Retourne une référence à l’objet [error_category](../standard-library/error-category-class.md) qui caractérise les erreurs associées aux objets `future`.  
  
```
const error_category& future_category() noexcept;
```  
  
##  <a name="a-namemakeerrorcodefunctiona--makeerrorcode"></a><a name="make_error_code_function"></a>  make_error_code  
 Crée un [error_code](../standard-library/error-code-class.md) avec l’objet [error_category](../standard-library/error-category-class.md) qui caractérise les erreurs de [future](../standard-library/future-class.md).  
  
```
inline error_code make_error_code(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Errno`  
 Valeur [future_errc](../standard-library/future-enums.md#future_errc_enumeration) qui identifie l’erreur signalée.  
  
### <a name="return-value"></a>Valeur de retour  
 `error_code(static_cast<int>(Errno), future_category());`  
  
##  <a name="a-namemakeerrorconditionfunctiona--makeerrorcondition"></a><a name="make_error_condition_function"></a>  make_error_condition  
 Crée un [error_condition](../standard-library/error-condition-class.md) avec l’objet [error_category](../standard-library/error-category-class.md) qui caractérise les erreurs de [future](../standard-library/future-class.md).  
  
```
inline error_condition make_error_condition(future_errc Errno) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Errno`  
 Valeur [future_errc](../standard-library/future-enums.md#future_errc_enumeration) qui identifie l’erreur signalée.  
  
### <a name="return-value"></a>Valeur de retour  
 `error_condition(static_cast<int>(Errno), future_category());`  
  
##  <a name="a-nameswapfunctiona--swap"></a><a name="swap_function"></a>  swap  
 Échange l’*état asynchrone associé* d’un objet `promise` avec celui d’un autre.  
  
```
template <class Ty>
void swap(promise<Ty>& Left, promise<Ty>& Right) noexcept;

template <class Ty, class... ArgTypes>
void swap(packaged_task<Ty(ArgTypes...)>& Left, packaged_task<Ty(ArgTypes...)>& Right) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet gauche `promise`.  
  
 `Right`  
 Objet droit `promise`.  
  
## <a name="see-also"></a>Voir aussi  
 [\<future>](../standard-library/future.md)



