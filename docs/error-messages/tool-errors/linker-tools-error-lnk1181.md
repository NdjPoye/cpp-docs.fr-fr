---
title: "Erreur des outils &#201;diteur de liens LNK1181 | Microsoft Docs"
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
  - "LNK1181"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK1181"
ms.assetid: 984b0db6-e331-4284-b2a7-a212fe96c486
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK1181
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'ouvrir le fichier en entrée 'NomFichier'  
  
 L'éditeur de liens n'a pas pu trouver `filename` parce qu'il n'existe pas ou parce que le chemin d'accès n'a pas été trouvé.  
  
 Certaines causes courantes de l'erreur LNK1181 incluent :  
  
-   `filename` est référencé comme dépendance supplémentaire sur la ligne de l'éditeur de liens, mais le fichier n'existe pas.  
  
-   Une instruction **\/LIBPATH** qui spécifie le répertoire contenant `filename` est manquante.  
  
 Pour résoudre les problèmes ci\-dessus, assurez\-vous que tous les fichiers référencés sur la ligne de l'éditeur de liens soient présents sur le système.  Veillez aussi à ce qu'il y ait une instruction **\/LIBPATH** pour chaque répertoire qui contient un fichier dépendant de l'éditeur de liens.  
  
 L'erreur LNK1181 peut aussi être due au fait qu'un nom de fichier long avec espaces incorporés n'était pas entre guillemets.  Dans ce cas, l'éditeur de liens ne reconnaît un nom de fichier que jusqu'au premier espace, puis il suppose la présence de l'extension .obj.  La solution à cette situation est de mettre le long nom de fichier \(chemin d'accès plus nom de fichier\) entre guillemets.  
  
 Pour plus d'informations, consultez [Fichiers .lib en tant qu'entrée dans l'éditeur de liens](../../build/reference/dot-lib-files-as-linker-input.md).  
  
## Voir aussi  
 [\/LIBPATH \(Autre chemin de bibliothèque\)](../../build/reference/libpath-additional-libpath.md)