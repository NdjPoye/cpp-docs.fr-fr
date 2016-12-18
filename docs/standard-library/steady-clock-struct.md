---
title: "steady_clock, struct | Microsoft Docs"
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
  - "chrono/std::chrono::steady_clock"
dev_langs: 
  - "C++"
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
caps.latest.revision: 14
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# steady_clock, struct
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente une horloge `steady`.  
  
## Syntaxe  
  
```  
struct steady_clock;  
```  
  
## Notes  
 Sous Windows, steady\_clock encapsule la fonction QueryPerformanceCounter.  
  
 Une horloge est *monotonic* si la valeur retournée par un premier appel à `now()` est toujours inférieure ou égale à la valeur retournée par un appel ultérieur à `now()`.  
  
 Une horloge est *steady* si elle est *monotonic* et si le laps de temps entre les battements d'horloge est constant.  
  
 High\_resolution\_clock est un typdef pour steady\_clock.  
  
## Fonctions publiques  
  
|Fonction|Description|  
|--------------|-----------------|  
|now|Retourne l'heure actuelle en tant que valeur time\_point.|  
  
## Constantes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`system_clock::is_steady`|Contient `true`.  Un `steady_clock` est *steady*.|  
  
## Configuration requise  
 **En\-tête :** chrono  
  
 **Espace de noms :** std::chrono  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)   
 [system\_clock, structure](../standard-library/system-clock-structure.md)