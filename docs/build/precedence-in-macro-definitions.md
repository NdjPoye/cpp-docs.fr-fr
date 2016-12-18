---
title: "Priorit&#233; dans les d&#233;finitions de macros | Microsoft Docs"
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
  - "macros, priorité"
  - "programme NMAKE, priorité dans les définitions de macros"
ms.assetid: 0c13182d-83cb-4cbd-af2d-f4c916b62aeb
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Priorit&#233; dans les d&#233;finitions de macros
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si une macro possède plusieurs définitions, NMAKE utilise la définition ayant la plus haute priorité.  La liste suivante présente les définitions de macros par ordre de priorité décroissante :  
  
1.  Macro définie sur la ligne de commande  
  
2.  Macro définie dans un makefile ou Include  
  
3.  Macro héritée d'une variable d'environnement  
  
4.  Macro définie dans le fichier Tools.ini  
  
5.  Macro prédéfinie, telle que [CC](../build/command-macros-and-options-macros.md) et [AS](../build/command-macros-and-options-macros.md)  
  
 Utilisez l'option \/E pour que les macros héritées de variables d'environnement substituent les macros du makefile portant le même nom.  Utilisez **\!UNDEF** pour substituer une ligne de commande.  
  
## Voir aussi  
 [Définition d'une macro NMAKE](../build/defining-an-nmake-macro.md)