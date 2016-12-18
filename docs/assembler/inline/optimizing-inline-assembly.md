---
title: "Optimisation de l&#39;assembly inline | Microsoft Docs"
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
  - "__asm (mot clé) (C++), optimiser"
  - "assembleur inline, optimiser"
  - "optimisation, assembleur inline"
  - "optimiser les performances, assembleur inline"
  - "stockage, optimiser dans l'assembleur inline"
ms.assetid: 52a7ec83-9782-4d96-94c1-53bb2ac9e8c8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Optimisation de l&#39;assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 La présence d'un bloc `__asm` dans une fonction affecte l'optimisation de plusieurs façons.  D'abord, le compilateur ne tente pas d'optimiser le bloc `__asm` lui\-même.  Ce que vous écrivez dans le langage assembleur est exactement ce que vous obtenez.  Ensuite, la présence d'un bloc `__asm` affecte le stockage des variables du registre.  Le compilateur évite d'enregistrer les variables dans un bloc `__asm` si le contenu du registre est modifié par le bloc `__asm`.  Enfin, certaines optimisations au niveau de la fonction seront affectées par l'inclusion du langage assembleur dans une fonction.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Assembleur inline](../../assembler/inline/inline-assembler.md)