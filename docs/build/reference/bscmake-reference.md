---
title: "R&#233;f&#233;rence BSCMAKE | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "fichiers .bsc, générer"
  - "fichiers d'informations de consultation (.bsc), générer"
  - "fenêtres de consultation"
  - "fichiers bsc, générer"
  - "BSCMAKE"
  - "BSCMAKE, référence"
  - "Microsoft Browse Information Maintenance Utility"
ms.assetid: b97ad994-1355-4809-98db-6abc12c6fb13
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# R&#233;f&#233;rence BSCMAKE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

> [!WARNING]
>  Bien que BSCMAKE soit toujours installé avec Visual Studio, il n'est plus utilisé par l'environnement IDE.  Depuis Visual Studio 2008, les informations de consultation et de symbole sont stockées automatiquement dans un fichier SQL Server .sdf, dans le dossier de solution.  
  
 Microsoft Browse Information Maintenance Utility \(BSCMAKE.EXE\) génère un fichier d'informations de consultation \(.bsc\) à partir des fichiers .sbr créés lors de la compilation.  Vous affichez un fichier d'informations de consultation dans l'Explorateur d'objets.  Pour plus d'informations sur l'Explorateur d'objets, consultez [Naviguer dans l'Explorateur d'objets](http://msdn.microsoft.com/fr-fr/53eb91aa-08c6-4299-8e3c-a877ae8d0c55).  
  
 Quand vous générez votre programme, vous pouvez créer automatiquement un fichier d'informations de consultation pour votre programme en utilisant BSCMAKE pour générer le fichier.  Vous n'avez pas besoin de savoir comment exécuter BSCMAKE si vous créez votre fichier d'informations de consultation dans l'environnement de développement Visual C\+\+.  Toutefois, vous pouvez lire cette rubrique pour comprendre les choix disponibles.  
  
 Si vous générez votre programme en dehors de l'environnement de développement, vous pouvez encore créer un fichier .bsc personnalisé que vous pouvez examiner dans l'environnement.  Exécutez BSCMAKE sur les fichiers .sbr que vous avez créés lors de la compilation.  
  
> [!NOTE]
>  Vous pouvez démarrer cet outil uniquement à partir de l'invite de commandes [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  Vous ne pouvez pas le démarrer à partir d'une invite de commandes système ni de l'Explorateur de fichiers.  
  
 Cette section comprend les rubriques suivantes :  
  
-   [Génération de fichiers d'informations de consultation : vue d'ensemble](../../build/reference/building-browse-information-files-overview.md)  
  
-   [Génération d'un fichier .bsc](../../build/reference/building-a-dot-bsc-file.md)  
  
-   [Ligne de commande BSCMAKE](../../build/reference/bscmake-command-line.md)  
  
-   [Fichier de commandes BSCMAKE](../../build/reference/bscmake-command-file-response-file.md)  
  
-   [Options BSCMAKE](../../build/reference/bscmake-options.md)  
  
-   [Codes de sortie BSCMAKE](../../build/reference/bscmake-exit-codes.md)  
  
## Voir aussi  
 [Outils de génération C\/C\+\+](../../build/reference/c-cpp-build-tools.md)