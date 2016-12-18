---
title: "&lt; map &gt; | Microsoft Docs"
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
  - "std::<map>"
  - "std.<map>"
  - "<map>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "map (en-tête)"
ms.assetid: bbf76680-7362-456e-88fa-ecda93561b6a
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt; map &gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les classes de modèle de conteneur map et multimap et leurs modèles de prise en charge.  
  
## Syntaxe  
  
```  
  
#include <map>  
  
```  
  
## Membres  
  
### Opérateurs  
  
|Version map|Version multimap|Description|  
|-----------------|----------------------|-----------------|  
|[operator\!\= \(map\)](../Topic/operator!=%20\(map\).md)|[operator\!\= \(multimap\)](../Topic/operator!=%20\(multimap\).md)|Teste si l'objet map ou multimap situé à gauche de l'opérateur n'est pas égal à l'objet map ou multimap situé à droite.|  
|[operator\< \(map\)](../Topic/operator==%20\(map\).md)|[operator\< \(multimap\)](../Topic/operator==%20\(multimap\).md)|Teste si l'objet map ou multimap situé à gauche de l'opérateur est inférieur à l'objet map ou multimap situé à droite.|  
|[operator\<\= \(map\)](../Topic/operator%3C%20\(map\).md)|[operator\<\= \(multimap\)](../Topic/operator%3C%20\(multimap\).md)|Teste si l'objet map ou multimap situé à gauche de l'opérateur est inférieur ou égal à l'objet map ou multimap situé à droite.|  
|[operator\=\= \(map\)](../Topic/operator%3C=%20\(map\).md)|[operator\=\= \(multimap\)](../Topic/operator%3C=%20\(multimap\).md)|Teste si l'objet map ou multimap situé à gauche de l'opérateur est égal à l'objet map ou multimap situé à droite.|  
|[operator\> \(map\)](../Topic/operator%3E%20\(map\).md)|[operator\> \(multimap\)](../Topic/operator%3E%20\(multimap\).md)|Teste si l'objet map ou multimap situé à gauche de l'opérateur est supérieur à l'objet map ou multimap situé à droite.|  
|[operator\>\= \(map\)](../Topic/operator%3E=%20\(map\).md)|[operator\>\= \(multimap\)](../Topic/operator%3E=%20\(multimap\).md)|Teste si l'objet map ou multimap situé à gauche de l'opérateur est supérieur ou égal à l'objet map ou multimap situé à droite.|  
  
### Fonctions avec modèle spécialisé  
  
|Version map|Version multimap|Description|  
|-----------------|----------------------|-----------------|  
|[swap \(map\)](../Topic/swap%20\(map\).md)|[swap \(multimap\)](../Topic/swap%20\(multimap\).md)|Échange les éléments de deux classes map ou multimap.|  
  
### Classes  
  
|||  
|-|-|  
|[value\_compare, classe](../standard-library/value-compare-class-map.md)|Fournit un objet de fonction qui peut comparer les éléments d'un map en comparant les valeurs de leurs clés pour déterminer leur ordre relatif dans le map.|  
|[map, classe](../standard-library/map-class.md)|Sert au stockage et à la récupération des données d’une collection dans laquelle chacun des éléments a une clé unique avec laquelle les données sont automatiquement triées.|  
|[multimap, classe](../standard-library/multimap-class.md)|Sert au stockage et à la récupération des données d’une collection dans laquelle chacun des éléments a une clé avec laquelle les données sont automatiquement triées et les clés ne doivent pas obligatoirement avoir des valeurs uniques.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)