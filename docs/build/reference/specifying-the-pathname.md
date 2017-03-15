---
title: "Sp&#233;cification du nom de chemin | Microsoft Docs"
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
  - "compilateur cl.exe, fichiers de sortie"
  - "noms (C++), fichiers de sortie du compilateur"
  - "fichiers de sortie, spécifier des noms de chemins"
ms.assetid: 7a6595ce-3383-44ae-957a-466bfa29c343
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Sp&#233;cification du nom de chemin
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Chaque option du fichier de sortie accepte un argument *pathname* pouvant spécifier un emplacement et un nom pour le fichier de sortie.  L'argument peut inclure un nom de lecteur, un répertoire et un nom de fichier.  Aucun espace n'est admis entre l'option et l'argument.  
  
 Si *pathname* comprend un nom de fichier sans extension, le compilateur attribue une extension par défaut à la sortie.  Si *pathname* inclut un répertoire, mais pas de nom de fichier, le compilateur crée un fichier avec un nom par défaut dans le répertoire spécifié.  Le nom par défaut repose sur le nom de base du fichier source et une extension par défaut basée sur le type du fichier de sortie.  Si vous omettez complètement l'argument *pathname*, le compilateur crée un fichier avec un nom par défaut dans un répertoire par défaut.  
  
 L'argument *pathname* peut aussi spécifier un nom de périphérique \(AUX, CON, PRN ou NUL\) au lieu d'un nom de fichier.  N'ajoutez pas d'espace entre l'option et le nom de périphérique ni le signe deux\-points dans le nom de périphérique.  
  
|Nom de périphérique|Représente|  
|-------------------------|----------------|  
|AUX|Périphérique auxiliaire|  
|CON|Console|  
|PRN|Imprimante|  
|NUL|Périphérique null \(aucun fichier créé\)|  
  
## Exemple  
 La ligne de commande suivante envoie un fichier de mappage à l'imprimante :  
  
```  
CL /FmPRN HELLO.CPP  
```  
  
## Voir aussi  
 [Options du fichier de sortie \(\/F\)](../../build/reference/output-file-f-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)