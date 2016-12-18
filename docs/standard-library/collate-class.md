---
title: "collate, classe | Microsoft Docs"
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
  - "std::collate"
  - "locale/std::collate"
  - "std.collate"
  - "collate"
  - "Collate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "collate (classe)"
ms.assetid: 92168798-9628-4a2e-be6e-fa62dcd4d6a6
caps.latest.revision: 18
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# collate, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe de modèle qui décrit un objet pouvant servir de facette de paramètres régionaux pour contrôler le tri et le regroupement des caractères d'une chaîne, pour leur comparaison et pour le hachage des chaînes.  
  
## Syntaxe  
  
```  
template <class CharType >  
   class collate : public locale::facet;  
```  
  
#### Paramètres  
 `CharType`  
 Type utilisé dans le cadre d'un programme pour encoder des caractères.  
  
## Notes  
 Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro.  La première tentative d'accès à sa valeur stockée entraîne le stockage d'une valeur positive unique dans **id**. Dans certaines langues, plusieurs caractères peuvent être regroupés et traités comme un seul caractère, et dans d'autres, un caractère peut être traité comme un ensemble de deux caractères.  Les services de classement fournis par la classe collate permettent de gérer ces cas.  
  
### Constructeurs  
  
|||  
|-|-|  
|[collate](../Topic/collate::collate.md)|Constructeur des objets de la classe `collate` qui sert de facette de paramètres régionaux pour la gestion des conventions de tri de chaînes.|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/collate::char_type.md)|Type qui décrit un caractère de type `CharType`.|  
|[string\_type](../Topic/collate::string_type.md)|Type qui décrit une chaîne de type `basic_string` qui contient des caractères de type `CharType`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[compare](../Topic/collate::compare.md)|Compare deux séquences de caractères selon leurs règles de facette afin de vérifier leur égalité ou leur inégalité.|  
|[do\_compare](../Topic/collate::do_compare.md)|Fonction virtuelle appelée pour comparer deux séquences de caractères selon leurs règles de facette afin de vérifier leur égalité ou leur inégalité.|  
|[do\_hash](../Topic/collate::do_hash.md)|Fonction virtuelle appelée pour déterminer la valeur de hachage des séquences en fonction de leurs règles de facette.|  
|[do\_transform](../Topic/collate::do_transform.md)|Fonction virtuelle appelée pour convertir une séquence de caractères de paramètres régionaux en une chaîne pouvant être utilisée dans des comparaisons lexicographiques avec d'autres séquences de caractères également converties depuis les mêmes paramètres régionaux.|  
|[hash](../Topic/collate::hash.md)|Détermine la valeur de hachage d'une séquence en fonction de ses règles de facette.|  
|[transformation](../Topic/collate::transform.md)|Convertit une séquence de caractères de paramètres régionaux en une chaîne qui peut être utilisée dans des comparaisons lexicographiques avec d'autres séquences de caractères, elles aussi converties depuis les mêmes paramètres régionaux.|  
  
## Configuration requise  
 **En\-tête :** \<locale\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<locale\>](../standard-library/locale.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)