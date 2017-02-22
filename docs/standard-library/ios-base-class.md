---
title: "ios_base, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ios_base"
  - "std.ios_base"
  - "std::ios_base"
  - "xiosbase/std::ios_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ios_base (classe)"
ms.assetid: 0f9e0abc-f70f-49bc-aa1f-003859f56cfe
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# ios_base, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe décrit les fonctions membres et de stockage communes aux flux d'entrée et de sortie qui ne dépendent pas des paramètres du modèle.  \(La classe de modèle [basic\_ios](../standard-library/basic-ios-class.md) décrit ce qui est commun et qui dépend des paramètres de modèle.\)  
  
 Un objet de la classe ios\_base stocke des informations de mise en forme, qui comprennent :  
  
-   Des indicateurs de format dans un objet de type [fmtflags](../Topic/ios_base::fmtflags.md).  
  
-   Un masque d'exception dans un objet de type [iostate](../Topic/ios_base::iostate.md).  
  
-   Une largeur de champ dans un objet de type `int`*.*  
  
-   Une précision d'affichage dans un objet de type `int`.  
  
-   Un objet de paramètres régionaux dans un objet de type **paramètres régionaux**.  
  
-   Deux tableaux extensibles, avec des éléments de type **long** et un pointeur `void`.  
  
 Un objet de la classe ios\_base stocke également des informations d'état de flux dans un objet de type [iostate](../Topic/ios_base::iostate.md) et une pile des rappels.  
  
### Constructeurs  
  
|||  
|-|-|  
|[ios\_base](../Topic/ios_base::ios_base.md)|Construit des objets `ios_base`.|  
  
### Typedefs  
  
|||  
|-|-|  
|[event\_callback](../Topic/ios_base::event_callback.md)|Décrit une fonction passée à [register\_call](../Topic/ios_base::register_callback.md).|  
|[fmtflags](../Topic/ios_base::fmtflags.md)|Constantes pour spécifier l'apparence de la sortie.|  
|[iostate](../Topic/ios_base::iostate.md)|Définit des constantes décrivant l'état d'un flux.|  
|[openmode](../Topic/ios_base::openmode.md)|Décrit comment interagir avec un flux.|  
|[seekdir](../Topic/ios_base::seekdir.md)|Spécifie le point de départ pour les opérations de décalage.|  
  
### Énumérations  
  
|||  
|-|-|  
|[événement](../Topic/ios_base::event.md)|Spécifie des types d'événements.|  
  
### Constantes  
  
