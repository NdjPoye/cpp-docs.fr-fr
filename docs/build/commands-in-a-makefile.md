---
title: "Commandes dans un makefile | Microsoft Docs"
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
  - "commandes, makefiles"
ms.assetid: 8085517e-42f4-493b-b8f8-44311fc08c64
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Commandes dans un makefile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un bloc de description ou une règle d'inférence spécifie l'exécution d'un bloc de commandes si la dépendance est obsolète.  NMAKE affiche chaque commande avant de l'exécuter, sauf si l'option \/S, **.SILENT**, **\!CMDSWITCHES** ou le symbole @ est utilisé.  NMAKE recherche une règle d'inférence correspondante si un bloc de description n'est pas suivi par un bloc de commandes.  
  
 Un bloc de commandes contient une ou plusieurs commandes, chacune sur sa propre ligne.  La dépendance ou la règle et le bloc de commandes ne peuvent pas être séparés par une ligne vide.  Cependant, une ligne contenant uniquement des espaces ou des tabulations peut les séparer ; cette ligne est interprétée comme une commande nulle, et aucune erreur ne s'ensuit.  Les lignes vides sont admises entre les lignes de commande.  
  
 Une ligne de commande commence par un ou plusieurs espaces ou tabulations.  Une barre oblique inverse \(\\\) suivi par un caractère de saut de ligne est interprétée comme un espace dans la commande ; utilisez une barre oblique inverse à la fin d'une ligne pour continuer la commande sur la ligne suivante.  NMAKE interprète la barre oblique inverse littéralement si elle est suivie par un autre caractère, espaces et tabulations compris.  
  
 Une commande précédée par un point\-virgule \(;\) peut figurer sur une ligne de dépendance ou dans une règle d'inférence, qu'elle soit suivie ou non par un bloc de commandes :  
  
```  
project.obj : project.c project.h ; cl /c project.c  
```  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
 [Modificateurs de commandes](../build/command-modifiers.md)  
  
 [Syntaxe des éléments d'un nom de fichier](../build/filename-parts-syntax.md)  
  
 [Fichiers inline dans un makefile](../build/inline-files-in-a-makefile.md)  
  
## Voir aussi  
 [Référence NMAKE](../build/nmake-reference.md)