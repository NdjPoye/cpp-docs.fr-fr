---
title: steady_clock, struct | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::steady_clock
dev_langs:
- C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e1dbfac1eb8c67c5306bded6e6fd9ee8dacf54b0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="steadyclock-struct"></a>steady_clock, struct

Représente une horloge `steady`.

## <a name="syntax"></a>Syntaxe

```cpp
struct steady_clock;
```

## <a name="remarks"></a>Notes

Sous Windows, steady_clock encapsule la fonction QueryPerformanceCounter.

Une horloge est *monotonic* si la valeur retournée par un premier appel à `now()` est toujours inférieure ou égale à la valeur retournée par un appel ultérieur à `now()`.

Une horloge est *steady* si elle est *monotonic* et si le laps de temps entre les battements d’horloge est constant.

High_resolution_clock est un typdef pour steady_clock.

## <a name="public-functions"></a>Fonctions publiques

|Fonction|Description|
|--------------|-----------------|
|now|Retourne l'heure actuelle en tant que valeur time_point.|

## <a name="public-constants"></a>Constantes publiques

|Name|Description|
|----------|-----------------|
|`system_clock::is_steady`|Contient `true`. Un `steady_clock` est *steady*.|

## <a name="requirements"></a>Spécifications

**En-tête :** \<chrono >

**Espace de noms :** std::chrono

## <a name="see-also"></a>Voir aussi

[Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
[system_clock, structure](../standard-library/system-clock-structure.md)<br/>
