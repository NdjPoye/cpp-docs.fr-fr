---
title: "Erreur des outils &#201;diteur de liens LNK1201 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "LNK1201"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1201"
ms.assetid: 64c3f496-a428-4b54-981e-faa82ef9c8a1
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1201
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

erreur lors de l'écriture dans la base de données 'NomFichier' du programme ; vérifiez l'espace disque, le chemin d'accès ou les privilèges  
  
 LINK n'a pas pu écrire dans la base de données du programme \(PDB\) du fichier de sortie.  
  
### Pour résoudre le problème en vérifiant les causes possibles suivantes  
  
1.  Le fichier est endommagé.  Supprimez le fichier PDB et recommencez l'édition de liens.  
  
2.  Pas assez d'espace disque pour écrire le fichier.  
  
3.  Le lecteur n'est pas disponible, peut\-être suite à un problème réseau.  
  
4.  Le débogueur est actif sur le programme dont vous tentez l'édition de liens.  
  
5.  Espace du tas insuffisant.  Pour plus d'informations, consultez [C1060](../../error-messages/compiler-errors-1/fatal-error-c1060.md).