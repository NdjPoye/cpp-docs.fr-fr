---
title: "Sp&#233;cification d&#39;un fichier inline | Microsoft Docs"
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
  - "fichiers (C++), inline"
  - "fichiers inline (C++), spécifier NMAKE"
  - "programme NMAKE, fichiers inline"
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Sp&#233;cification d&#39;un fichier inline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifiez deux chevrons \(\<\<\) dans la commande où *filename* doit apparaître.  Les chevrons ne peuvent pas être une expansion macro.  
  
## Syntaxe  
  
```  
<<[filename]  
```  
  
## Notes  
 Lorsque la commande est exécutée, les chevrons sont remplacés par *filename*, s'il est défini, ou par un nom unique généré par NMAKE.  S'il est spécifié, *filename* doit suivre les chevrons sans espace ni tabulation.  L'utilisation d'un chemin d'accès est autorisée.  Les extensions ne sont ni requises ni supposées.  Si *filename* est spécifié, le fichier est créé dans le répertoire en cours ou spécifié, remplaçant ainsi tout fichier existant sous ce nom ; sinon, il est créé dans le répertoire TMP \(ou le répertoire en cours, si la variable d'environnement TMP n'est pas définie\).  Si un *filename* précédent est réutilisé, NMAKE remplace le fichier précédent.  
  
## Voir aussi  
 [Fichiers inline dans un makefile](../build/inline-files-in-a-makefile.md)