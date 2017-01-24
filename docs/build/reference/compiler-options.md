---
title: "Options du compilateur | Microsoft Docs"
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
  - "compilateur cl.exe"
  - "options du compilateur, C++"
  - "compilateur Visual C++ IPF"
  - "compilateur Itanium Visual C++"
  - "compilateur Visual C++ x64"
ms.assetid: ed3376c8-bef4-4c9a-80e9-3b5da232644c
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Options du compilateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

cl.exe est un outil qui contrôle les compilateurs et l'éditeur de liens Microsoft C et C\+\+. cl.exe peut être exécuté uniquement sur les systèmes d'exploitation qui prennent en charge Microsoft Visual Studio.  
  
> [!NOTE]
>  Vous pouvez démarrer cet outil uniquement à partir de l'invite de commandes [!INCLUDE[vsprvs](../../assembler/masm/includes/vsprvs_md.md)].  Vous ne pouvez pas le démarrer à partir d'une invite de commandes système ou dans l'Explorateur Windows.  
  
 Les compilateurs génèrent des fichiers objets \(.obj\) au format COFF \(Common Object File Format\).  L'éditeur de liens produit des fichiers exécutables \(.exe\) ou des bibliothèques de liens dynamiques \(DLL\).  
  
 Notez que toutes les options du compilateur respectent la casse.  
  
 Pour une compilation sans liaison, utilisez [\/c](../../build/reference/c-compile-without-linking.md).  
  
## Recherche d'une option  
 Pour trouver une option spécifique, recherchez\-la dans l'une des listes suivantes :  
  
-   [Options du compilateur classées par ordre alphabétique](../../build/reference/compiler-options-listed-alphabetically.md)  
  
-   [Options du compilateur classées par catégorie](../../build/reference/compiler-options-listed-by-category.md)  
  
## Spécification des options  
 La rubrique consacrée à chaque option du compilateur explique comment définir cette option dans l'environnement de développement.  Pour plus d'informations sur la spécification des options en dehors de l'environnement de développement, consultez :  
  
-   [Syntaxe de la ligne de commande du compilateur](../../build/reference/compiler-command-line-syntax.md)  
  
-   [Fichiers de commandes CL](../../build/reference/cl-command-files.md)  
  
-   [Variables d'environnement CL](../../build/reference/cl-environment-variables.md)  
  
## Outils de génération connexes  
 Utilisez [NMAKE](../../build/nmake-reference.md) pour générer le fichier de sortie.  
  
 Utilisez [BSCMAKE](../../build/reference/bscmake-reference.md) pour prendre en charge l'exploration des classes.  
  
 Les [options de l'éditeur de liens](../../build/reference/linker-options.md) affectent également la manière dont votre programme est généré.  
  
## Voir aussi  
 [Référence à la génération C\/C\+\+](../../build/reference/c-cpp-building-reference.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Compilation rapide](../../build/reference/fast-compilation.md)   
 [CL appelle l'Éditeur de liens](../../build/reference/cl-invokes-the-linker.md)