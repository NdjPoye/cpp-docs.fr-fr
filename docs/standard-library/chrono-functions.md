---
title: '&lt;chrono&gt;, fonctions | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
caps.latest.revision: 10
manager: ghogen
ms.openlocfilehash: 91ea7bbec0f86d74cf87ee06b8ec130b13ede83e
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="ltchronogt-functions"></a>&lt;chrono&gt;, fonctions

||||
|-|-|-|
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|


## <a name="duration_cast"></a>  duration_cast

Caste un objet `duration` en un type spécifié.

```cpp
template <class To, class Rep, class Period>
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```

### <a name="return-value"></a>Valeur de retour

Objet `duration` de type `To` qui représente l’intervalle de temps `Dur`, qui est tronqué s’il doit tenir dans le type cible.

### <a name="remarks"></a>Notes

Si `To` est une instanciation de `duration`, cette fonction ne participe pas à la résolution de surcharge.

## <a name="time_point_cast"></a>  time_point_cast

Caste un objet [time_point](../standard-library/time-point-class.md) en type spécifié.

```cpp
template <class To, class Clock, class Duration>
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```

### <a name="return-value"></a>Valeur de retour

Objet `time_point` qui a une durée de type `To`.

### <a name="remarks"></a>Notes

À moins que `To` soit une instanciation de [duration](../standard-library/duration-class.md), cette fonction ne participe pas à la résolution de surcharge.

## <a name="see-also"></a>Voir aussi

[\<chrono>](../standard-library/chrono.md)<br/>
