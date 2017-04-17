---
title: recursive_mutex, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- mutex/std::recursive_mutex
dev_langs:
- C++
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
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
ms.openlocfilehash: c82c8302be5d3e01de90adda2049a022100b8443
ms.lasthandoff: 02/24/2017

---
# <a name="recursivemutex-class"></a>recursive_mutex, classe
Représente un *type mutex*. Contrairement à [mutex](../standard-library/mutex-class-stl.md), le comportement est bien défini pour les appels aux méthodes de verrouillage sur des objets qui sont déjà verrouillés.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class recursive_mutex;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[recursive_mutex, constructeur](#recursive_mutex__recursive_mutex_constructor)|Construit un objet `recursive_mutex`.|  
|[~recursive_mutex, destructeur](#recursive_mutex___dtorrecursive_mutex_destructor)|Libère les ressources utilisées par l’objet `recursive_mutex`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[lock](#recursive_mutex__lock_method)|Bloque le thread appelant jusqu’à ce que le thread obtienne la propriété du mutex.|  
|[try_lock](#recursive_mutex__try_lock_method)|Tente d’obtenir la propriété du mutex sans bloquer le thread.|  
|[unlock](#recursive_mutex__unlock_method)|Libère la propriété du mutex.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** mutex  
  
 **Espace de noms :** std  
  
##  <a name="a-namerecursivemutexlockmethoda--lock"></a><a name="recursive_mutex__lock_method"></a>  lock  
 Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.  
  
```cpp  
void lock();
```  
  
### <a name="remarks"></a>Notes  
 Si le thread appelant possède déjà le `mutex`, la méthode est retournée immédiatement, et le verrou précédent reste en vigueur.  
  
##  <a name="a-namerecursivemutexrecursivemutexconstructora--recursivemutex"></a><a name="recursive_mutex__recursive_mutex_constructor"></a>  recursive_mutex  
 Construit un objet `recursive_mutex` qui n’est pas verrouillé.  
  
```cpp  
recursive_mutex();
```  
  
##  <a name="a-namerecursivemutexdtorrecursivemutexdestructora--recursivemutex"></a><a name="recursive_mutex___dtorrecursive_mutex_destructor"></a>  ~recursive_mutex  
 Libère les ressources utilisées par l’objet.  
  
```cpp  
~recursive_mutex();
```  
  
### <a name="remarks"></a>Notes  
 Si l'objet est verrouillé lorsque le destructeur s'exécute, le comportement est indéfini.  
  
##  <a name="a-namerecursivemutextrylockmethoda--trylock"></a><a name="recursive_mutex__try_lock_method"></a>  try_lock  
 Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.  
  
```cpp  
bool try_lock() noexcept;
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si la méthode réussit à obtenir la propriété du `mutex` ou si le thread appelant possède déjà le `mutex`. Sinon, `false`.  
  
### <a name="remarks"></a>Notes  
 Si le thread appelant possède déjà le `mutex`, la fonction retourne immédiatement `true`, et le verrou précédent reste en vigueur.  
  
##  <a name="a-namerecursivemutexunlockmethoda--unlock"></a><a name="recursive_mutex__unlock_method"></a>  unlock  
 Libère la propriété du mutex.  
  
```cpp  
void unlock();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode libère la propriété du `mutex` uniquement si elle a été appelée autant de fois que [lock](#recursive_mutex__lock_method) et [try_lock](#recursive_mutex__try_lock_method) ont été appelés avec succès sur l’objet `recursive_mutex`.  
  
 Si le thread appelant ne possède pas `mutex`, le comportement est indéfini.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex>](../standard-library/mutex.md)



