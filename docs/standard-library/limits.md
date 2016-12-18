---
title: "&lt;limits&gt; | Microsoft Docs"
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
  - "std.<limits>"
  - "std::<limits>"
  - "limits/std::<limits>"
  - "<limits>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "limits (en-tête)"
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;limits&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit la classe de modèle `numeric_limits` et deux énumérations concernant les représentations et l'arrondi des valeurs à virgule flottante.  
  
## Syntaxe  
  
```  
  
#include <limits>  
  
```  
  
## Notes  
 Les spécialisations explicites de la classe `numeric_limits` décrivent de nombreuses propriétés des types fondamentaux, y compris les types à virgule flottante, caractère, entier et `bool` qui sont définis par l'implémentation plutôt que fixés par les règles du langage C\+\+.  Les propriétés décrites dans \<limits\> incluent la précision, les représentations de taille minimale et maximale, l'arrondi et le signalement des erreurs de type.  
  
### Énumérations  
  
|||  
|-|-|  
|[float\_denorm\_style](../Topic/float_denorm_style.md)|L'énumération décrit les différentes méthodes qu'une implémentation peut choisir pour représenter une valeur à virgule flottante dénormalisée \(trop petite pour être représentée comme valeur normalisée\) :|  
|[float\_round\_style](../Topic/float_round_style.md)|L'énumération décrit les différentes méthodes qu'une implémentation peut choisir pour arrondir une valeur à virgule flottante en une valeur entière.|  
  
### Classes  
  
|||  
|-|-|  
|[numeric\_limits, classe](../standard-library/numeric-limits-class.md)|La classe de modèle décrit les propriétés arithmétiques des types numériques intégrés.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)