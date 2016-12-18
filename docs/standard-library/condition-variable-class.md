---
title: "condition_variable, classe | Microsoft Docs"
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
  - "condition_variable/std::condition_variable"
dev_langs: 
  - "C++"
ms.assetid: 80b1295c-b73d-4d46-b664-6e183f2eec1b
caps.latest.revision: 16
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# condition_variable, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez la classe `condition_variable` pour attendre un événement lorsque vous avez un `mutex` de type `unique_lock<mutex>`.  Les objets de ce type peuvent avoir des meilleures performances que les objets de type [condition\_variable\_any\<unique\_lock\<mutex\>\>](../standard-library/condition-variable-any-class.md).  
  
## Syntaxe  
  
```  
class condition_variable;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[condition\_variable::condition\_variable, constructeur](../Topic/condition_variable::condition_variable%20Constructor.md)|Construit un objet `condition_variable`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[condition\_variable::native\_handle, méthode](../Topic/condition_variable::native_handle%20Method.md)|Retourne le type à l'implémentation représentant le handle condition\_variable.|  
|[condition\_variable::notify\_all, méthode](../Topic/condition_variable::notify_all%20Method.md)|Débloque tous les threads qui attendent l'objet `condition_variable`.|  
|[condition\_variable::notify\_one, méthode](../Topic/condition_variable::notify_one%20Method.md)|Débloque un des threads qui attendent l'objet `condition_variable`.|  
|[condition\_variable::wait, méthode](../Topic/condition_variable::wait%20Method.md)|Bloque un thread.|  
|[condition\_variable::wait\_for, méthode](../Topic/condition_variable::wait_for%20Method.md)|Bloque un thread, et définit un intervalle de temps après lequel le thread se débloque.|  
|[condition\_variable::wait\_until, méthode](../Topic/condition_variable::wait_until%20Method.md)|Bloque un thread, et définit un moment maximal auquel le thread se débloque.|  
  
## Configuration requise  
 **En\-tête :** condition\_variable  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<variable\_condition\>](../standard-library/condition-variable.md)