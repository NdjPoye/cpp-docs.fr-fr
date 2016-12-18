---
title: "unique_lock, classe | Microsoft Docs"
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
  - "mutex/std::unique_lock"
dev_langs: 
  - "C++"
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
caps.latest.revision: 10
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# unique_lock, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un modèle qui peut être instancié pour créer des objets qui gèrent le verrouillage et le déverrouillage d'`mutex`.  
  
## Syntaxe  
  
```  
template<class Mutex>  
class unique_lock;  
```  
  
## Notes  
 L'argument TEMPLATE `Mutex` doit nommer *un type d'exclusion mutuelle \(mutex*\).  
  
 En interne, `unique_lock` fournit un pointeur vers un objet associé à `mutex` et un `bool` qui indique si le thread actuel est propriétaire `mutex`.  
  
## Membres  
  
### Typedefs publics  
  
|Nom|Description|  
|---------|-----------------|  
|`unique_lock::mutex_type`|Synonyme pour l'argument TEMPLATE `Mutex`.|  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[unique\_lock::unique\_lock, constructeur](../Topic/unique_lock::unique_lock%20Constructor.md)|Construit un objet `unique_lock`.|  
|[unique\_lock::~unique\_lock, destructeur](../Topic/unique_lock::~unique_lock%20Destructor.md)|Libère toutes les ressources associées à l'objet d'`unique_lock`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[unique\_lock::lock, méthode](../Topic/unique_lock::lock%20Method.md)|Bloque le thread appelant jusqu'à ce que le thread obtenir la propriété d'`mutex`associé.|  
|[unique\_lock::mutex, méthode](../Topic/unique_lock::mutex%20Method.md)|Récupère le pointeur stockée à `mutex`associé.|  
|[unique\_lock::owns\_lock, méthode](../Topic/unique_lock::owns_lock%20Method.md)|Spécifie si le thread appelant possède `mutex`associé.|  
|[unique\_lock::release, méthode](../Topic/unique_lock::release%20Method.md)|Dissocie l'objet d'`unique_lock` de l'objet associé à `mutex`.|  
|[unique\_lock::swap, méthode](../Topic/unique_lock::swap%20Method.md)|Habite `mutex` et l'état associés de propriété avec celle de l'objet spécifié.|  
|[unique\_lock::try\_lock, méthode](../Topic/unique_lock::try_lock%20Method.md)|Tente d'obtenir la propriété de la référence `mutex` associée sans se bloquer.|  
|[unique\_lock::try\_lock\_for, méthode](../Topic/unique_lock::try_lock_for%20Method.md)|Tente d'obtenir la propriété de la référence `mutex` associée sans se bloquer.|  
|[unique\_lock::try\_lock\_until, méthode](../Topic/unique_lock::try_lock_until%20Method.md)|Tente d'obtenir la propriété de la référence `mutex` associée sans se bloquer.|  
|[unique\_lock::unlock, méthode](../Topic/unique_lock::unlock%20Method.md)|Libère la propriété d'`mutex`associé.|  
  
### Op&\#233;rateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[unique\_lock::operator bool, opérateur](../Topic/unique_lock::operator%20bool%20Operator.md)|Spécifie si le thread appelant a la propriété d'`mutex`associé.|  
|[unique\_lock::operator\=, opérateur](../Topic/unique_lock::operator=%20Operator.md)|Copie le pointeur stockée d'`mutex` et l'état associé de la propriété d'un objet spécifié.|  
  
## Hiérarchie d'héritage  
 `unique_lock`  
  
## Configuration requise  
 **En\-tête :** mutex  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)