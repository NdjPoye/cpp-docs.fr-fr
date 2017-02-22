---
title: "atomic_flag, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "atomic/std::atomic_flag"
dev_langs: 
  - "C++"
ms.assetid: 17f0c2f5-fd39-4a44-873a-b569720a670e
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# atomic_flag, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui définit et désactive atomiquement un indicateur `bool`.  Les opérations sur les indicateurs atomiques sont toujours sans verrouillage.  
  
## Syntaxe  
  
```  
struct atomic_flag;  
```  
  
## Membres  
  
### M&\#233;thodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[atomic\_flag::clear, méthode](../Topic/atomic_flag::clear%20Method.md)|Définit l'indicateur stocké sur `false`.|  
|[atomic\_flag::test\_and\_set, méthode](../Topic/atomic_flag::test_and_set%20Method.md)|Définit l'indicateur stocké sur `true` et retourne la valeur d'indicateur initiale.|  
  
## Notes  
 Des objets`atomic_flag` peuvent être passés aux fonctions non\-membres [atomic\_flag\_clear](../Topic/atomic_flag_clear%20Function.md), [atomic\_flag\_clear\_explicit](../Topic/atomic_flag_clear_explicit%20Function.md), [atomic\_flag\_test\_and\_set](../Topic/atomic_flag_test_and_set%20Function.md), et [atomic\_flag\_test\_and\_set\_explicit](../Topic/atomic_flag_test_and_set_explicit%20Function.md).  Ils peuvent être initialisés en utilisant la valeur `ATOMIC_FLAG_INIT`.  
  
## Configuration requise  
 **En\-tête :** atomique  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<atomic\>](../standard-library/atomic.md)