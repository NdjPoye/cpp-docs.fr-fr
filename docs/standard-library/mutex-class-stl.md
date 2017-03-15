---
title: "mutex, classe (Bibliothèque standard C++)| Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::mutex
dev_langs:
- C++
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 11
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
ms.openlocfilehash: ff3e7e71c678ffc9bdead79ec56ad94f8e297a16
ms.lasthandoff: 02/24/2017

---
# <a name="mutex-class-c-standard-library"></a>mutex, classe (Bibliothèque standard C++)
Représente un *type mutex*. Vous pouvez utiliser des objets de ce type pour appliquer une exclusion mutuelle dans un programme.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class mutex;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[mutex::mutex, constructeur](#mutex__mutex_constructor)|Construit un objet `mutex`.|  
|[mutex::~mutex, destructeur](#mutex___dtormutex_destructor)|Libère toutes les ressources qui étaient utilisées par l’objet `mutex`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[mutex::lock, méthode](#mutex__lock_method)|Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.|  
|[mutex::native_handle, méthode](#mutex__native_handle_method)|Retourne le type propre à l’implémentation qui représente le descripteur de mutex.|  
|[mutex::try_lock, méthode](#mutex__try_lock_method)|Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.|  
|[mutex::unlock, méthode](#mutex__unlock_method)|Libère la propriété du `mutex`.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** mutex  
  
 **Espace de noms :** std  
  
##  <a name="a-namemutexlockmethoda--mutexlock-method"></a><a name="mutex__lock_method"></a> mutex::lock, méthode  
 Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Remarques  
 Si le thread appelant possède déjà `mutex`, le comportement est indéfini.  
  
##  <a name="a-namemutexmutexconstructora--mutexmutex-constructor"></a><a name="mutex__mutex_constructor"></a>  mutex::mutex, constructeur  
 Construit un objet `mutex` qui n’est pas verrouillé.  
  
```cpp  
constexpr mutex() noexcept;
```  
  
##  <a name="a-namemutexdtormutexdestructora--mutexmutex-destructor"></a><a name="mutex___dtormutex_destructor"></a>  mutex::~mutex, destructeur  
 Libère les ressources utilisées par l’objet `mutex`.  
  
```cpp  
~mutex();
```  
  
### <a name="remarks"></a>Notes  
 Si l'objet est verrouillé lorsque le destructeur s'exécute, le comportement est indéfini.  
  
##  <a name="a-namemutexnativehandlemethoda--mutexnativehandle-method"></a><a name="mutex__native_handle_method"></a>  mutex::native_handle, méthode  
 Retourne le type propre à l’implémentation qui représente le descripteur de mutex. Vous pouvez utiliser le descripteur de plusieurs manières propres à l’implémentation.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `native_handle_type` est défini comme un `Concurrency::critical_section *` converti en `void *`.  
  
##  <a name="a-namemutextrylockmethoda--mutextrylock-method"></a><a name="mutex__try_lock_method"></a>  mutex::try_lock, méthode  
 Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.  
  
```cpp  
bool try_lock();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode obtient correctement la propriété du `mutex` ; sinon, `false`.  
  
### <a name="remarks"></a>Remarques  
 Si le thread appelant possède déjà `mutex`, le comportement est indéfini.  
  
##  <a name="a-namemutexunlockmethoda--mutexunlock-method"></a><a name="mutex__unlock_method"></a>  mutex::unlock, méthode  
 Libère la propriété du `mutex`.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Remarques  
 Si le thread appelant ne possède pas `mutex`, le comportement est indéfini.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)




