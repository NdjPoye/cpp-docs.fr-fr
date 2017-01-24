---
title: "&lt;utility&gt; | Microsoft Docs"
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
  - "<utility>"
  - "utility/std::<utility>"
  - "std.<utility>"
  - "std::<utility>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "utility (en-tête)"
ms.assetid: c4491103-5da9-47a1-9c2b-ed8bc64b0599
caps.latest.revision: 18
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;utility&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit des types, des fonctions et des opérateurs de la bibliothèque STL \(Standard Template Library\) qui aident à construire et à gérer des paires d'objets qui sont utiles quand deux objets doivent être traités comme s'ils n'en étaient qu'un seul.  
  
## Syntaxe  
  
```  
  
#include <utility>  
  
```  
  
## Notes  
 Les paires sont largement utilisées dans la bibliothèque C\+\+ standard.  Elles sont nécessaires comme arguments et valeurs de retour pour diverses fonctions et comme types d'éléments pour des conteneurs tels que la [classe map](../standard-library/map-class.md) et la [classe multimap](../standard-library/multimap-class.md).  L'en\-tête \<utility\> est inclus automatiquement par \<map\> pour aider à gérer leurs éléments de type paire clé\/valeur.  
  
### Classes  
  
|||  
|-|-|  
|[tuple\_element](../standard-library/tuple-element-class-utility.md)|Classe qui encapsule le type d'un élément `pair`.|  
|[tuple\_size](../standard-library/tuple-size-class-utility.md)|Classe qui encapsule le nombre d'éléments `pair`.|  
  
### Fonctions  
  
|||  
|-|-|  
|[forward](../Topic/forward.md)|Empêche que le type de référence \(`lvalue` ou `rvalue`\) de l'argument ne soit masqué par le transfert parfait.|  
|[get](../Topic/get%20Function%20%3Cutility%3E.md)|Fonction qui obtient un élément d'un objet `pair`.|  
|[make\_pair](../Topic/make_pair.md)|Fonction d'assistance de modèle qui sert à construire des objets de type `pair`, où les types de composants sont basés sur les types de données passés comme paramètres.|  
|[move](../Topic/move.md)|Retourne l'argument passé comme référence `rvalue`.|  
|[swap](../Topic/swap%20\(%3Cutility%3E\).md)|Échange les éléments de deux objets `pair`.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[operator\!\=](../Topic/operator!=%20\(%3Cutility%3E\).md)|Teste si l'objet pair situé à gauche de l'opérateur n'est pas égal à l'objet pair situé à droite.|  
|[operator\=\=](../Topic/operator==%20\(%3Cutility%3E\).md)|Teste si l'objet pair situé à gauche de l'opérateur est égal à l'objet pair situé à droite.|  
|[operator\<](../Topic/operator%3C%20\(%3Cutility%3E\).md)|Teste si l'objet pair situé à gauche de l'opérateur est inférieur à l'objet pair situé à droite.|  
|[operator\<\=](../Topic/operator%3C=%20\(%3Cutility%3E\).md)|Teste si l'objet pair situé à gauche de l'opérateur est inférieur ou égal à l'objet pair situé à droite.|  
|[operator\>](../Topic/operator%3E%20\(%3Cutility%3E\).md)|Teste si l'objet pair situé à gauche de l'opérateur est supérieur à l'objet pair situé à droite.|  
|[operator\>\=](../Topic/operator%3E=%20\(%3Cutility%3E\).md)|Teste si l'objet pair situé à gauche de l'opérateur est supérieur ou égal à l'objet pair situé à droite.|  
  
### Structures  
  
|||  
|-|-|  
|[identité](../standard-library/identity-structure.md)||  
|[paire](../standard-library/pair-structure.md)|Struct qui permet de traiter deux objets comme s'il s'agissait d'un objet unique.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)