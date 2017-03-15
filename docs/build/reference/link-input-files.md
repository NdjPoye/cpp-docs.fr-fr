---
title: "Fichiers d&#39;entr&#233;e LINK | Microsoft Docs"
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
  - "entrée de commande dans des fichiers de l'éditeur de liens (C++)"
  - "fichiers (C++), LINK"
  - "bibliothèques d'importation (C++), fichiers de l'éditeur de liens"
  - "fichiers d'entrée (C++), LINK"
  - "LINK (outil C++), fichiers d'entrée"
  - "éditeur de liens (C++), fichiers d'entrée"
  - "fichiers de définition de module"
  - "fichiers de définition de module, fichiers de l'éditeur de liens"
  - "ressources (C++), fichiers de l'éditeur de liens"
ms.assetid: bb26fcc5-509a-4620-bc3e-b6c6e603a412
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Fichiers d&#39;entr&#233;e LINK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vous fournissez à l'éditeur de liens des fichiers contenant des objets, des bibliothèques standard et des bibliothèques d'importation, des ressources, des définitions de module et des entrées de commande.  LINK n'utilise pas les extensions de fichier pour déterminer le contenu d'un fichier,  mais examine chaque fichier d'entrée pour en déduire la nature.  
  
 Les fichiers objets de la ligne de commande sont traités dans l'ordre où ils apparaissent sur celle\-ci.  Les bibliothèques également sont examinées dans l'ordre de la ligne de commande, avec la restriction suivante : les symboles qui ne sont pas résolus lors de l'importation d'un fichier objet à partir d'une bibliothèque sont examinés en premier dans cette bibliothèque, puis dans les bibliothèques suivantes à partir de la ligne de commande et des directives [\/DEFAULTLIB \(Spécifier la bibliothèque par défaut\)](../../build/reference/defaultlib-specify-default-library.md), et ensuite dans les bibliothèques éventuellement situées au début de la ligne de commande.  
  
> [!NOTE]
>  LINK n'accepte plus de point\-virgule \(ou tout autre caractère\) au début du commentaire des fichiers réponse et des fichiers d'ordres.  Les points\-virgules sont reconnus uniquement au début des commentaires des fichiers de définition de module \(.def\).  
  
 LINK utilise les types de fichiers d'entrée suivants :  
  
-   [fichiers .obj](../../build/reference/dot-obj-files-as-linker-input.md)  
  
-   [fichiers.netmodule](../../build/reference/netmodule-files-as-linker-input.md)  
  
-   [fichiers .lib](../../build/reference/dot-lib-files-as-linker-input.md)  
  
-   [fichiers .exp](../../build/reference/dot-exp-files-as-linker-input.md)  
  
-   [Fichiers .def](../../build/reference/dot-def-files-as-linker-input.md)  
  
-   [fichiers .pdb](../../build/reference/dot-pdb-files-as-linker-input.md)  
  
-   [fichiers .res](../../build/reference/dot-res-files-as-linker-input.md)  
  
-   [fichiers .exe](../../build/reference/dot-exe-files-as-linker-input.md)  
  
-   [fichiers .txt](../../build/reference/dot-txt-files-as-linker-input.md)  
  
-   [fichiers .ilk](../../build/reference/dot-ilk-files-as-linker-input.md)  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)