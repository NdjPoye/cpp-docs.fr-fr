---
title: recursive_timed_mutex, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::recursive_timed_mutex
dev_langs:
- C++
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: a28e9521455f0380f412fc2aa81aecd713f9535a
ms.lasthandoff: 02/24/2017

---
# <a name="recursivetimedmutex-class"></a>recursive_timed_mutex, classe
Représente un *type mutex limité dans le temps*. Les objets de ce type permettent d’appliquer une exclusion mutuelle (mutex) en utilisant un blocage limité dans le temps dans un programme. Contrairement aux objets de type [timed_mutex](../standard-library/timed-mutex-class.md), l’effet des appels à des méthodes de verrouillage sur les objets `recursive_timed_mutex` est bien défini.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class recursive_timed_mutex;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[recursive_timed_mutex, constructeur](#recursive_timed_mutex__recursive_timed_mutex_constructor)|Construit un objet `recursive_timed_mutex` qui n’est pas verrouillé.|  
|[~recursive_timed_mutex, destructeur](#recursive_timed_mutex___dtorrecursive_timed_mutex_destructor)|Libère les ressources utilisées par l’objet `recursive_timed_mutex`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[lock](#recursive_timed_mutex__lock_method)|Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.|  
|[try_lock](#recursive_timed_mutex__try_lock_method)|Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.|  
|[try_lock_for](#recursive_timed_mutex__try_lock_for_method)|Tente d’obtenir la propriété du `mutex` pour un intervalle de temps spécifié.|  
|[try_lock_until](#recursive_timed_mutex__try_lock_until_method)|Tente d’obtenir la propriété du `mutex` jusqu’à une heure spécifiée.|  
|[unlock](#recursive_timed_mutex__unlock_method)|Libère la propriété du `mutex`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** mutex  
  
 **Espace de noms :** std  
  
##  <a name="a-namerecursivetimedmutexlockmethoda--lock"></a><a name="recursive_timed_mutex__lock_method"></a>  lock  
 Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Notes  
 Si le thread appelant possède déjà le `mutex`, la méthode est retournée immédiatement, et le verrou précédent reste en vigueur.  
  
##  <a name="a-namerecursivetimedmutexrecursivetimedmutexconstructora--recursivetimedmutex-constructor"></a><a name="recursive_timed_mutex__recursive_timed_mutex_constructor"></a>  recursive_timed_mutex, constructeur  
 Construit un objet `recursive_timed_mutex` qui n’est pas verrouillé.  
  
```cpp  
recursive_timed_mutex();
```  
  
##  <a name="a-namerecursivetimedmutexdtorrecursivetimedmutexdestructora--recursivetimedmutex-destructor"></a><a name="recursive_timed_mutex___dtorrecursive_timed_mutex_destructor"></a>  ~recursive_timed_mutex, destructeur  
 Libère les ressources utilisées par l’objet `recursive_timed_mutex`.  
  
```cpp  
~recursive_timed_mutex();
```  
  
### <a name="remarks"></a>Notes  
 Si l'objet est verrouillé lorsque le destructeur s'exécute, le comportement est indéfini.  
  
##  <a name="a-namerecursivetimedmutextrylockmethoda--trylock"></a><a name="recursive_timed_mutex__try_lock_method"></a>  try_lock  
 Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode a réussi à obtenir la propriété du `mutex` ou si le thread appelant possède déjà le `mutex`. Sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Si le thread appelant possède déjà le `mutex`, la fonction retourne immédiatement `true`, et le verrou précédent reste en vigueur.  
  
##  <a name="a-namerecursivetimedmutextrylockformethoda--trylockfor"></a><a name="recursive_timed_mutex__try_lock_for_method"></a>  try_lock_for  
 Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.  
  
```cpp  
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Paramètres  
 `Rel_time`  
 Objet [chrono::duration](../standard-library/duration-class.md) qui spécifie la durée maximale pendant laquelle la méthode essaie d’obtenir la propriété du `mutex`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode réussit à obtenir la propriété du `mutex` ou si le thread appelant possède déjà le `mutex`. Sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Si le thread appelant possède déjà le `mutex`, la méthode retourne immédiatement `true`, et le verrou précédent reste en vigueur.  
  
##  <a name="a-namerecursivetimedmutextrylockuntilmethoda--trylockuntil"></a><a name="recursive_timed_mutex__try_lock_until_method"></a>  try_lock_until  
 Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.  
  
```cpp  
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```  
  
### <a name="parameters"></a>Paramètres  
 `Abs_time`  
 Point dans le temps qui spécifie le seuil au-delà duquel la méthode ne tente plus d'obtenir la propriété du `mutex`.  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode réussit à obtenir la propriété du `mutex` ou si le thread appelant possède déjà le `mutex`. Sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Si le thread appelant possède déjà le `mutex`, la méthode retourne immédiatement `true`, et le verrou précédent reste en vigueur.  
  
##  <a name="a-namerecursivetimedmutexunlockmethoda--unlock"></a><a name="recursive_timed_mutex__unlock_method"></a>  unlock  
 Libère la propriété du `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode libère la propriété du `mutex` uniquement si elle a été appelée autant de fois que [lock](#recursive_timed_mutex__lock_method), [try_lock](#recursive_timed_mutex__try_lock_method), [try_lock_for](#recursive_timed_mutex__try_lock_for_method) et [try_lock_until](#recursive_timed_mutex__try_lock_until_method) ont été appelés avec succès sur l’objet `recursive_timed_mutex`.  
  
 Si le thread appelant ne possède pas `mutex`, le comportement est indéfini.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



