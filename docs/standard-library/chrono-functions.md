---
title: '&lt;chrono&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 9824bdc37d1ae2d1d3a8e42c727986fd2a194514
ms.lasthandoff: 02/24/2017

---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt;, fonctions
||||  
|-|-|-|  
|[duration_cast, fonction](#duration_cast_function)|[time_point_cast, fonction](#time_point_cast_function)|  
  

##  <a name="a-namedurationcastfunctiona--durationcast-function"></a><a name="duration_cast_function"></a>  duration_cast, fonction  
 Caste un objet `duration` en un type spécifié.  
  
```  
template <class To, class Rep, class Period>  
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `duration` de type `To` qui représente l’intervalle de temps `Dur`, qui est tronqué s’il doit tenir dans le type cible.  
  
### <a name="remarks"></a>Notes  
 Si `To` est une instanciation de `duration`, cette fonction ne participe pas à la résolution de surcharge.  
  
##  <a name="a-nametimepointcastfunctiona--timepointcast-function"></a><a name="time_point_cast_function"></a>  time_point_cast, fonction  
 Caste un objet [time_point](../standard-library/time-point-class.md) en type spécifié.  
  
```  
template <class To, class Clock, class Duration>  
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Objet `time_point` qui a une durée de type `To`.  
  
### <a name="remarks"></a>Notes  
 À moins que `To` soit une instanciation de [duration](../standard-library/duration-class.md), cette fonction ne participe pas à la résolution de surcharge.  
  
## <a name="see-also"></a>Voir aussi  
 [\<chrono>](../standard-library/chrono.md)


