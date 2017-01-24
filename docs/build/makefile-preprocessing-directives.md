---
title: "Directives de pr&#233;traitement d&#39;un makefile | Microsoft Docs"
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
  - "!UNDEF"
  - "!INCLUDE"
  - "!IFNDEF"
  - "!MESSAGE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!CMDSWITCHES (directive)"
  - "!ELSE (directive)"
  - "!ELSEIF (directive)"
  - "!ELSEIFDEF (directive)"
  - "!ELSEIFNDEF (directive)"
  - "!ENDIF (directive)"
  - "!ERROR (directive)"
  - "!IF (directive)"
  - "!IFDEF (directive)"
  - "!IFNDEF (directive)"
  - "!INCLUDE (directive)"
  - "!MESSAGE (directive)"
  - "!UNDEF (directive)"
  - "CMDSWITCHES (directive)"
  - "directives, prétraitement d'un makefile"
  - "ELSE (directive)"
  - "ELSEIF (directive)"
  - "ELSEIFDEF (directive)"
  - "ELSEIFNDEF (directive)"
  - "ENDIF (directive)"
  - "ERROR (directive)"
  - "IF (directive)"
  - "IFDEF (directive)"
  - "IFNDEF (directive)"
  - "INCLUDE (directive)"
  - "makefiles, directives de prétraitement"
  - "MESSAGE (directive)"
  - "programme NMAKE, expressions"
  - "programme NMAKE, directives de préprocesseur"
  - "directives de prétraitement, makefiles"
  - "UNDEF (directive)"
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Directives de pr&#233;traitement d&#39;un makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les directives de prétraitement ne tiennent pas compte de la casse.  Le point d'exclamation initial \(\!\) doit apparaître au début de la ligne.  Aucun ou plusieurs espaces ou tabulations peuvent apparaître après le point d'exclamation, pour la mise en retrait.  
  
 **\!CMDSWITCHES**  
 {**\+**&#124; **–**}*option*...  Active ou désactive chaque *option* listée.  Les espaces ou les tabulations doivent apparaître devant l'opérateur \+ ou – ; aucun ne peut apparaître entre l'opérateur et les [lettres des options](../build/nmake-options.md).  Les lettres ne tiennent pas compte de la casse et sont spécifiées sans barre oblique \(\/\).  Pour activer ou désactiver certaines options, utilisez des spécifications séparées de **\!CMDSWITCHES**.  
  
 Seules les directives \/D, \/I, \/N et \/S sont admises dans un makefile.  Dans Tools.ini, toutes les options sont utilisables sauf \/F, \/HELP, \/NOLOGO, \/X et \/?.  Les modifications spécifiées dans un bloc de description ne prennent effet qu'avec le bloc de description suivant.  Cette directive met à jour **MAKEFLAGS** ; les modifications sont héritées lors de la récursivité si **MAKEFLAGS** est spécifiée.  
  
 **\!ERROR**  *texte*  
 Affiche *texte* dans l'erreur U1050, puis arrête NMAKE, même si \/K, \/I, **.IGNORE**, **\!CMDSWITCHES** ou le modificateur de commande tiret \(–\) est utilisé.  Les espaces ou les tabulations placés devant *texte* sont ignorés.  
  
 **\!MESSAGE**  *texte*  
 Affiche *texte* selon la sortie standard.  Les espaces ou les tabulations placés devant *texte* sont ignorés.  
  
 **\!INCLUDE**\[ **\<**\] *nomfichier*\[ **\>**\]  
 Lit *nomfichier* en tant que makefile, puis passe au makefile en cours.  NMAKE recherche *nomfichier* d'abord dans le répertoire spécifié ou actuel, puis de façon récursive parmi les répertoires de tout makefile parent, puis, si *nomfichier* est mis entre crochets \(\< \>\), dans les répertoires spécifiés par la macro **INCLUDE** qui est initialement définie selon la variable d'environnement INCLUDE.  Utile pour passer des paramètres **.SUFFIXES**, **.PRECIOUS** et des règles d'inférence aux makefiles récursifs.  
  
 **\!IF**  `constantexpression`  
 Traite les instructions entre la directive **\!IF** et la directive **\!ELSE** ou `!ENDIF` suivante si `constantexpression` s'évalue comme une valeur autre que zéro.  
  
 **\!IFDEF**  *nommacro*  
 Traite les instructions entre la directive `!IFDEF` et la directive **\!ELSE** ou `!ENDIF` suivante si l'élément *nommacro* est défini.  Une macro nulle est considérée comme étant définie.  
  
 **\!IFNDEF**  *nommacro*  
 Traite les instructions entre la directive **\!IFNDEF** et la directive **\!ELSE** ou `!ENDIF` suivante si *nommacro* est défini.  
  
 **\!ELSE**\[**IF** *expressionconstante* &#124; **IFDEF** *nommacro*&#124; **IFNDEF** *nommacro*\]  
 Traite les instructions entre la directive **\!ELSE** et la directive `!ENDIF` suivante si **\!IF**, `!IFDEF` ou **\!IFNDEF** précédente s'évaluait comme une valeur zéro.  Les mots clés facultatifs permettent un contrôle accru du prétraitement.  
  
 **\!ELSEIF**  
 Synonyme de **\!ELSE IF**.  
  
 **\!ELSEIFDEF**  
 Synonyme de **\!ELSE IFDEF**.  
  
 **\!ELSEIFNDEF**  
 Synonyme de **\!ELSE IFNDEF**.  
  
 `!ENDIF`  
 Marque la fin d'un bloc **\!IF**, `!IFDEF` ou **\!IFNDEF**.  Tout texte situé après `!ENDIF` sur la même ligne est ignoré.  
  
 **\!UNDEF**  *nommacro*  
 Annule la définition de *nommacro*.  
  
## Voir aussi  
 [Prétraitement d'un makefile](../build/makefile-preprocessing.md)