|||  
|-|-|  
|[adjustfield](../Topic/ios_base::fmtflags.md)|Masque de bits défini comme `internal` &#124; `left` &#124; `right`.|  
|[app](../Topic/ios_base::openmode.md)|Spécifie qu'une recherche doit être effectuée jusqu'à la fin d'un flux avant chaque insertion.|  
|[ate](../Topic/ios_base::openmode.md)|Spécifie qu'une recherche doit être effectuée jusqu'à la fin d'un flux quand son objet de contrôle est créé en premier.|  
|[badbit](../Topic/ios_base::iostate.md)|Enregistre une perte d'intégrité de la mémoire tampon du flux.|  
|[basefield](../Topic/ios_base::fmtflags.md)|Masque de bits défini comme `dec` &#124; `hex` &#124; `oct`.|  
|[beg](../Topic/ios_base::seekdir.md)|Spécifie qu'une recherche doit être effectuée relativement au début d'une séquence.|  
|[binaire](../Topic/ios_base::openmode.md)|Spécifie qu'un fichier doit être lu comme un flux binaire, et non pas comme un flux de texte.|  
|[boolalpha](../Topic/ios_base::fmtflags.md)|Spécifie l'insertion ou l'extraction d'objets de type `bool` en tant que noms \(comme `true` et `false`\) et non pas en tant que valeurs numériques.|  
|[cur](../Topic/ios_base::seekdir.md)|Spécifie qu'une recherche doit être effectuée relativement à la position actuelle dans une séquence.|  
|[dec](../Topic/ios_base::fmtflags.md)|Spécifie l'insertion ou l'extraction de valeurs entières au format décimal.|  
|[end](../Topic/ios_base::seekdir.md)|Spécifie qu'une recherche doit être effectuée relativement à la fin d'une séquence.|  
|[eofbit](../Topic/ios_base::iostate.md)|Enregistre la fin de fichier lors de l'extraction à partir d'un flux.|  
|[failbit](../Topic/ios_base::iostate.md)|Enregistre un échec de l'extraction d'un champ valide dans un flux.|  
|[fixe](../Topic/ios_base::fmtflags.md)|Spécifie l'insertion de valeurs à virgule flottante dans un format à virgule fixe \(sans champ d'exposant\).|  
|[floatfield](../Topic/ios_base::fmtflags.md)|Masque de bits défini comme `fixed` &#124; `scientific`|  
|[goodbit](../Topic/ios_base::iostate.md)|Tous les bits d'état sont effacés.|  
|[hex](../Topic/ios_base::fmtflags.md)|Spécifie l'insertion ou l'extraction de valeurs entières au format hexadécimal.|  
|[in](../Topic/ios_base::openmode.md)|Spécifie l'extraction à partir d'un flux.|  
|[internal](../Topic/ios_base::fmtflags.md)|Complète jusqu'à une largeur de champ en insérant des caractères de remplissage à un point interne dans un champ numérique généré.|  
|[left](../Topic/ios_base::fmtflags.md)|Spécifie la justification à gauche.|  
|[oct](../Topic/ios_base::fmtflags.md)|Spécifie l'insertion ou l'extraction de valeurs entières au format octal.|  
|[out](../Topic/ios_base::openmode.md)|Spécifie l'insertion dans un flux.|  
|[droit](../Topic/ios_base::fmtflags.md)|Spécifie la justification à droite.|  
|[scientifique](../Topic/ios_base::fmtflags.md)|Spécifie l'insertion de valeurs à virgule flottante au format scientifique \(sans champ d'exposant\).|  
|[showbase](../Topic/ios_base::fmtflags.md)|Spécifie l'insertion d'un préfixe qui indique la base d'un champ d'entier généré.|  
|[showpoint](../Topic/ios_base::fmtflags.md)|Spécifie l'insertion inconditionnelle de la virgule décimale dans un champ à virgule flottante généré.|  
|[showpos](../Topic/ios_base::fmtflags.md)|Spécifie l'insertion d'un signe plus dans un champ numérique généré non négatif.|  
|[skipws](../Topic/ios_base::fmtflags.md)|Spécifie qu'il faut ignorer l'espace blanc du début avant certaines extractions.|  
|[trunc](../Topic/ios_base::openmode.md)|Spécifie la suppression du contenu d'un fichier existant lors de la création de son objet de contrôle.|  
|[unitbuf](../Topic/ios_base::fmtflags.md)|Provoque le vidage de la sortie après chaque insertion.|  
|[majuscules](../Topic/ios_base::fmtflags.md)|Spécifie l'insertion d'équivalents majuscules des lettres minuscules dans certaines insertions.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[failure](../Topic/ios_base::failure.md)|La classe membre sert de classe de base pour toutes les exceptions levées par la fonction membre [clear](../Topic/basic_ios::clear.md) dans la classe de modèle [basic\_ios](../standard-library/basic-ios-class.md).|  
|[flags](../Topic/ios_base::flags.md)|Définit ou retourne les valeurs de l'indicateur actuel.|  
|[getloc](../Topic/ios_base::getloc.md)|Retourne l'objet des paramètres régionaux stockés.|  
|[imbue](../Topic/ios_base::imbue.md)|Change les paramètres régionaux.|  
|[Init](../Topic/ios_base::Init.md)|Crée les objets iostream standard lors de la construction.|  
|[iword](../Topic/ios_base::iword.md)|Affecte une valeur à stocker comme `iword`.|  
|[precision](../Topic/ios_base::precision.md)|Spécifie le nombre de chiffres à afficher dans un nombre à virgule flottante.|  
|[pword](../Topic/ios_base::pword.md)|Affecte une valeur à stocker comme `pword`.|  
|[register\_callback](../Topic/ios_base::register_callback.md)|Spécifie une fonction de rappel.|  
|[setf](../Topic/ios_base::setf.md)|Définit les indicateurs spécifiés.|  
|[sync\_with\_stdio](../Topic/ios_base::sync_with_stdio.md)|Garantit que les opérations d'iostream et de la bibliothèque Runtime C se produisent dans l'ordre où elles apparaissent dans le code source.|  
|[unsetf](../Topic/ios_base::unsetf.md)|Désactive les indicateurs spécifiés.|  
|[width](../Topic/ios_base::width.md)|Définit la longueur du flux de sortie.|  
|[xalloc](../Topic/ios_base::xalloc.md)|Spécifie qu'une variable fera partie du flux.|  
  
### Opérateurs  
  
|||  
|-|-|  
|[opérateur \=](../Topic/ios_base::operator=.md)|Opérateur d'affectation pour les objets `ios_base`.|  
  
## Spécifications  
 **En\-tête :** \<ios\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)