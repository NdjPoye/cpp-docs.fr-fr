---
title: "duration_values, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "chrono/std::chrono::duration_values"
dev_langs: 
  - "C++"
ms.assetid: 7f66d2e3-1faf-47c3-b47e-08f2a87f20e8
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# duration_values, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fournit des valeurs spécifiques du paramètre `Rep` du modèle de [durée](../standard-library/duration-class.md).  
  
## Syntaxe  
  
```  
template<class Rep>  
   struct duration_values;  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[duration\_values::max, méthode](../Topic/duration_values::max%20Method.md)|Static.  Spécifie la limite supérieure pour une valeur de type `Rep`.|  
|[duration\_values::min, méthode](../Topic/duration_values::min%20Method.md)|Static.  Spécifie la limite inférieure pour une valeur de type `Rep`.|  
|[duration\_values::zero, méthode](../Topic/duration_values::zero%20Method.md)|Static.  retourne `Rep(0)` ;|  
  
## Configuration requise  
 **En\-tête :** chrono  
  
 **Espace de noms :** std::chrono  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<chrono\>](../standard-library/chrono.md)