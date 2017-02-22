---
title: "condition_variable_any, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "condition_variable/std::condition_variable_any"
dev_langs: 
  - "C++"
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# condition_variable_any, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez la classe `condition_variable_any` pour attendre un événement de tout type `mutex`.  
  
## Syntaxe  
  
```  
class condition_variable_any;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[condition\_variable\_any::condition\_variable\_any, constructeur](../Topic/condition_variable_any::condition_variable_any%20Constructor.md)|Construit un objet `condition_variable_any`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[condition\_variable\_any::notify\_all, méthode](../Topic/condition_variable_any::notify_all%20Method.md)|Débloque tous les threads qui attendent l'objet `condition_variable_any`.|  
|[condition\_variable\_any::notify\_one, méthode](../Topic/condition_variable_any::notify_one%20Method.md)|Débloque un des threads qui attendent l'objet `condition_variable_any`.|  
|[condition\_variable\_any::wait, méthode](../Topic/condition_variable_any::wait%20Method.md)|Bloque un thread.|  
|[condition\_variable\_any::wait\_for, méthode](../Topic/condition_variable_any::wait_for%20Method.md)|Bloque un thread, et définit un intervalle de temps après lequel le thread se débloque.|  
|[condition\_variable\_any::wait\_until, méthode](../Topic/condition_variable_any::wait_until%20Method.md)|Bloque un thread, et définit un moment maximal auquel le thread se débloque.|  
  
## Configuration requise  
 **En\-tête :** condition\_variable  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<variable\_condition\>](../standard-library/condition-variable.md)