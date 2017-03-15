---
title: "lock_guard, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "mutex/std::lock_guard"
dev_langs: 
  - "C++"
ms.assetid: 57121f0d-9c50-481c-b971-54e64df864e0
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# lock_guard, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un modèle qui peut être instancié pour créer un objet dont le destructeur déverrouille un `mutex`.  
  
## Syntaxe  
  
```  
template<class Mutex>  
class lock_guard;  
```  
  
## Notes  
 L'argument de modèle `Mutex` doit nommer un *type d'exclusion mutuelle \(mutex\)*\).  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`lock_guard::mutex_type`|Synonyme pour l'argument de modèle `Mutex`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[lock\_guard::lock\_guard, constructeur](../Topic/lock_guard::lock_guard%20Constructor.md)|Construit un objet `lock_guard`.|  
|[lock\_guard::~lock\_guard, destructeur](../Topic/lock_guard::~lock_guard%20Destructor.md)|Déverrouille le `mutex` passé au constructeur.|  
  
## Configuration requise  
 **En\-tête :** mutex  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)