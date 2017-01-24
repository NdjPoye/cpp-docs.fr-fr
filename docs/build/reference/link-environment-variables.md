---
title: "Variables d&#39;environnement de LINK | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
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
  - "variables d'environnement (C++), LINK"
  - "LIB (variable d'environnement)"
  - "LINK (outil C++), variables d'environnement"
  - "variables, environnement"
ms.assetid: 9a3d3291-0cc4-4a7d-9d50-80e351b90708
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Variables d&#39;environnement de LINK
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'outil LINK utilise les variables d'environnement suivantes :  
  
-   LINK et \_LINK\_, si elles sont définies.  L'outil LINK ajoute les options et les arguments définis dans la variable d'environnement LINK, puis il ajoute les options et les arguments définis dans la variable d'environnement \_LINK\_ aux arguments de ligne de commande, avant le traitement.  
  
-   LIB, si elle est définie.  L'outil LINK utilise le chemin d'accès LIB quand vous recherchez un objet, une bibliothèque ou un autre fichier spécifié sur la ligne de commande ou par l'option [\/BASE](../../build/reference/base-base-address.md).  Il utilise également le chemin d'accès LIB pour rechercher un fichier .pdb nommé dans un objet.  La variable LIB peut contenir une ou plusieurs spécifications de chemin d'accès, séparées par des points\-virgules.  Un chemin d'accès doit pointer vers le sous\-répertoire \\lib de votre installation Visual C\+\+.  
  
-   PATH, si l'outil doit exécuter CVTRES et ne peut pas trouver le fichier dans le même répertoire que LINK.  \(LINK requiert CVTRES pour lier un fichier .res.\) PATH doit pointer vers le sous\-répertoire \\bin de votre installation Visual C\+\+.  
  
-   TMP, pour spécifier un répertoire lors de la liaison de fichiers OMF ou .res.  
  
## Voir aussi  
 [Définition des options de l'Éditeur de liens](../../build/reference/setting-linker-options.md)   
 [Options de l'Éditeur de liens](../../build/reference/linker-options.md)   
 [Définition du chemin d'accès et des variables d'environnement pour la génération à partir de la ligne de commande](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md)