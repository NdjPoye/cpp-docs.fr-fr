---
title: "Fichiers .pdb en tant qu&#39;entr&#233;e dans l&#39;&#233;diteur de liens | Microsoft Docs"
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
  - "fichiers .pdb, en tant qu'entrée dans l'éditeur de liens"
  - "fichiers PDB, en tant qu'entrée dans l'éditeur de liens"
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Fichiers .pdb en tant qu&#39;entr&#233;e dans l&#39;&#233;diteur de liens
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les fichiers objets \(.obj\) compilés à l'aide de l'option \/Zi contiennent le nom d'une base de données du programme \(PDB\).  Vous ne spécifiez pas le nom du fichier PDB de l'objet à l'éditeur de liens ; LINK utilise le nom incorporé pour trouver le fichier PDB, si nécessaire.  Cela s'applique également aux objets débogables contenus dans une bibliothèque ; le fichier PDB d'une bibliothèque débogable doit être mis à la disposition de l'éditeur de liens, parallèlement à la bibliothèque.  
  
 LINK utilise également un fichier PDB pour stocker les informations de débogage du fichier .exe ou .dll.  Le PDB du programme est à la fois un fichier d'entrée ou de sortie, car LINK met à jour le PDB lorsqu'il régénère le programme.  
  
## Voir aussi  
 [Fichiers d'entrée LINK](../../build/reference/link-input-files.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)