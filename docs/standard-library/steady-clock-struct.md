---
title: steady_clock, struct | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: chrono/std::chrono::steady_clock
dev_langs: C++
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5cd10ebcb9a068e78109c1a232b04c6beff9ebac
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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
