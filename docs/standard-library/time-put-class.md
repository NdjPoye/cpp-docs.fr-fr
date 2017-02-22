---
title: "time_put, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std::time_put"
  - "time_put"
  - "xloctime/std::time_put"
  - "std.time_put"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_put (classe)"
ms.assetid: df79493e-3331-48d2-97c3-ac3a745f0791
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# time_put, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette classe de modèle décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler les conversions des valeurs temporelles en séquences de type `CharType`.  
  
## Syntaxe  
  
```  
template <  
   class CharType,  
   class OutputIterator = ostreambuf_iterator<CharType>  
> class time_put : public locale::facet;  
```  
  
#### Paramètres  
 `CharType`  
 Type utilisé dans le cadre d'un programme pour encoder des caractères.  
  
 `OutputIterator`  
 Type d'itération dans lequel les fonctions put temporelles enregistrent leur sortie.  
  
## Notes  
 Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro.  La première tentative d'accès à sa valeur stockée entraîne le stockage d'une valeur positive unique dans **id**.  
  
### Constructeurs  
  
|||  
|-|-|  
|[time\_put](../Topic/time_put::time_put.md)|Constructeur des objets de type `time_put`.|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/time_put::char_type.md)|Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.|  
|[iter\_type](../Topic/time_put::iter_type.md)|Type qui décrit un itérateur de sortie.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[do\_put](../Topic/time_put::do_put.md)|Fonction virtuelle qui fournit en sortie des informations de date et d'heure sous la forme d'une séquence d'objets `CharType`.|  
|[put](../Topic/time_put::put.md)|Fournit en sortie des informations de date et d'heure sous la forme d'une séquence d'objets `CharType`.|  
  
## Configuration requise  
 **En\-tête :** \<locale\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<locale\>](../standard-library/locale.md)   
 [time\_base, classe](../standard-library/time-base-class.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)