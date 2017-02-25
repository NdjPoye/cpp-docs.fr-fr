---
title: "Cr&#233;ation du texte d&#39;un fichier inline | Microsoft Docs"
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
helpviewer_keywords: 
  - "fichiers inline, créer du texte"
  - "programme NMAKE, fichiers inline"
  - "texte, fichier inline"
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Cr&#233;ation du texte d&#39;un fichier inline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les fichiers inline peuvent être de type temporaire ou permanent.  
  
## Syntaxe  
  
```  
  
      inlinetext  
.  
.  
.  
<<[KEEP | NOKEEP]  
```  
  
## Notes  
 Spécifiez *inlinetext* sur la première ligne suivant la commande.  Marquez la fin par des doubles chevrons \(\<\<\) placés au début d'une ligne séparée.  Le fichier contient tout le *inlinetext* précédant les chevrons de délimitation.  Le *inlinetext* peut contenir des expansions et des substitutions macros, mais ni directives ni commentaires de makefile.  Les espaces, les tabulations et les caractères de saut de ligne reçoivent un traitement littéral.  
  
 Un fichier temporaire existe pendant la durée de la session et peut être réutilisé par d'autres commandes.  Spécifiez **KEEP** après les chevrons de fin pour conserver le fichier après la session NMAKE ; un fichier sans nom est conservé sur le disque avec le nom de fichier généré.  Spécifiez **NOKEEP** ou rien du tout pour un fichier temporaire.  **KEEP** et **NOKEEP** ne respectent pas la casse.  
  
## Voir aussi  
 [Fichiers inline dans un makefile](../build/inline-files-in-a-makefile.md)