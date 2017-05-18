---
title: future, classe | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- future/std::future
- future/std::future::future
- future/std::future::get
- future/std::future::share
- future/std::future::valid
- future/std::future::wait
- future/std::future::wait_for
- future/std::future::wait_until
dev_langs:
- C++
ms.assetid: 495e82c3-5341-4e37-87dd-b40107fbdfb6
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 2a062caf9b28a48f2195f96b3a22f95a15c7149e
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="future-class"></a>future, classe
Décrit un *objet de retour asynchrone*.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class Ty>
class future;
```  
  
## <a name="remarks"></a>Notes  
 Chaque *fournisseur asynchrone* standard retourne un objet dont le type est une instanciation de ce modèle. Un objet `future` fournit le seul accès au fournisseur asynchrone qui lui est associé. Si vous avez besoin de plusieurs objets de retour asynchrones associés au même fournisseur asynchrone, copiez l’objet `future` dans un objet [shared_future](../standard-library/shared-future-class.md).  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[future](#future)|Construit un objet `future`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[get](#get)|Récupère le résultat stocké dans l’état asynchrone associé.|  
|[Partager](#share)|Convertit l’objet en `shared_future`.|  
|[valide](#valid)|Spécifie si l’objet n’est pas vide.|  
|[attente](#wait)|Bloque le thread actuel jusqu’à ce que l’état asynchrone associé soit prêt.|  
|[wait_for](#wait_for)|Bloque le thread actuel jusqu’à ce que l’état asynchrone associé soit prêt ou que le délai spécifié soit écoulé.|  
|[wait_until](#wait_until)|Bloque le thread actuel jusqu’à ce que l’état asynchrone associé soit prêt ou jusqu’à un point spécifié dans le temps.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[future::operator=](#op_eq)|Transfère l’état asynchrone associé d’un objet spécifié.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<future >  
  
 **Espace de noms :** std  
  
##  <a name="future"></a>  future::future, constructeur  
 Construit un objet `future`.  
  
```
future() noexcept;
future(future&& Other) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Other`  
 Objet `future`.  
  
### <a name="remarks"></a>Notes  
 Le premier constructeur construit un objet `future` sans état asynchrone associé.  
  
 Le deuxième constructeur construit un objet `future` et transfère l’état asynchrone associé de `Other`. `Other` n’a plus d’état asynchrone associé.  
  
##  <a name="get"></a>  future::get  
 Récupère le résultat stocké dans l’état asynchrone associé.  
  
```
Ty get();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si le résultat est une exception, la méthode la lève de nouveau. Sinon, le résultat est retourné.  
  
### <a name="remarks"></a>Notes  
 Avant de récupérer le résultat, cette méthode bloque le thread actuel jusqu’à ce que l’état asynchrone associé soit prêt.  
  
 Pour la spécialisation partielle `future<Ty&>`, la valeur stockée est une référence à l’objet qui a été passé au fournisseur asynchrone comme valeur de retour.  
  
 Comme il n’y a pas de valeur stockée pour la spécialisation `future<void>`, la méthode retourne `void`.  
  
 Dans d’autres spécialisations, la méthode déplace sa valeur de retour à partir de la valeur stockée. Par conséquent, n’appelez cette méthode qu’une seule fois.  
  
##  <a name="op_eq"></a>  future::operator=  
 Transfère un état asynchrone associé d’un objet spécifié.  
  
```
future& operator=(future&& Right) noexcept;
```  
  
### <a name="parameters"></a>Paramètres  
 `Right`  
 Objet `future`.  
  
### <a name="return-value"></a>Valeur de retour  
 `*this`  
  
### <a name="remarks"></a>Notes  
 Après le transfert, `Right` n’a plus d’état asynchrone associé.  
  
##  <a name="share"></a>  future::share  
 Convertit l’objet en un objet [shared_future](../standard-library/shared-future-class.md).  
  
```
shared_future<Ty> share();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `shared_future(move(*this))`  
  
##  <a name="valid"></a>  future::valid  
 Spécifie si l’objet a un état asynchrone associé.  
  
```
bool valid() noexcept;
```  
  
### <a name="return-value"></a>Valeur de retour  
 `true` si l'objet possède un état asynchrone associé ; sinon, `false`.  
  
##  <a name="wait"></a>  future::wait  
 Bloque le thread actuel jusqu’à ce que l’état asynchrone associé soit *prêt*.  
  
```cpp  
void wait() const;
```  
  
### <a name="remarks"></a>Notes  
 Un état asynchrone associé est *prêt* uniquement si son fournisseur asynchrone a stocké une valeur de retour ou une exception.  
  
##  <a name="wait_for"></a>  future::wait_for  
 Bloque le thread actuel jusqu’à ce que l’état asynchrone associé soit *prêt* ou que l’intervalle de temps spécifié soit écoulé.  
  
```
template <class Rep, class Period>
future_status wait_for(const chrono::duration<Rep, Period>& Rel_time) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `Rel_time`  
 Objet [chrono::duration](../standard-library/duration-class.md) qui spécifie un intervalle de temps maximal pour le blocage du thread.  
  
### <a name="return-value"></a>Valeur de retour  
 [future_status](../standard-library/future-enums.md#future_status) qui indique la raison du retour.  
  
### <a name="remarks"></a>Notes  
 Un état asynchrone associé est prêt uniquement si son fournisseur asynchrone a stocké une valeur de retour ou une exception.  
  
##  <a name="wait_until"></a>  future::wait_until  
 Bloque le thread actuel jusqu’à ce que l’état asynchrone associé soit *prêt* ou jusqu’à un point spécifié dans le temps.  
  
```cpp  
template <class Clock, class Duration>
future_status wait_until(const chrono::time_point<Clock, Duration>& Abs_time) const;
```  
  
### <a name="parameters"></a>Paramètres  
 `Abs_time`  
 Objet [chrono::time_point](../standard-library/time-point-class.md) qui spécifie un point dans le temps après lequel le thread peut être débloqué.  
  
### <a name="return-value"></a>Valeur de retour  
 [future_status](../standard-library/future-enums.md#future_status) qui indique la raison du retour.  
  
### <a name="remarks"></a>Notes  
 Un état asynchrone associé est *prêt* uniquement si son fournisseur asynchrone a stocké une valeur de retour ou une exception.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<future>](../standard-library/future.md)




