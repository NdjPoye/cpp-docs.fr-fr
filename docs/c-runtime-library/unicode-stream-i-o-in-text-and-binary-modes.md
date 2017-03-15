---
title: "E/S de flux Unicode en modes texte et binaire | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.io"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "E/S (CRT), flux unicode"
  - "routines E/S de flux"
  - "flux unicode E/S"
  - "Unicode, routines E/S de flux"
ms.assetid: 68be0c3e-a9e6-4fd5-b34a-1b5207f0e7d6
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# E/S de flux Unicode en modes texte et binaire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsqu'une routine d'E\/S de flux de données Unicode \(par exemple `fwprintf`, `fwscanf`, `fgetwc`, `fputwc`, `fgetws`, ou `fputws`\) traite un fichier ouvert en mode texte \(valeur par défaut\), deux types de conversions de caractères ont lieu :  
  
-   Conversion Unicode\- à \- MBCS ou MBCS\-à\- Unicode.  Lorsqu'une fonction d'E\/S de flux Unicode s'exécute en mode texte, on suppose que le flux source ou de destination est une séquence de caractères multioctets.  Par conséquent, les fonctions d'entrée de flux Unicode convertissent les caractères multioctets en caractères larges \(comme suite à un appel à la fonction `mbtowc`\).  Pour la même raison, les fonctions de flux de sortie Unicode convertissent les caractères larges en caractères multioctets \(comme suite à un appel à la fonction `wctomb`\).  
  
-   Traduction saut de ligne – retour de chariot \(CR\-LF\) .  Cette traduction se produit avant le MBCS – conversion Unicode \(pour les fonctions d'entrée de flux de données Unicode\) et après conversion Unicode et MBCS \(pour les fonctions de flux de données Unicode\).  Lors de l'entrée, chaque combinaison CR\-LF est convertie en un unique caractère de saut de ligne.  Lors de la sortie, chaque caractère de saut de ligne est converti en une combinaison CR\-LF.  
  
 Toutefois, lorsqu'une fonction E\/S de flux Unicode s'exécute en mode binaire, on suppose que le fichier est au format Unicode, et aucune conversion de traduction en caractère ou en CR\-LF ne se produit lors de l'entrée ou la sortie.  Utilisez l'instruction \_setmode \(\_fileno\( stdin \), \_O\_BINARY\) ; afin d'utiliser correctement le wcin dans un fichier texte UNICODE.  
  
## Voir aussi  
 [Routines runtime par catégorie](../c-runtime-library/run-time-routines-by-category.md)   
 [Entrées et sorties](../c-runtime-library/input-and-output.md)