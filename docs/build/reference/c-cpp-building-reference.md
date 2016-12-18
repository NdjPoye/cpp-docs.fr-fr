---
title: "R&#233;f&#233;rence &#224; la g&#233;n&#233;ration&#160;C/C++ | Microsoft Docs"
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
  - "générations (C++), informations supplémentaires"
  - "cl.exe (compilateur C++), générer des programmes"
  - "compiler le code source (C++), informations supplémentaires"
  - "éditeur de liens (C++), référence à la génération"
ms.assetid: 100b4ccf-572c-4d1f-970c-fa0bc0cc0d2d
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# R&#233;f&#233;rence &#224; la g&#233;n&#233;ration&#160;C/C++
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Visual C\+\+ offre deux méthodes de génération de programmes C\/C\+\+.  La méthode la plus simple, et la plus courante, consiste à [générer un programme dans l'environnement de développement Visual C\+\+](../../ide/building-cpp-projects-in-visual-studio.md).  L'autre méthode consiste à [générer un programme à partir d'une invite à l'aide d'outils en ligne de commande](../../build/building-on-the-command-line.md).  Dans les deux cas, vous pouvez créer des fichiers sources en utilisant l'éditeur de code source de Visual C\+\+ ou un éditeur tiers de votre choix.  
  
 Si votre programme utilise un makefile plutôt qu'un fichier .vcxproj, vous avez toujours la possibilité de le générer dans l'environnement de développement en tant que [projet externe](../../ide/building-external-projects.md).  
  
## Dans cette section  
 [Compilation d'un programme C\/C\+\+](../../build/reference/compiling-a-c-cpp-program.md)  
 Décrit le compilateur qui crée un fichier objet contenant le code machine, les directives de l'éditeur de liens, des sections, des références externes et les noms des fonctions\/données.  
  
 [Liaison](../../build/reference/linking.md)  
 Décrit l'éditeur de liens, qui combine le code issu des fichiers objets créés par le compilateur et celui qui est issu des bibliothèques statiques, résout les références aux noms de fichiers et crée un fichier exécutable.  
  
 [Versions release](../../build/reference/release-builds.md)  
 Présente des informations indiquant pourquoi et quand il convient de passer d'une version Debug à une version Release ; aborde également quelques\-uns des problèmes que vous pouvez rencontrer lors de ce passage.  
  
 [Optimisation du code](../../build/reference/optimizing-your-code.md)  
 Fournit des liens aux rubriques présentant les mécanismes d'optimisation du code :  
  
 [Outils de génération C\/C\+\+](../../build/reference/c-cpp-build-tools.md)  
 Fournit les outils en ligne de commande suivants pour l'affichage ou la manipulation de la sortie de la génération :  
  
 [Erreurs de build C\/C\+\+](../../error-messages/compiler-errors-1/c-cpp-build-errors.md)  
 Introduit la rubrique des erreurs de build dans la table des matières.  
  
## Rubriques connexes  
 [Référence du préprocesseur C\/C\+\+](../../preprocessor/c-cpp-preprocessor-reference.md)  
 Présente le préprocesseur, qui prépare les fichiers sources pour le compilateur en convertissant les macros, les opérateurs et les directives.  
  
 [Présentation des étapes de build personnalisée et des événements de build](../../ide/understanding-custom-build-steps-and-build-events.md)  
 Traite de la personnalisation du processus de génération.  
  
 [Génération d'un programme C\/C\+\+](../../build/building-c-cpp-programs.md)  
 Fournit des liens vers les rubriques décrivant la génération de votre programme depuis la ligne de commande ou depuis l'environnement de développement intégré de Visual Studio.  
  
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)  
 Décrit la définition des options du compilateur soit dans l'environnement de développement, soit sur la ligne de commande.  
  
 [Options du compilateur](../../build/reference/compiler-options.md)  
 Fournit des liens vers les rubriques décrivant l'utilisation des options de compilation.  
  
 [Définition des options de l'éditeur de liens](../../build/reference/setting-linker-options.md)  
 Décrit la définition des options de l'éditeur de liens à l'intérieur ou à l'extérieur de l'environnement de développement.  
  
 [Options de l'éditeur de liens](../../build/reference/linker-options.md)  
 Fournit des liens vers les rubriques décrivant l'utilisation des options de l'éditeur de liens.  
  
 [Référence de BSCMAKE](../../build/reference/bscmake-reference.md)  
 Décrit l'utilitaire de maintenance BSCMAKE.EXE \(Microsoft Browse Information Maintenance Utility\), qui génère un fichier d'informations de consultation \(.bsc\) à partir de fichiers .sbr créés lors de la compilation.  
  
 [Référence LIB](../../build/reference/lib-reference.md)  
 Décrit le gestionnaire de bibliothèques de Microsoft \(LIB.exe\), qui crée et gère une bibliothèque de fichiers objets COFF \(Common Object File Format\).  
  
 [Référence EDITBIN](../../build/reference/editbin-reference.md)  
 Décrit l'éditeur de fichiers binaires COFF de Microsoft \(EDITBIN.EXE\), qui modifie les fichiers binaires COFF \(Common Object File Format\).  
  
 [Référence DUMPBIN](../../build/reference/dumpbin-reference.md)  
 Décrit l'outil Microsoft COFF Binary File Dumper \(DUMPBIN.EXE\), qui affiche des informations sur les fichiers binaires COFF \(Common Object File Format\).  
  
 [Référence NMAKE](../../build/nmake-reference.md)  
 Décrit l'utilitaire Microsoft Program Maintenance \(NMAKE.EXE\), qui est un outil permettant de créer des projets en fonction des commandes contenues dans un fichier de description.