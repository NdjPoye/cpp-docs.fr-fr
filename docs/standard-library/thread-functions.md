---
title: '&lt;thread&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- thread/std::get_id
- thread/std::sleep_for
- thread/std::sleep_until
- thread/std::swap
- thread/std::yield
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
caps.latest.revision: 12
manager: ghogen
helpviewer_keywords:
- std::get_id [C++]
- std::sleep_for [C++]
- std::sleep_until [C++]
- std::swap [C++]
- std::yield [C++]
ms.translationtype: MT
ms.sourcegitcommit: 65f4e356ad0d46333b0d443d0fd6ac0b9f2b6f58
ms.openlocfilehash: dd073f48eb926e8fec0017f63ab77a91eb65acff
ms.contentlocale: fr-fr
ms.lasthandoff: 10/03/2017

---
# <a name="ltthreadgt-functions"></a>&lt;thread&gt;, fonctions
||||  
|-|-|-|  
|[get_id](#get_id)|[sleep_for](#sleep_for)|[sleep_until](#sleep_until)|  
|[swap](#swap)|[yield](#yield)|  
  
##  <a name="get_id"></a>  get_id  
 Identifie de façon unique le thread d’exécution en cours.  
  
```  
thread::id this_thread::get_id() noexcept;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un objet de type [thread::id](../standard-library/thread-class.md) qui identifie de façon unique le thread d’exécution en cours.  
  
##  <a name="sleep_for"></a>  sleep_for  
 Bloque le thread appelant.  
  
```  
template <class Rep,  
class Period>  
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```  
  
### <a name="parameters"></a>Paramètres  
 `Rel_time`  
 Objet [duration](../standard-library/duration-class.md) qui spécifie un intervalle de temps.  
  
### <a name="remarks"></a>Notes  
 La fonction bloque le thread appelant pendant au moins la durée spécifiée par `Rel_time`. Cette fonction ne lève aucune exception.  
  
##  <a name="sleep_until"></a>  sleep_until  
 Bloque le thread appelant au moins jusqu’à l’heure spécifiée.  
  
```  
template <class Clock, class Duration>  
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```  
  
### <a name="parameters"></a>Paramètres  
 `Abs_time`  
 Représente un point dans le temps.  
  
### <a name="remarks"></a>Notes  
 Cette fonction ne lève aucune exception.  
  
##  <a name="swap"></a>  swap  
 Permute les états de deux objets `thread`.  
  
```  
void swap(thread& Left, thread& Right) noexcept;  
```  
  
### <a name="parameters"></a>Paramètres  
 `Left`  
 Objet gauche `thread`.  
  
 `Right`  
 Objet droit `thread`.  
  
### <a name="remarks"></a>Notes  
 La fonction appelle `Left.swap(Right)`.  
  
##  <a name="yield"></a>  yield  
 Indique au système d’exploitation d’exécuter d’autres threads, même si le thread actuel continuerait normalement à s’exécuter.  
  
```  
inline void yield() noexcept;  
```  
  
## <a name="see-also"></a>Voir aussi  
 [\<thread>](../standard-library/thread.md)


