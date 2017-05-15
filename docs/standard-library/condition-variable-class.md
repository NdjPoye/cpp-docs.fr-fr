---
title: "condition_variable, classe │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- condition_variable/std::condition
- condition_variable/std::condition_variable::condition_variable
- condition_variable/std::condition_variable::native_handle
- condition_variable/std::condition_variable::notify_all
- condition_variable/std::condition_variable::notify_one
- condition_variable/std::condition_variable::wait
- condition_variable/std::condition_variable::wait_for
- condition_variable/std::condition_variable::wait_until
dev_langs:
- C++
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
caps.latest.revision: 16
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 5614afd8d17f119b47d11c641e3f999399f80925
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="conditionvariable-class"></a>condition_variable, classe
Utilisez la classe `condition_variable` pour attendre un événement quand vous avez un `mutex` de type `unique_lock<mutex>`. Les objets de ce type peuvent avoir de meilleures performances que les objets de type [condition_variable_any<unique_lock\<mutex>>](../standard-library/condition-variable-any-class.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```
class condition_variable;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[condition_variable](#condition_variable)|Construit un objet `condition_variable`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[native_handle](#native_handle)|Retourne le type spécifique de l’implémentation qui représente le descripteur condition_variable.|  
|[notify_all](#notify_all)|Débloque tous les threads qui attendent l’objet `condition_variable`.|  
|[notify_one](#notify_one)|Débloque un des threads qui attendent l’objet `condition_variable`.|  
|[attente](#wait)|Bloque un thread.|  
|[wait_for](#wait_for)|Bloque un thread et définit un intervalle de temps après lequel le thread est débloqué.|  
|[wait_until](#wait_until)|Bloque un thread et définit un point dans le temps maximal auquel le thread est débloqué.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<condition_variable >  
  
 **Espace de noms :** std  
  
##  <a name="condition_variable"></a>  condition_variable::condition_variable, constructeur  
 Construit un objet `condition_variable`.  
  
```
condition_variable();
```  
  
### <a name="remarks"></a>Notes  
 Si la mémoire disponible n’est pas suffisante, le constructeur lève un objet [system_error](../standard-library/system-error-class.md) avec le code d’erreur `not_enough_memory`. Si l’objet ne peut pas être construit, car une autre ressource n’est pas disponible, le constructeur lève un objet `system_error` avec le code d’erreur `resource_unavailable_try_again`.  
  
##  <a name="native_handle"></a>  condition_variable::native_handle  
 Retourne le type spécifique de l’implémentation qui représente le descripteur condition_variable.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `native_handle_type` est défini comme un pointeur vers les structures de données internes du runtime d’accès concurrentiel.  
  
##  <a name="notify_all"></a>  condition_variable::notify_all  
 Débloque tous les threads qui attendent l’objet `condition_variable`.  
  
```
void notify_all() noexcept;
```  
  
##  <a name="notify_one"></a>  condition_variable::notify_one  
 Débloque un des threads qui attendent l’objet `condition_variable`.  
  
```
void notify_one() noexcept;
```  
  
##  <a name="wait"></a>  condition_variable::wait  
 Bloque un thread.  
  
```
void wait(unique_lock<mutex>& Lck);

template <class Predicate>
void wait(unique_lock<mutex>& Lck, Predicate Pred);
```  
  
### <a name="parameters"></a>Paramètres  
 `Lck`  
 Objet [unique_lock\<mutex>](../standard-library/unique-lock-class.md).  
  
 `Pred`  
 Toute expression valide qui retourne `true` ou `false`.  
  
### <a name="remarks"></a>Notes  
 La première méthode se bloque jusqu’à ce que l’objet `condition_variable` soit signalé par un appel à [notify_one](#notify_one) ou [notify_all](#notify_all). Elle peut également s’éveiller sans motif.  
  
 La deuxième méthode exécute le code suivant.  
  
```cpp  
while(!Pred())
    wait(Lck);
```    
  
##  <a name="wait_for"></a>  condition_variable::wait_for  
 Bloque un thread et définit un intervalle de temps après lequel le thread est débloqué.  
  
```
template <class Rep, class Period>
cv_status wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time);

template <class Rep, class Period, class Predicate>
bool wait_for(
    unique_lock<mutex>& Lck,
    const chrono::duration<Rep, Period>& Rel_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>Paramètres  
 `Lck`  
 Objet [unique_lock\<mutex>](../standard-library/unique-lock-class.md).  
  
 `Rel_time`  
 Objet `chrono::duration` qui spécifie le délai avant l’éveil du thread.  
  
 `Pred`  
 Toute expression valide qui retourne `true` ou `false`.  
  
### <a name="return-value"></a>Valeur de retour  
 La première méthode retourne `cv_status::timeout` si l’attente se termine quand `Rel_time` est écoulé. Dans le cas contraire, la méthode retourne `cv_status::no_timeout`.  
  
 La deuxième méthode retourne la valeur de `Pred`.  
  
### <a name="remarks"></a>Notes  
 La première méthode se bloque jusqu’à ce que l’objet `condition_variable` soit signalé par un appel à [notify_one](#notify_one) ou [notify_all](#notify_all), ou jusqu’à ce que l’intervalle de temps `Rel_time` soit écoulé. Elle peut également s’éveiller sans motif.  
  
 La deuxième méthode exécute le code suivant.  
  
```cpp  
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
##  <a name="wait_until"></a>  condition_variable::wait_until  
 Bloque un thread et définit un point dans le temps maximal auquel le thread est débloqué.  
  
```
template <class Clock, class Duration>
cv_status wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time);

template <class Clock, class Duration, class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time, 
    Predicate Pred);

cv_status wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time);

template <class Predicate>
bool wait_until(
    unique_lock<mutex>& Lck,
    const xtime* Abs_time, 
    Predicate Pred);
```  
  
### <a name="parameters"></a>Paramètres  
 `Lck`  
 Objet [unique_lock\<mutex>](../standard-library/unique-lock-class.md).  
  
 `Abs_time`  
 Objet [chrono::time_point](../standard-library/time-point-class.md).  
  
 `Pred`  
 Toute expression valide qui retourne `true` ou `false`.  
  
### <a name="return-value"></a>Valeur de retour  
 Les méthodes qui retournent un type `cv_status` retournent `cv_status::timeout` si l’attente se termine quand `Abs_time` est écoulé. Sinon, les méthodes retournent `cv_status::no_timeout`.  
  
 Les méthodes qui retournent `bool` retournent la valeur de `Pred`.  
  
### <a name="remarks"></a>Notes  
 La première méthode se bloque jusqu’à ce que l’objet `condition_variable` soit signalé par un appel à [notify_one](#notify_one) ou [notify_all](#notify_all), ou jusqu’à `Abs_time`. Elle peut également s’éveiller sans motif.  
  
 La deuxième méthode exécute le code suivant  
  
```cpp  
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```  
  
 Les troisième et quatrième méthodes utilisent un pointeur vers un objet de type `xtime` pour remplacer l’objet `chrono::time_point`. L’objet `xtime` spécifie le délai d’attente maximal d’un signal.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [<condition_variable>](../standard-library/condition-variable.md)




