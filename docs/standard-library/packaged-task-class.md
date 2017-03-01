---
title: packaged_task, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::packaged_task
dev_langs:
- C++
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
caps.latest.revision: 9
author: corob-msft
ms.author: corob
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
ms.sourcegitcommit: acc0ecd4edaf1e58977dcbdeb483d497a72bc4c8
ms.openlocfilehash: a54b1c9788ef60f63aafafc9125b09c449fde1b0
ms.lasthandoff: 02/24/2017

---
# <a name="packagedtask-class"></a>packaged_task, classe
Décrit un *fournisseur asynchrone* qui est un wrapper d’appel dont la signature d’appel est `Ty(ArgTypes...)`. Son *état asynchrone associé* contient une copie de l’objet pouvant être appelé, ainsi que le résultat potentiel.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class>
class packaged_task;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[packaged_task::packaged_task, constructeur](#packaged_task__packaged_task_constructor)|Construit un objet `packaged_task`.|  
|[packaged_task::~packaged_task, destructeur](#packaged_task___dtorpackaged_task_destructor)|Détruit un objet `packaged_task`.|  
  
### <a name="public-methods"></a>Méthodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[packaged_task::get_future](#packaged_task__get_future_method)|Retourne un objet [future](../standard-library/future-class.md) qui a le même état asynchrone associé.|  
|[packaged_task::make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method)|Appelle l’objet pouvant être appelé qui est stocké dans l’état asynchrone associé et stocke atomiquement la valeur retournée.|  
|[packaged_task::reset](#packaged_task__reset_method)|Remplace l’état asynchrone associé.|  
|[packaged_task::swap](#packaged_task__swap_method)|Échange l’état asynchrone associé avec celui d’un objet spécifié.|  
|[packaged_task::valid](#packaged_task__valid_method)|Spécifie si l’objet a un état asynchrone associé.|  
  
### <a name="public-operators"></a>Opérateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[packaged_task::operator=](#packaged_task__operator_eq)|Transfère un état asynchrone associé à partir d’un objet spécifié.|  
|[packaged_task::operator()](#packaged_task__operator__)|Appelle l’objet pouvant être appelé qui est stocké dans l’état asynchrone associé, stocke atomiquement la valeur retournée et définit l’état sur *ready*.|  
|[packaged_task::operator bool](#packaged_task__operator_bool)|Spécifie si l’objet a un état asynchrone associé.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** future  
  
 **Espace de noms :** std  
  
##  <a name="a-namepackagedtaskgetfuturemethoda--packagedtaskgetfuture"></a><a name="packaged_task__get_future_method"></a>  packaged_task::get_future  
 Retourne un objet de type `future<Ty>` qui a le même *état asynchrone associé*.  
  
```
future<Ty> get_future();
```  
  
### <a name="remarks"></a>Notes  
 Si l’objet `packaged_task` n’a pas d’état asynchrone associé, cette méthode lève une exception [future_error](../standard-library/future-error-class.md) avec le code d’erreur `no_state`.  
  
 Si cette méthode a déjà été appelée pour un objet `packaged_task` ayant le même état asynchrone associé, la méthode lève une exception `future_error` avec le code d’erreur `future_already_retrieved`.  
  
##  <a name="a-namepackagedtaskmakereadyatthreadexitmethoda--packagedtaskmakereadyatthreadexit"></a><a name="packaged_task__make_ready_at_thread_exit_method"></a>  packaged_task::make_ready_at_thread_exit  
 Appelle l’objet pouvant être appelé qui est stocké dans l’*état asynchrone associé* et stocke atomiquement la valeur retournée.  
  
```
void make_ready_at_thread_exit(ArgTypes... args);
```  
  
### <a name="remarks"></a>Notes  
 Si l’objet `packaged_task` n’a pas d’état asynchrone associé, cette méthode lève une exception [future_error](../standard-library/future-error-class.md) avec le code d’erreur `no_state`.  
  
 Si cette méthode ou [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) a déjà été appelée pour un objet `packaged_task` ayant le même état asynchrone associé, la méthode lève une exception `future_error` avec le code d’erreur `promise_already_satisfied`.  
  
 Sinon, cet opérateur appelle `INVOKE(fn, args..., Ty)`, où *fn* est l’objet pouvant être appelé qui est stocké dans l’état asynchrone associé. Chaque valeur retournée est stockée atomiquement comme résultat retourné de l’état asynchrone associé.  
  
 Contrairement à [packaged_task::operator()](#packaged_task__operator__), l’état asynchrone associé n’est pas défini à `ready` tant que les objets locaux de thread dans le thread appelant n’ont pas tous été détruits. En règle générale, les threads qui sont bloqués sur l’état asynchrone associé sont libérés seulement au moment de la sortie du thread appelant.  
  
##  <a name="a-namepackagedtaskoperatoreqa--packagedtaskoperator"></a><a name="packaged_task__operator_eq"></a>  packaged_task::operator=  
 Transfère l’*état asynchrone associé* à partir d’un objet spécifié.  
  
```
packaged_task& operator=(packaged_task&& Right);
```  
  
### <a name="parameters"></a>Paramètres  
 `Right`  
 Objet `packaged_task`.  
  
### <a name="return-value"></a>Valeur de retour  
 `*this`  
  
### <a name="remarks"></a>Notes  
 Après l’opération, `Right` n’a plus d’état asynchrone associé.  
  
##  <a name="a-namepackagedtaskoperatora--packagedtaskoperator"></a><a name="packaged_task__operator__"></a>  packaged_task::operator()  
 Appelle l’objet pouvant être appelé qui est stocké dans l’*état asynchrone associé*, stocke atomiquement la valeur retournée et définit l’état sur *ready*.  
  
```
void operator()(ArgTypes... args);
```  
  
### <a name="remarks"></a>Notes  
 Si l’objet `packaged_task` n’a pas d’état asynchrone associé, cette méthode lève une exception [future_error](../standard-library/future-error-class.md) avec le code d’erreur `no_state`.  
  
 Si cette méthode ou [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) a déjà été appelée pour un objet `packaged_task` ayant le même état asynchrone associé, la méthode lève une exception `future_error` avec le code d’erreur `promise_already_satisfied`.  
  
 Sinon, cet opérateur appelle `INVOKE(fn, args..., Ty)`, où *fn* est l’objet pouvant être appelé qui est stocké dans l’état asynchrone associé. Chaque valeur retournée est stockée atomiquement comme résultat retourné de l’état asynchrone associé, et l’état est défini sur ready. Tous les threads qui sont bloqués sur l’état asynchrone associé sont alors libérés.  
  
##  <a name="a-namepackagedtaskoperatorboola--packagedtaskoperator-bool"></a><a name="packaged_task__operator_bool"></a>  packaged_task::operator bool  
 Spécifie si l’objet a un `associated asynchronous state`.  
  
```
operator bool() const noexcept;
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si l'objet possède un état asynchrone associé ; sinon, `false`.  
  
##  <a name="a-namepackagedtaskpackagedtaskconstructora--packagedtaskpackagedtask-constructor"></a><a name="packaged_task__packaged_task_constructor"></a>  packaged_task::packaged_task, constructeur  
 Construit un objet `packaged_task`.  
  
```
packaged_task() noexcept;
packaged_task(packaged_task&& Right) noexcept;
template <class Fn>
   explicit packaged_task(Fn&& fn);

template <class Fn, class Alloc>
   explicit packaged_task(
      allocator_arg_t, const Alloc& alloc, Fn&& fn);
```  
  
### <a name="parameters"></a>Paramètres  
 `Right`  
 Objet `packaged_task`.  
  
 `alloc`  
 Allocateur de mémoire. Pour plus d’informations, consultez [\<allocators>](../standard-library/allocators-header.md).  
  
 `fn`  
 Objet de fonction.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur construit un objet `packaged_task` sans *état asynchrone associé*.  
  
 Le deuxième constructeur construit un objet `packaged_task` et transfère l’état asynchrone associé à partir de `Right`. Après l’opération, `Right` n’a plus d’état asynchrone associé.  
  
 Le troisième constructeur construit un objet `packaged_task` qui a une copie de `fn` stockée dans son état asynchrone associé.  
  
 Le quatrième constructeur construit un objet `packaged_task` qui a une copie de `fn` stockée dans son état asynchrone associé, et utilise `alloc` pour l’allocation de mémoire.  
  
##  <a name="a-namepackagedtaskdtorpackagedtaskdestructora--packagedtaskpackagedtask-destructor"></a><a name="packaged_task___dtorpackaged_task_destructor"></a>  packaged_task::~packaged_task, destructeur  
 Détruit un objet `packaged_task`.  
  
```
~packaged_task();
```  
  
### <a name="remarks"></a>Notes  
 Si l’*état asynchrone associé* n’est pas défini sur *ready*, le destructeur stocke une exception [future_error](../standard-library/future-error-class.md) avec le code d’erreur `broken_promise` comme résultat dans l’état asynchrone associé, et les threads qui sont bloqués sur l’état asynchrone associé sont libérés.  
  
##  <a name="a-namepackagedtaskresetmethoda--packagedtaskreset"></a><a name="packaged_task__reset_method"></a>  packaged_task::reset  
 Remplace l’état asynchrone associé existant par un nouvel *état asynchrone associé*.  
  
```
void reset();
```  
  
### <a name="remarks"></a>Notes  
 En effet, cette méthode exécute `*this = packaged_task(move(fn))`, où *fn* est l’objet de fonction qui est stocké dans l’état asynchrone associé pour cet objet. Par conséquent, l’état de l’objet est effacé, et les méthodes [get_future](#packaged_task__get_future_method), [operator()](#packaged_task__operator__) et [make_ready_at_thread_exit](#packaged_task__make_ready_at_thread_exit_method) peuvent être appelées de la même manière que pour un nouvel objet construit.  
  
##  <a name="a-namepackagedtaskswapmethoda--packagedtaskswap"></a><a name="packaged_task__swap_method"></a>  packaged_task::swap  
 Échange l’état asynchrone associé avec celui d’un objet spécifié.  
  
```
void swap(packaged_task& Right) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Right`  
 Objet `packaged_task`.  
  
##  <a name="a-namepackagedtaskvalidmethoda--packagedtaskvalid"></a><a name="packaged_task__valid_method"></a>  packaged_task::valid  
 Spécifie si l’objet a un `associated asynchronous state`.  
  
```
bool valid() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si l'objet possède un état asynchrone associé ; sinon, `false`.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)




