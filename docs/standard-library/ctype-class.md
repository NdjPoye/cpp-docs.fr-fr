---
title: "ctype, classe | Microsoft Docs"
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
  - "ctype"
  - "std::ctype"
  - "std.ctype"
  - "CType"
  - "xlocale/std::ctype"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype (classe)"
ms.assetid: 3627154c-49d9-47b5-b28f-5bbedee38e3b
caps.latest.revision: 19
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ctype, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Classe fournissant une facette utilisée pour la classification des caractères et la conversion entre majuscules et minuscules et entre le jeu de caractères natif et celui utilisé par les paramètres régionaux.  
  
## Syntaxe  
  
```  
template <class CharType>  
   class ctype : public ctype_base;  
```  
  
#### Paramètres  
 `CharType`  
 Type utilisé dans le cadre d'un programme pour encoder des caractères.  
  
## Notes  
 Comme avec n'importe quelle facette de paramètres régionaux, l'ID d'objet statique possède une valeur stockée initiale de zéro.  La première tentative d'accès à sa valeur stockée entraîne le stockage d'une valeur positive unique dans **id**. Les critères de classification sont fournis par un type de masque de bits imbriqué dans la classe de base ctype\_base.  
  
 La bibliothèque C\+\+ standard définit deux spécialisations explicites de cette classe de modèle :  
  
-   [ctype](#vclrf_locale_ctype_class)\<`char`\>, une spécialisation explicite dont les différences sont décrites séparément.  
  
-   **ctype**\<`wchar_t`\>, qui traite des éléments comme des caractères larges.  
  
 Autres spécialisations de la classe de modèle **ctype**\<**CharType**\> :  
  
-   Convertit une valeur ***ch*** de type **CharType** en une valeur de type `char` avec l'expression \(`char`\)**ch**.  
  
-   Convertit une valeur ***byte*** de type `char` en une valeur de type **CharType** avec l'expression **CharType** \(**byte**\).  
  
 Toutes les opérations sont effectuées sur des valeurs `char` de la même manière que pour la spécialisation explicite **ctype**\<`char`\>.  
  
### Constructeurs  
  
|||  
|-|-|  
|[ctype](../Topic/ctype::ctype.md)|Constructeur des objets de classe `ctype` qui servent de facettes de paramètres régionaux pour les caractères.|  
  
### Typedef  
  
|||  
|-|-|  
|[char\_type](../Topic/ctype::char_type.md)|Type qui décrit un caractère utilisé par les paramètres régionaux.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[do\_is](../Topic/ctype::do_is.md)|Fonction virtuelle appelée pour vérifier si un caractère unique possède un attribut particulier, ou pour classer les attributs de chaque caractère dans une plage et les stocker dans un tableau.|  
|[do\_narrow](../Topic/ctype::do_narrow.md)|Fonction virtuelle appelée pour convertir un caractère de type `CharType` utilisé par les paramètres régionaux en caractère correspondant de type `char` dans le jeu de caractères natif.|  
|[do\_scan\_is](../Topic/ctype::do_scan_is.md)|Fonction virtuelle appelée pour rechercher le premier caractère d'une plage qui correspond au masque spécifié.|  
|[do\_scan\_not](../Topic/ctype::do_scan_not.md)|Fonction virtuelle appelée pour rechercher le premier caractère d'une plage qui ne correspond pas au masque spécifié.|  
|[do\_tolower](../Topic/ctype::do_tolower.md)|Fonction virtuelle appelée pour convertir un caractère ou une plage de caractères en minuscules.|  
|[do\_toupper](../Topic/ctype::do_toupper.md)|Fonction virtuelle appelée pour convertir un caractère ou une plage de caractères en majuscules.|  
|[do\_widen](../Topic/ctype::do_widen.md)|Fonction virtuelle appelée pour convertir un caractère de type `char` du jeu de caractères natif en caractère correspondant de type `CharType` utilisé par les paramètres régionaux.|  
|[is](../Topic/ctype::is.md)|Vérifie si un caractère possède un attribut spécifique, ou classe les attributs de chaque caractère dans une plage et les stocke dans un tableau.|  
|[narrow](../Topic/ctype::narrow.md)|Convertit un caractère de type `CharType` utilisé par les paramètres régionaux en caractère correspondant de type char dans le jeu de caractères natif.|  
|[scan\_is](../Topic/ctype::scan_is.md)|Localise le premier caractère d'une plage qui correspond au masque spécifié.|  
|[scan\_not](../Topic/ctype::scan_not.md)|Localise le premier caractère d'une plage qui ne correspond pas au masque spécifié.|  
|[tolower](../Topic/ctype::tolower.md)|Convertit un caractère ou une plage de caractères en minuscules.|  
|[toupper](../Topic/ctype::toupper.md)|Convertit un caractère ou une plage de caractères en majuscules.|  
|[widen](../Topic/ctype::widen.md)|Convertit un caractère de type `char` dans le jeu de caractères natif en caractère correspondant de type `CharType` utilisé par les paramètres régionaux.|  
  
## Configuration requise  
 **En\-tête :** \<locale\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<locale\>](../standard-library/locale.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)