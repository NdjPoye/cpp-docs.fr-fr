---
title: "mutex, classe (STL) | Microsoft Docs"
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
  - "mutex/std::mutex"
dev_langs: 
  - "C++"
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
caps.latest.revision: 11
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mutex, classe (STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un *type de mutex*.  Les objets de ce type peuvent être utilisés pour appliquer l'exclusion mutuelle à l'intérieur d'un programme.  
  
## Syntaxe  
  
```  
class mutex;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[mutex::mutex, constructeur \(STL\)](../Topic/mutex::mutex%20Constructor%20\(STL\).md)|Construit un objet `mutex`.|  
|[mutex::~mutex, destructeur \(STL\)](../Topic/mutex::~mutex%20Destructor%20\(STL\).md)|Libère n'importe quelles ressources utilisées par l'objet `mutex`.|  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[mutex::lock, méthode \(STL\)](../Topic/mutex::lock%20Method%20\(STL\).md)|Bloque le thread appelant jusqu'à ce que le thread obtienne la propriété du `mutex`.|  
|[Méthode mutex::native\_handle \(STL\)](../Topic/mutex::native_handle%20Method%20\(STL\).md)|Retourne le type spécifique d'implémentation qui représente le handle du mutex.|  
|[mutex::try\_lock, méthode \(STL\)](../Topic/mutex::try_lock%20Method%20\(STL\).md)|Tente d'obtenir la propriété de la référence `mutex` sans se bloquer.|  
|[mutex::unlock, méthode \(STL\)](../Topic/mutex::unlock%20Method%20\(STL\).md)|Libère la propriété du `mutex`.|  
  
## Configuration requise  
 **En\-tête :** mutex  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)