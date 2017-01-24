---
title: "&lt;bitset&gt; | Microsoft Docs"
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
  - "std::<bitset>"
  - "std.<bitset>"
  - "<bitset>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "en-tête <bitset>"
  - "bitset (en-tête)"
ms.assetid: af30a9b9-489e-46e3-9d29-5f3ea07ae6dc
caps.latest.revision: 19
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;bitset&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit la classe de modèle bitset et deux fonctions de modèle de prise en charge pour la représentation et la manipulation de séquences de bits de taille fixe.  
  
## Syntaxe  
  
```  
  
#include <bitset>  
  
```  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator&](../Topic/operator&%20\(%3Cbitset%3E\).md)|Exécute une opération AND au niveau du bit entre deux bitsets.|  
|[operator\<\<](../Topic/operator%3C%3C%20\(%3Cbitset%3E\).md)|Insère une représentation textuelle de la séquence de bits dans le flux de sortie standard.|  
|[operator\>\>](../Topic/operator%3E%3E%20\(%3Cbitset%3E\).md)|Insère une représentation textuelle de la séquence de bits dans le flux d'entrée standard.|  
|[operator^](../Topic/operator%5E%20\(%3Cbitset%3E\).md)|Exécute une opération EXCLUSIVE\-OR au niveau du bit entre deux bitsets.|  
|[operator&#124;](../Topic/operator%7C%20\(%3Cbitset%3E\).md)|Exécute une opération OR au niveau du bit entre deux bitsets.|  
  
### Classes  
  
|||  
|-|-|  
|[bitset, classe](../standard-library/bitset-class.md)|La classe de modèle décrit un type d'objet qui stocke une séquence composée d'un nombre fixe de bits qui offrent un moyen compact de conserver des indicateurs pour un ensemble d'éléments ou de conditions.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)