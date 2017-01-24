---
title: "R&#233;sum&#233; des d&#233;finitions de grammaire | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "préprocesseur"
  - "préprocesseur, définitions"
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# R&#233;sum&#233; des d&#233;finitions de grammaire
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les éléments terminaux sont des points de terminaison dans une définition de syntaxe.  Aucune autre résolution n'est possible.  Les terminaux incluent l'ensemble des mots réservés et des identificateurs définis par l'utilisateur.  
  
 Les éléments non terminaux sont des espaces réservés dans la syntaxe.  La plupart de ces éléments sont définis ailleurs dans ce résumé de syntaxe.  Les définitions peuvent être récursives.  Les éléments non terminaux suivants sont définis dans la section [Résumé de la grammaire](../misc/grammar-summary-cpp.md) du *Guide de référence du langage C\+\+* :  
  
 `constant`, *constant\-expression*, *identifier*, *keyword*, `operator`, `punctuator`  
  
 Un composant facultatif est indiqué par l'élément opt indicé.  Par exemple, le code suivant indique une expression facultative entre accolades :  
  
 **{** *expression*opt **}**  
  
## Voir aussi  
 [Résumé de la grammaire](../preprocessor/grammar-summary-c-cpp.md)