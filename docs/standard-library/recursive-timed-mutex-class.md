---
title: "recursive_timed_mutex, classe | Microsoft Docs"
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
  - "mutex/std::recursive_timed_mutex"
dev_langs: 
  - "C++"
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
caps.latest.revision: 9
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# recursive_timed_mutex, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un *type de mutex temporisé*.  Les objets de ce type sont utilisés pour appliquer l'exclusion mutuelle à l'aide de blocage limité dans le temps d'un programme.  Contrairement aux objets de type [timed\_mutex](../standard-library/timed-mutex-class.md), le résultat de l'appel des méthodes de verrouillage pour les objets `recursive_timed_mutex` est bien défini.  
  
## Syntaxe  
  
```  
class recursive_timed_mutex;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[recursive\_timed\_mutex::recursive\_timed\_mutex, constructeur](../Topic/recursive_timed_mutex::recursive_timed_mutex%20Constructor.md)|Construit un objet `recursive_timed_mutex` qui n'est pas verrouillé.|  
|[recursive\_timed\_mutex::~recursive\_timed\_mutex, destructeur](../Topic/recursive_timed_mutex::~recursive_timed_mutex%20Destructor.md)|Libère toutes ressources utilisées par l'objet de `recursive_timed_mutex`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[recursive\_timed\_mutex::lock, méthode](../Topic/recursive_timed_mutex::lock%20Method.md)|Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.|  
|[recursive\_timed\_mutex::try\_lock, méthode](../Topic/recursive_timed_mutex::try_lock%20Method.md)|Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.|  
|[recursive\_timed\_mutex::try\_lock\_for, méthode](../Topic/recursive_timed_mutex::try_lock_for%20Method.md)|Tente d'obtenir la propriété du `mutex` pour un intervalle de temps spécifié.|  
|[recursive\_timed\_mutex::try\_lock\_until, méthode](../Topic/recursive_timed_mutex::try_lock_until%20Method.md)|Tente d'obtenir la propriété du `mutex` jusqu'à une date spécifique.|  
|[recursive\_timed\_mutex::unlock, méthode](../Topic/recursive_timed_mutex::unlock%20Method.md)|Libère la propriété du `mutex`.|  
  
## Configuration requise  
 **En\-tête :** mutex  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)