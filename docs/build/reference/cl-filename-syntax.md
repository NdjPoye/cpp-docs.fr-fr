---
title: "Syntaxe de nom de fichier&#160;CL | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, syntaxe du nom de fichier"
  - "extensions, spécifier au compilateur"
  - "noms de fichiers (C++)"
  - "noms de fichiers (C++), CL (compilateur)"
  - "chemins d'accès, syntaxe de nom de fichier du compilateur CL"
  - "syntaxe, nom de fichier du compilateur"
ms.assetid: 3ca72586-75be-4477-b323-a1be232e80d4
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Syntaxe de nom de fichier&#160;CL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

CL accepte les fichiers dont les noms respectent les conventions d'affectation de noms FAT, HPFS ou NTFS.  Un nom de fichier peut inclure un chemin d'accès complet ou partiel.  Un chemin d'accès complet comprend un nom de lecteur et un ou plusieurs noms de répertoire.  CL accepte les noms de fichiers séparés par des barres obliques inverses \(\\\) ou des barres obliques standard \(\/\).  Les noms de fichiers qui contiennent des espaces doivent être mis entre guillemets doubles.  Un chemin d'accès partiel omet le nom de lecteur, CL considérant qu'il s'agit du lecteur actif.  Si vous ne spécifiez pas de chemin d'accès, CL considère que le fichier se trouve dans le répertoire actif.  
  
 L'extension de nom de fichier détermine la façon dont les fichiers sont traités.  Les fichiers C et C\+\+, qui ont l'extension .c, .cxx ou .cpp, sont compilés.  Les autres fichiers, notamment les fichiers .obj, les bibliothèques \(.lib\) et les fichiers de définition de module \(.def\), sont passés à l'éditeur de liens sans avoir été traités.  
  
## Voir aussi  
 [Syntaxe de la ligne de commande du compilateur](../../build/reference/compiler-command-line-syntax.md)