---
title: steady_clock, struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- chrono/std::chrono::steady_clock
dev_langs:
- C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
caps.latest.revision: 14
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
ms.sourcegitcommit: 4ecf60434799708acab4726a95380a2d3b9dbb3a
ms.openlocfilehash: 332008ed313eeae7f04f39165424a9280c2aed8c
ms.contentlocale: fr-fr
ms.lasthandoff: 04/19/2017

---
# <a name="steadyclock-struct"></a>steady_clock, struct
Représente une horloge `steady`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
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
  
|Nom|Description|  
|----------|-----------------|  
|`system_clock::is_steady`|Contient `true`. Un `steady_clock` est *steady*.|  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** \<chrono >  
  
 **Espace de noms :** std::chrono  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono>](../standard-library/chrono.md)   
 [system_clock, structure](../standard-library/system-clock-structure.md)

