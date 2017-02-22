---
title: "ARM Assembler Directives | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# ARM Assembler Directives
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour l'essentiel, l'assembleur ARM Microsoft utilise le langage assembleur ARM, qui est décrite au chapitre 7 de la [guide des outils assembleur ARM](http://go.microsoft.com/fwlink/?LinkId=246102).  Toutefois, les implémentations Microsoft de certaines directives d'assemblage diffèrent les directives d'assemblage de ARM.  Cet article explique les différences.  
  
## Implémentations Microsoft de Directives d'assemblage de ARM  
 ZONE  
 L'assembleur ARM Microsoft prend en charge ces attributs de la zone : aligner, CODE, CODEALIGN, données, NOINIT, READONLY, READWRITE, THUMB, ARM.  
  
 Tous sauf le pouce et ARM fonctionnent comme indiqué dans le [guide des outils assembleur ARM](http://go.microsoft.com/fwlink/?LinkId=246102).  
  
 Dans l'assembleur Microsoft ARM, THUMB indique qu'une section de CODE contient du code Thumb et est la valeur par défaut pour les sections CODE.  ARM indique que la section contient du code ARM.  
  
 ATTR  
 Non pris en charge.  
  
 CODE16  
 Non pris en charge car il implique la syntaxe pre\-UEL Thumb, qui ne permet pas de l'assembleur ARM de Microsoft.  Utilisez à la place, la directive THUMB avec syntaxe UEL.  
  
 COMMUNE  
 Spécification d'un alignement pour la région commune n'est pas pris en charge.  
  
 DCDO  
 Non pris en charge.  
  
 DN, QN, SN  
 Spécification d'un type ou un couloir sur l'alias de Registre n'est pas pris en charge.  
  
 ENTRÉE  
 Non pris en charge.  
  
 EQU  
 Spécification d'un type pour le symbole défini n'est pas pris en charge.  
  
 EXPORTATION et GLOBAL  
 ```  
  
EXPORTsym {[type]}  
  
```  
  
 `sym`est le symbole à exporter.  `[type]`, si spécifié, il peut être soit `[DATA]` pour indiquer que le symbole pointant vers des données ou `[FUNC]` pour indiquer que le symbole pointe vers le code.  
  
 GLOBAL est un synonyme pour l'exportation.  
  
 EXPORTAS  
 Non pris en charge.  
  
 CADRE  
 Non pris en charge.  
  
 FONCTION et PROC  
 Bien que la syntaxe assembly prend en charge la spécification d'un personnalisé convention d'appel sur les procédures en répertoriant les registres sont appelant enregistrer et ceux qui sont appelé\-save, l'assembleur ARM Microsoft accepte la syntaxe, mais ignore les listes du Registre.  Les informations de débogage qui sont générées par l'assembleur prend en charge uniquement la valeur par défaut convention d'appel.  
  
 IMPORTATION et EXTERN  
 ```  
  
IMPORT sym{, WEAK alias{, TYPE t}}  
  
```  
  
 `sym`est le nom du symbole à importer.  
  
 Si faible `alias` est spécifié, il indique que `sym` est un externe faible.  Si aucune définition pour qu'il ne se trouve au moment de la liaison, puis lier à la place toutes les références qui lui `alias`.  
  
 Si TYPE  `t` est spécifié, puis `t` indique comment l'éditeur de liens doit tenter de résoudre `sym`.  Ces valeurs pour `t` sont possibles :   
1 — N'effectuent pas une recherche de la bibliothèque pour`sym`   
2: Effectuer une recherche de la bibliothèque de`sym`   
3 —`sym` est un alias de `alias` \(par défaut\)  
  
 EXTERN est un synonyme pour l'importation, sauf que `sym` est importé uniquement s'il existe des références à celui\-ci dans l'assembly actuel.  
  
 MACRO  
 L'utilisation d'une variable pour contenir le code condition de macro n'est pas pris en charge.  Valeurs par défaut pour les paramètres ne sont pas pris en charge des macros.  
  
 NOFP  
 Non pris en charge.  
  
 OPT, TTL, SUBT  
 Non pris en charge car l'assembleur ARM Microsoft ne produit pas d'annonces.  
  
 PRESERVE8  
 Non pris en charge.  
  
 RELOC  
 `RELOC n`peuvent suivre uniquement une instruction ou une directive de définition de données.  Il n'existe aucun « symbol anonyme » qui peut être relocalisée.  
  
 EXIGER  
 Non pris en charge.  
  
 REQUIRE8  
 Non pris en charge.  
  
 THUMBX  
 N'est pas pris en charge car l'assembleur ARM Microsoft ne gère pas le jeu d'instructions 2EE de pouce.  
  
## Voir aussi  
 [ARM Assembler Command\-Line Reference](../../assembler/arm/arm-assembler-command-line-reference.md)   
 [ARM Assembler Diagnostic Messages](../../assembler/arm/arm-assembler-diagnostic-messages.md)