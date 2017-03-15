---
title: "Erreur des outils &#201;diteur de liens LNK1200 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1200"
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur des outils &#201;diteur de liens LNK1200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur lors de la lecture de la base de données 'NomFichier' du programme  
  
 La base de données du programme \(PDB\) n'a pas pu être lue.  
  
 Cette erreur est peut\-être due au fait que le fichier est endommagé.  
  
 Si `filename` est la PDB d'un fichier objet, recompilez le fichier objet avec [\/Zi](../../build/reference/z7-zi-zi-debug-information-format.md).  
  
 Si `filename` est la PDB du fichier de sortie principal, et si cette erreur est survenue lors d'une édition de liens incrémentielle, supprimez la PDB et recommencez l'édition de liens.