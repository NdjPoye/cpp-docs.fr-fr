---
title: "time_point, classe | Microsoft Docs"
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
  - "chrono/std::chrono::time_point"
dev_langs: 
  - "C++"
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
caps.latest.revision: 10
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# time_point, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`time_point` décrit un type qui représente un instant temporel.  Elle maintient un objet du type [durée](../standard-library/duration-class.md) qui stocke le temps écoulé depuis l'époque représentée par l'argument de modèle `Clock`.  
  
## Syntaxe  
  
```  
template<  
   class Clock,  
   class Duration = typename Clock::duration  
>  
class time_point;  
```  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`time_point::clock`|Synonyme pour le paramètre de modèle `Clock`.|  
|`time_point::duration`|Synonyme pour le paramètre de modèle `Duration`.|  
|`time_point::period`|Synonyme pour le nom de type imbriqué `duration::period`.|  
|`time_point::rep`|Synonyme pour le nom de type imbriqué `duration::rep`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[time\_point::time\_point, constructeur](../Topic/time_point::time_point%20Constructor.md)|Construit un objet `time_point`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[time\_point::max, méthode](../Topic/time_point::max%20Method.md)|Spécifie la limite supérieure pour `time_point::ref`.|  
|[time\_point::min, méthode](../Topic/time_point::min%20Method.md)|Spécifie la limite inférieure pour `time_point::ref`.|  
|[time\_point::time\_since\_epoch, méthode](../Topic/time_point::time_since_epoch%20Method.md)|Retourne la valeur `duration`.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[time\_point::operator\+\=, opérateur](../Topic/time_point::operator+=%20Operator.md)|Ajoute une valeur spécifiée à la durée stockée.|  
|[time\_point::operator\-\=, opérateur](../Topic/time_point::operator-=%20Operator.md)|Soustrait une valeur spécifiée à la valeur de durée stockée.|  
  
## Configuration requise  
 **En\-tête :** chrono  
  
 **Espace de noms :** std::chrono  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)