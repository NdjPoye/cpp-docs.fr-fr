---
title: "Macros nulles et non&#160;d&#233;finies | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "macros, nulles et non définies"
  - "programme NMAKE, macros null"
  - "programme NMAKE, macros non définies"
  - "macros null dans NMAKE"
  - "macros non définies et NMAKE"
ms.assetid: 1db4611a-1755-4328-b00f-d35365af8b6c
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Macros nulles et non&#160;d&#233;finies
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'expansion des macros aussi bien nulles que non définies se traduit par des chaînes nulles, mais une macro définie comme une chaîne nulle est considérée comme étant définie dans des expressions de prétraitement.  Pour définir une macro en tant que chaîne nulle, ne spécifiez aucun caractère en dehors des espaces et des tabulations après le signe égal à \(\=\) dans une ligne de commande ou un fichier de commandes, et placez la chaîne nulle ou la définition entre des guillemets doubles \(" "\).  Pour supprimer la définition d'une macro, utilisez **\!UNDEF.** Pour plus d'informations, consultez [Directives de prétraitement d'un makefile](../build/makefile-preprocessing-directives.md).  
  
## Voir aussi  
 [Définition d'une macro NMAKE](../build/defining-an-nmake-macro.md)