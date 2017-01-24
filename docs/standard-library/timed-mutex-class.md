---
title: "timed_mutex, classe | Microsoft Docs"
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
  - "mutex/std::timed_mutex"
dev_langs: 
  - "C++"
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# timed_mutex, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente *un type expiré d'exclusion mutuelle \(mutex*\).  Les objets de ce type sont utilisés pour appliquer l'exclusion mutuelle par le blocage temps limité dans le cadre d'un programme.  
  
## Syntaxe  
  
```  
class timed_mutex;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[timed\_mutex::timed\_mutex, constructeur](../Topic/timed_mutex::timed_mutex%20Constructor.md)|Construit un objet d'`timed_mutex` qui n'est pas verrouillé.|  
|[timed\_mutex::~timed\_mutex, destructeur](../Topic/timed_mutex::~timed_mutex%20Destructor.md)|Libère toutes les ressources utilisées par l'objet d'`timed_mutex`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[timed\_mutex::lock, méthode](../Topic/timed_mutex::lock%20Method.md)|Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.|  
|[timed\_mutex::try\_lock, méthode](../Topic/timed_mutex::try_lock%20Method.md)|Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.|  
|[timed\_mutex::try\_lock\_for, méthode](../Topic/timed_mutex::try_lock_for%20Method.md)|Tente d'obtenir la propriété d'`mutex` pour un intervalle de temps spécifié.|  
|[timed\_mutex::try\_lock\_until, méthode](../Topic/timed_mutex::try_lock_until%20Method.md)|Tente d'obtenir la propriété d'`mutex` jusqu'à une heure spécifique.|  
|[timed\_mutex::unlock, méthode](../Topic/timed_mutex::unlock%20Method.md)|Libère la propriété du `mutex`.|  
  
## Configuration requise  
 **En\-tête :** mutex  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)