---
title: "recursive_mutex, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::recursive_mutex"
dev_langs: 
  - "C++"
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# recursive_mutex, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un *type de mutex*.  Contrairement à [mutex](../standard-library/mutex-class-stl.md), le comportement des appels aux méthodes de verrouillage des objets qui sont déjà verrouillés est bien défini.  
  
## Syntaxe  
  
```  
class recursive_mutex;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[recursive\_mutex::recursive\_mutex, constructeur](../Topic/recursive_mutex::recursive_mutex%20Constructor.md)|Construit un objet `recursive_mutex`.|  
|[recursive\_mutex::~recursive\_mutex, destructeur](../Topic/recursive_mutex::~recursive_mutex%20Destructor.md)|Libère toutes les ressources utilisées par l'objet d'`recursive_mutex`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[recursive\_mutex::lock, méthode](../Topic/recursive_mutex::lock%20Method.md)|Bloque le thread appelant jusqu'à ce que le thread obtenir la propriété des mutex.|  
|[recursive\_mutex::try\_lock, méthode](../Topic/recursive_mutex::try_lock%20Method.md)|Tente d'obtenir la propriété des mutex sans blocage.|  
|[recursive\_mutex::unlock, méthode](../Topic/recursive_mutex::unlock%20Method.md)|Libère la propriété des mutex.|  
  
## Configuration requise  
 **En\-tête :** mutex  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)