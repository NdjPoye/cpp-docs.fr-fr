---
title: "Directives de prétraitement d’un makefile | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- '!UNDEF'
- '!INCLUDE'
- '!IFNDEF'
- '!MESSAGE'
dev_langs:
- C++
helpviewer_keywords:
- ERROR directive
- '!MESSAGE directive'
- IF directive
- '!UNDEF directive'
- IFDEF directive
- '!ELSEIF directive'
- '!IFDEF directive'
- '!IF directive'
- UNDEF directive
- '!CMDSWITCHES directive'
- ENDIF directive
- directives, makefile preprocessing
- INCLUDE directive
- IFNDEF directive
- preprocessing directives, makefiles
- '!IFNDEF directive'
- ELSEIFNDEF directive
- NMAKE program, expressions
- ELSEIF directive
- '!ERROR directive'
- '!ENDIF directive'
- MESSAGE directive
- '!INCLUDE directive'
- '!ELSEIFNDEF directive'
- CMDSWITCHES directive
- '!ELSEIFDEF directive'
- '!ELSE directive'
- NMAKE program, preprocessor directives
- makefiles, preprocessing directives
- ELSE directive
- ELSEIFDEF directive
ms.assetid: bcedeccb-d981-469d-b9e8-ab5d097fd8c2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 1bc73a86b0772b13731aaf7ac4e2ef0760caa8a5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="makefile-preprocessing-directives"></a>Directives de prétraitement d'un makefile
Les directives de prétraitement ne respectent pas la casse. Le point d’exclamation initial ( !) doit apparaître au début de la ligne. Zéro ou plusieurs espaces ou tabulations peuvent apparaître après le point d’exclamation, pour la mise en retrait.  
  
 **! CMDSWITCHES**  
 {**+**&#124;  **-** }*option*... Transforme tous *option* répertoriés ou désactiver. Des espaces ou des onglets doivent apparaître avant le + ou - opérateur ; aucun ne peut apparaître entre l’opérateur et la [option lettres](../build/nmake-options.md). Des lettres ne sont pas respecter la casse et sont spécifiés sans une barre oblique (/). Pour activer ou désactiver certaines options, utilisez des spécifications séparées de **! CMDSWITCHES**.  
  
 Uniquement d, / I, /N et /S sont admises dans un makefile. Tools.ini, toutes les options sont autorisées à l’exception de /F, /HELP /NOLOGO, / X, et / ?. Modifications spécifiées dans un bloc de description ne prennent pas d’effet jusqu'à ce que le bloc de description suivant. Met à jour de cette directive **MAKEFLAGS**; les modifications sont héritées lors de la récursivité si **MAKEFLAGS** est spécifié.  
  
 **! ERREUR***texte*   
 Affiche *texte* dans l’erreur U1050, puis arrête NMAKE, même si/k, / I, **. Ignorer les**, **! CMDSWITCHES**, ou le modificateur de commande tiret (-) est utilisé. Des espaces ou des onglets avant *texte* sont ignorés.  
  
 **! MESSAGE***texte*   
 Affiche *texte* vers la sortie standard. Des espaces ou des onglets avant *texte* sont ignorés.  
  
 **! INCLURE**[  **\<** ] *nom de fichier*[  **>** ]  
 Lit *nom de fichier* en tant que makefile, puis passe le makefile en cours. NMAKE recherche *nom de fichier* tout d’abord dans le répertoire spécifié ou en cours, puis de manière récursive dans les répertoires de n’importe quel parent makefiles, puis, si *nom de fichier* est mis entre crochets (\<>), dans les répertoires spécifiés par la **INCLUDE** macro, qui est initialement défini sur la variable d’environnement INCLUDE. Utile pour passer **. SUFFIXES** paramètres, **. PRÉCIEUX**et les règles d’inférence aux makefiles récursifs.  
  
 **! IF**  `constantexpression`  
 Traite les instructions entre **! IF** et la prochaine **! AUTRE** ou `!ENDIF` si `constantexpression` prend une valeur différente de zéro.  
  
 **! IFDEF***nom_macro*   
 Traite les instructions entre `!IFDEF` et la prochaine **! AUTRE** ou `!ENDIF` si *nom_macro* est défini. Une macro null est considérée comme étant définie.  
  
 **! IFNDEF***nom_macro*   
 Traite les instructions entre **! IFNDEF** et la prochaine **! AUTRE** ou `!ENDIF` si *nom_macro* n’est pas défini.  
  
 **! AUTRE**[**IF** *ExpressionConstante* &#124; **IFDEF** *nom_macro*&#124; **IFNDEF** *nom_macro*]  
 Traite les instructions entre **! AUTRE** et la prochaine `!ENDIF` si précédent **! IF**, `!IFDEF`, ou **! IFNDEF** instruction évaluée à zéro. Les mots clés facultatifs donnent le contrôle du prétraitement.  
  
 **! ELSEIF**  
 Synonyme de **! ELSE IF**.  
  
 **! ELSEIFDEF**  
 Synonyme de **! IFDEF ELSE**.  
  
 **! ELSEIFNDEF**  
 Synonyme de **! IFNDEF ELSE**.  
  
 `!ENDIF`  
 Marque la fin d’une **! IF**, `!IFDEF`, ou **! IFNDEF** bloc. Tout texte situé après `!ENDIF` sur la même ligne est ignoré.  
  
 **! UNDEF***nom_macro*   
 Annule la définition de *nom_macro*.  
  
## <a name="see-also"></a>Voir aussi  
 [Prétraitement d’un makefile](../build/makefile-preprocessing.md)