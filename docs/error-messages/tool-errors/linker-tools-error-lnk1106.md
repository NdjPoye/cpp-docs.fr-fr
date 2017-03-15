---
title: "Erreur des outils &#201;diteur de liens LNK1106 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1106"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1106"
ms.assetid: 528f7e65-04be-4966-b8af-9276837c7cda
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur des outils &#201;diteur de liens LNK1106
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

fichier non valide ou disque plein : impossible de rechercher sur emplacement  
  
 L'outil n'a pas pu lire ou écrire à `location` dans un fichier transposé en mémoire.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Disque plein.  
  
     Libérez de l'espace disque avant de recommencer l'édition de liens.  
  
2.  Tentative d'édition de liens sur un réseau.  
  
     Certains réseaux ne prennent pas complètement en charge les fichiers transposés en mémoire utilisés par l'éditeur de liens.  Essayez de lancer l'éditeur de liens sur votre disque local.  
  
3.  Bloc défectueux sur votre disque.  
  
     Le système d'exploitation et le matériel du disque devraient avoir détecté une telle erreur, mais vous devriez peut\-être utiliser un programme de vérification de disque.  
  
4.  Espace du tas insuffisant.  
  
     Pour plus d'informations, consultez [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md).