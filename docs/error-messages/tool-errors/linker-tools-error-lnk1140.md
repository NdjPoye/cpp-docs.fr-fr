---
title: "Erreur des outils &#201;diteur de liens LNK1140 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1140"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1140"
ms.assetid: 468d7651-a7cd-47b9-aead-5bb2fab56121
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur des outils &#201;diteur de liens LNK1140
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

trop de modules pour la base de données du programme ; reliez avec \/PDB:NONE  
  
 Le projet contient plus de 4096 modules.  
  
### Pour résoudre le problème en utilisant les solutions possibles suivantes  
  
1.  Recommencez l'édition en lien en utilisant [\/PDB:NONE](../../build/reference/pdb-use-program-database.md).  
  
2.  Compilez certains modules sans informations de débogage.  
  
3.  Réduisez le nombre de modules.