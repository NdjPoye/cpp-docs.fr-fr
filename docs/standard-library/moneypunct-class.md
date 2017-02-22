---
title: "moneypunct, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "moneypunct"
  - "std.moneypunct"
  - "xlocmon/std::moneypunct"
  - "std::moneypunct"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "moneypunct (classe)"
ms.assetid: cf2650da-3e6f-491c-95d5-23e57f582ee6
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# moneypunct, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette classe de modèle décrit un objet pouvant servir de facette de paramètres régionaux pour décrire les séquences de type `CharType` utilisées pour représenter un champ d'entrée monétaire ou un champ de sortie monétaire.  Si le paramètre de modèle `Intl` est `true`, les conventions internationales sont respectées.  
  
## Syntaxe  
  
```  
template<class CharType, bool Intl>   
   class moneypunct;  
```  
  
#### Paramètres  
 `CharType`  
 Type utilisé dans le cadre d'un programme pour encoder des caractères.  
  
 `Intl`  
 Indicateur spécifiant si les conventions internationales doivent être respectées.  
  
## Notes  
 Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro.  La première tentative d'accès à sa valeur stockée entraîne le stockage d'une valeur positive unique dans **id**.  
  
 L'objet statique const intl stocke la valeur du paramètre de modèle **Intl**.  
  
### Constructeurs  
  
|||  
|-|-|  
|[moneypunct](../Topic/moneypunct::moneypunct.md)|Constructeur d'objets de type `moneypunct`.|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/moneypunct::char_type.md)|Type utilisé pour décrire un caractère utilisé par des paramètres régionaux.|  
|[string\_type](../Topic/moneypunct::string_type.md)|Type qui décrit une chaîne contenant des caractères de type `CharType`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[curr\_symbol](../Topic/moneypunct::curr_symbol.md)|Retourne une séquence spécifique aux paramètres régionaux d'éléments à utiliser comme symbole monétaire.|  
|[decimal\_point](../Topic/moneypunct::decimal_point.md)|Retourne une séquence spécifique aux paramètres régionaux d'éléments à utiliser comme symbole de virgule décimale.|  
|[do\_curr\_symbol](../Topic/moneypunct::do_curr_symbol.md)|Fonction membre virtuelle protégée qui retourne une séquence spécifique aux paramètres régionaux d'éléments à utiliser comme symbole monétaire.|  
|[do\_decimal\_point](../Topic/moneypunct::do_decimal_point.md)|Fonction membre virtuelle protégée qui est appelée pour retourner une séquence spécifique aux paramètres régionaux d'éléments à utiliser comme symbole de virgule décimale.|  
|[do\_frac\_digits](../Topic/moneypunct::do_frac_digits.md)|Cette fonction membre virtuelle protégée retourne un compte spécifique aux paramètres régionaux du nombre de chiffres à afficher à droite de la virgule décimale.|  
|[do\_grouping](../Topic/moneypunct::do_grouping.md)|Cette fonction membre virtuelle protégée retourne une règle spécifique aux paramètres régionaux permettant de déterminer la manière dont les chiffres sont regroupés à gauche de la virgule décimale.|  
|[do\_neg\_format](../Topic/moneypunct::do_neg_format.md)|Fonction membre virtuelle protégée qui est appelée pour retourner une règle spécifique aux paramètres régionaux pour mettre en forme les sorties avec des montants négatifs.|  
|[do\_negative\_sign](../Topic/moneypunct::do_negative_sign.md)|Fonction membre virtuelle protégée qui est appelée pour retourner une séquence spécifique aux paramètres régionaux d'éléments à utiliser comme symbole du signe négatif.|  
|[do\_pos\_format](../Topic/moneypunct::do_pos_format.md)|Fonction membre virtuelle protégée qui est appelée pour retourner une règle spécifique aux paramètres régionaux pour mettre en forme les sorties avec des montants positifs.|  
|[do\_positive\_sign](../Topic/moneypunct::do_positive_sign.md)|Fonction membre virtuelle protégée qui est appelée pour retourner une séquence spécifique aux paramètres régionaux d'éléments à utiliser comme symbole du signe positif.|  
|[do\_thousands\_sep](../Topic/moneypunct::do_thousands_sep.md)|Fonction membre virtuelle protégée qui est appelée pour retourner une séquence spécifique aux paramètres régionaux d'éléments à utiliser comme symbole de séparateur des milliers.|  
|[frac\_digits](../Topic/moneypunct::frac_digits.md)|Retourne un compte spécifique aux paramètres régionaux du nombre de chiffres à afficher à droite de la virgule décimale.|  
|[regroupement](../Topic/moneypunct::grouping.md)|Retourne une règle spécifique aux paramètres régionaux pour déterminer la manière dont les chiffres sont regroupés à gauche de la virgule décimale.|  
|[neg\_format](../Topic/moneypunct::neg_format.md)|Retourne une règle spécifique aux paramètres régionaux pour mettre en forme les sorties avec des montants négatifs.|  
|[negative\_sign](../Topic/moneypunct::negative_sign.md)|Retourne une séquence spécifique aux paramètres régionaux d'éléments à utiliser comme symbole du signe négatif.|  
|[pos\_format](../Topic/moneypunct::pos_format.md)|Retourne une règle spécifique aux paramètres régionaux pour mettre en forme les sorties avec des montants positifs.|  
|[positive\_sign](../Topic/moneypunct::positive_sign.md)|Retourne une séquence spécifique aux paramètres régionaux d'éléments à utiliser comme symbole du signe positif.|  
|[thousands\_sep](../Topic/moneypunct::thousands_sep.md)|Retourne une séquence spécifique aux paramètres régionaux d'éléments à utiliser comme symbole de séparateur des milliers.|  
  
## Configuration requise  
 **En\-tête :** \<locale\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<locale\>](../standard-library/locale.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)