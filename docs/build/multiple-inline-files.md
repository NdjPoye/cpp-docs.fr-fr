---
title: "Fichiers inline multiples | Microsoft Docs"
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
  - "fichiers inline, multiples (NMAKE)"
  - "fichiers inline multiples"
  - "programme NMAKE, fichiers inline"
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fichiers inline multiples
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une commande peut créer plusieurs fichiers inline.  
  
## Syntaxe  
  
```  
  
      command << <<  
inlinetext  
<<[KEEP | NOKEEP]  
inlinetext  
<<[KEEP | NOKEEP]  
```  
  
## Notes  
 Pour chaque fichier, définissez une ou plusieurs lignes de texte inline suivies par une ligne de fin contenant le délimiteur.  Commencez le texte du deuxième fichier sur la ligne suivant la ligne de délimitation du premier fichier.  
  
## Voir aussi  
 [Fichiers inline dans un makefile](../build/inline-files-in-a-makefile.md)