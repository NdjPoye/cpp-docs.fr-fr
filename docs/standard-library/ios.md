---
title: "&lt;ios&gt; | Microsoft Docs"
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
  - "std.<ios>"
  - "std::<ios>"
  - "<ios>"
  - "ios/std::<ios>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ios (en-tête)"
ms.assetid: d3d4c161-2f37-4f04-93cc-0a2a89984a9c
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;ios&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit plusieurs types et fonctions de base pour l'opération d'iostreams.  Cet en\-tête est généralement inclus pour vous par un autre en\-tête iostream ; vous l'incluez rarement directement.  
  
## Syntaxe  
  
```  
  
#include <ios>  
  
```  
  
## Notes  
 Un grand nombre de fonctions sont des manipulateurs.  Un manipulateur déclaré dans \<ios\> modifie les valeurs stockées dans son objet d'argument de classe [ios\_base](../standard-library/ios-base-class.md).  D'autres manipulateurs effectuent des actions sur des flux contrôlés par des objets d'un type dérivé de cette classe, comme une spécialisation de l'une des classes de modèle [basic\_istream](../standard-library/basic-istream-class.md) ou [basic\_ostream](../standard-library/basic-ostream-class.md).  Par exemple, [noskipws](../Topic/noskipws.md)\(**str**\) efface l'indicateur de format `ios_base::skipws` dans l'objet **str**, qui peut être de l'un de ces types.  
  
 Vous pouvez également appeler un manipulateur en l'insérant dans un flux de sortie ou en l'extrayant d'un flux d'entrée, grâce à des opérations d'insertion et d'extraction spéciales fournies pour les classes dérivées de `ios_base`.  Exemple :  
  
```  
istr >> noskipws;  
```  
  
 appelle [noskipws](../Topic/noskipws.md)\(**istr**\).  
  
### Typedefs  
  
|||  
|-|-|  
|[ios](../Topic/ios.md)|Prend en charge la classe ios de l'ancienne bibliothèque iostream.|  
|[streamoff](../Topic/streamoff.md)|Prend en charge les opérations internes.|  
|[streampos](../Topic/streampos.md)|Contient la position actuelle du pointeur de mémoire tampon ou du pointeur de fichier.|  
|[streamsize](../Topic/streamsize.md)|Spécifie la taille du flux.|  
|[wios](../Topic/wios.md)|Prend en charge la classe wios de l'ancienne bibliothèque iostream.|  
|[wstreampos](../Topic/wstreampos.md)|Contient la position actuelle du pointeur de mémoire tampon ou du pointeur de fichier.|  
  
### Manipulateurs  
  
|||  
|-|-|  
|[boolalpha](../Topic/boolalpha.md)|Indique que les variables de type [bool](../cpp/bool-cpp.md) apparaissent comme **true** ou **false** dans le flux.|  
|[dec](../Topic/dec.md)|Indique que les variables de type entier sont affichées en notation de base 10.|  
|[defaultfloat](../Topic/%3Cios%3E%20defaultfloat.md)|Configure les indicateurs d'un objet `ios_base` pour utiliser un format d'affichage par défaut pour les valeurs de type float.|  
|[fixe](../Topic/fixed.md)|Indique qu'un nombre à virgule flottante est affiché en notation décimale fixe.|  
|[hex](../Topic/hex.md)|Indique que les variables de type entier sont affichées en notation de base 16.|  
|[internal](../Topic/internal%20\(Standard%20C++%20Library\).md)|Aligne à gauche le signe d'un nombre et aligne à droite le nombre.|  
|[left](../Topic/left.md)|Fait en sorte que le texte qui n'est pas aussi large que la largeur de sortie apparaisse dans le flux aligné avec la marge de gauche.|  
|[noboolalpha](../Topic/noboolalpha.md)|Indique que les variables de type [bool](../cpp/bool-cpp.md) apparaissent comme 1 ou 0 dans le flux.|  
|[noshowbase](../Topic/noshowbase.md)|Désactive l'indication de la base de notation dans laquelle un nombre est affiché.|  
|[noshowpoint](../Topic/noshowpoint.md)|Affiche uniquement la partie entière des nombres à virgule flottante dont la partie fractionnaire est égale à zéro.|  
|[noshowpos](../Topic/noshowpos.md)|Fait en sorte que les nombres positifs ne soient pas signés explicitement.|  
|[noskipws](../Topic/noskipws.md)|Fait en sorte que les espaces soient lus par le flux d'entrée.|  
|[nounitbuf](../Topic/nounitbuf.md)|Fait en sorte que la sortie soit mise en mémoire tampon et traitée quand la mémoire tampon est pleine.|  
|[nouppercase](../Topic/nouppercase.md)|Spécifie que les chiffres hexadécimaux et l'exposant en notation scientifique apparaissent en minuscules.|  
|[oct](../Topic/oct%20\(%3Cios%3E\).md)|Indique que les variables de type entier sont affichées en notation de base 8.|  
|[droit](../Topic/right.md)|Fait en sorte que le texte qui n'est pas aussi large que la largeur de sortie apparaisse dans le flux aligné avec la marge de droite.|  
|[scientifique](../Topic/scientific.md)|Fait en sorte que les nombres à virgule flottante soient affichés à l'aide de la notation scientifique.|  
|[showbase](../Topic/showbase.md)|Indique la base de notation dans laquelle un nombre est affiché.|  
|[showpoint](../Topic/showpoint.md)|Affiche la partie entière d'un nombre à virgule flottante et les chiffres à droite de la virgule décimale même quand la partie fractionnaire est égale à zéro.|  
|[showpos](../Topic/showpos.md)|Fait en sorte que les nombres positifs soient signés explicitement.|  
|[skipws](../Topic/skipws.md)|Fait en sorte que les espaces ne soient pas lus par le flux d'entrée.|  
|[unitbuf](../Topic/unitbuf.md)|Fait en sorte que la sortie soit traitée quand la mémoire tampon n'est pas vide.|  
|[majuscules](../Topic/uppercase.md)|Spécifie que les chiffres hexadécimaux et l'exposant en notation scientifique apparaissent en majuscules.|  
  
### Classes  
  
|||  
|-|-|  
|[basic\_ios](../standard-library/basic-ios-class.md)|La classe de modèle décrit les fonctions membres et de stockage communes aux flux d'entrée \(de classe de modèle [basic\_istream](../standard-library/basic-istream-class.md)\) et de sortie \(de classe de modèle [basic\_ostream](../standard-library/basic-ostream-class.md)\) qui dépendent des paramètres du modèle.|  
|[fpos](../standard-library/fpos-class.md)|La classe de modèle décrit un objet qui peut stocker toutes les informations nécessaires à la restauration d'un indicateur de position de fichier arbitraire dans n'importe quel flux.|  
|[ios\_base](../standard-library/ios-base-class.md)|La classe décrit les fonctions membres et de stockage communes aux flux d'entrée et de sortie qui ne dépendent pas des paramètres du modèle.|  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)