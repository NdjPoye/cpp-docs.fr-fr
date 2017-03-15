---
title: "Sortie LINK | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "link"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .ilk"
  - "DLL (C++), en tant que sortie de l'éditeur de liens"
  - "fichiers exécutables (C++), en tant que sortie de l'éditeur de liens"
  - "fichiers (C++), LINK"
  - "fichiers ILK"
  - "bibliothèques d'importation (C++), créer"
  - "LINK (outil C++), fichier de mappage"
  - "LINK (outil C++), sortie"
  - "éditeur de liens (C++), fichiers de sortie"
  - "fichiers de mappage (C++)"
  - "fichiers de mappage (C++), sortie LINK"
  - "fichiers de sortie (C++), éditeur de liens"
ms.assetid: a98b557c-1947-447a-be1f-616fb45a9580
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Sortie LINK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La sortie LINK inclut des fichiers .exe, des DLL, des fichiers de mappage et des messages.  
  
##  <a name="_core_output_files"></a> Fichiers de sortie  
 Le fichier de sortie par défaut issu de LINK est un fichier .exe.  Si l'option [\/DLL](../../build/reference/dll-build-a-dll.md) est spécifiée, LINK génère un fichier .dll.  Vous pouvez contrôler le nom du fichier de sortie à l'aide de l'option [\/OUT \(Nom du fichier de sortie\)](../../build/reference/out-output-file-name.md).  
  
 En mode incrémentiel, LINK crée un fichier .ilk pour stocker les informations d'état en vue des générations incrémentielles ultérieures du programme.  Pour plus d'informations sur les fichiers .ilk, consultez [Fichiers .ilk](../../build/reference/dot-ilk-files-as-linker-input.md).  Pour plus d'informations sur la liaison incrémentielle, consultez l'option [\/INCREMENTAL \(lier par incrément\)](../../build/reference/incremental-link-incrementally.md).  
  
 Quand LINK crée un programme contenant des exportations \(une DLL en général\), il génère également un fichier .lib, à moins qu'un fichier .exp n'ait été utilisé lors de la génération.  Vous pouvez contrôler le nom de fichier bibliothèque d'importation à l'aide de l'option [\/IMPLIB](../../build/reference/implib-name-import-library.md).  
  
 Si l'option [\/MAP \(générer fichier de mappage\)](../../build/reference/map-generate-mapfile.md) est spécifiée, LINK crée un fichier de mappage.  
  
 Si l'option [\/DEBUG \(Générer les informations de débogage\)](../../build/reference/debug-generate-debug-info.md) est spécifiée, LINK crée un fichier PDB pour contenir les informations de débogage du programme.  
  
##  <a name="_core_other_output"></a> Autre sortie  
 Lorsque vous tapez la commande `link` sans effectuer aucune autre entrée sur la ligne de commande, LINK affiche une instruction d'utilisation qui récapitule ses options.  
  
 LINK affiche un message de copyright et un numéro de version, et reproduit par écho l'entrée sur la ligne de commande jusqu'à ce que l'option [\/NOLOGO \(Supprimer la bannière de démarrage\)](../../build/reference/nologo-suppress-startup-banner-linker.md) soit utilisée.  
  
 Vous pouvez utiliser l'option [\/VERBOSE \(imprimer les messages d'avancement\)](../../build/reference/verbose-print-progress-messages.md) pour afficher des détails supplémentaires sur la génération.  
  
 LINK émet des messages d'erreur et des messages d'avertissement sous la forme LNK*nnnn*.  Ce préfixe d'erreur et la plage de numéros sont également utilisés par LIB, DUMPBIN et EDITBIN.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)