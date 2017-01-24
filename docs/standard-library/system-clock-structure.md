---
title: "system_clock, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::system_clock"
dev_langs: 
  - "C++"
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
caps.latest.revision: 14
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# system_clock, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un *type d'horloge* basé sur l'horloge en temps réel du système.  
  
## Syntaxe  
  
```  
struct system_clock;  
```  
  
## Notes  
 Un *type d'horloge* est utilisé pour obtenir l'heure actuelle au format UTC.  Le type exprime une instanciation de [durée](../standard-library/duration-class.md) et le modèle de classe [time\_point](../standard-library/time-point-class.md), et il définit une fonction membre statique `now()` qui retourne l'heure.  
  
 Une horloge est *monotonic* si la valeur retournée par un premier appel à `now()` est toujours inférieure ou égale à la valeur retournée par un appel ultérieur à `now()`.  
  
 Une horloge est *steady* si elle est *monotonic* et si le laps de temps entre les battements d'horloge est constant.  
  
 Dans cette implémentation, un `system_clock` est un synonyme de `high_resolution_clock`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`system_clock::duration`|Synonyme de `duration<rep, period>`.|  
|`system_clock::period`|Synonyme du type qui est utilisé pour représenter le cycle d'horloge dans l'instanciation contenue de `duration`.|  
|`system_clock::rep`|Synonyme du type qui est utilisé pour représenter le nombre de battements d'horloge dans l'instanciation contenue de `duration`.|  
|`system_clock::time_point`|Synonyme de `time_point<Clock, duration>`, où `Clock` est un synonyme du type d'horloge ou d'un autre type d'horloge basé sur la même époque et ayant le même type `duration` imbriqué.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[system\_clock::from\_time\_t, méthode](../Topic/system_clock::from_time_t%20Method.md)|Static.  Retourne un `time_point` qui se rapproche le plus d'une heure spécifiée.|  
|[system\_clock::now, méthode](../Topic/system_clock::now%20Method.md)|Static.  Retourne l'heure actuelle.|  
|[system\_clock::to\_time\_t, méthode](../Topic/system_clock::to_time_t%20Method.md)|Static.  Retourne un objet `time_t` qui se rapproche le plus d'un `time_point` spécifié.|  
  
### Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[system\_clock::is\_monotonic, constante](../Topic/system_clock::is_monotonic%20Constant.md)|Spécifie si le type d'horloge est monotone.|  
|[system\_clock::is\_steady, constante](../Topic/system_clock::is_steady%20Constant.md)|Spécifie si le type d'horloge est stable.|  
  
## Configuration requise  
 **En\-tête :** chrono  
  
 **Espace de noms :** std::chrono  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [steady\_clock, struct](../standard-library/steady-clock-struct.md)