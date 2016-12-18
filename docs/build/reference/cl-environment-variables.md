---
title: "Variables d&#39;environnement CL | Microsoft Docs"
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
  - "cl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "compilateur cl.exe, variables d'environnement"
  - "variables d'environnement, CL (compilateur)"
  - "INCLUDE (variable d'environnement)"
  - "LIBPATH (variable d'environnement)"
ms.assetid: 2606585b-a681-42ee-986e-1c9a2da32108
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Variables d&#39;environnement CL
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'outil CL utilise les variables d'environnement suivantes :  
  
-   CL et \_CL\_, si elles sont définies.  L'outil CL ajoute les options et les arguments définis dans la variable d'environnement CL avant les arguments de ligne de commande, et il ajoute les options et les arguments définis dans \_CL\_, avant le traitement.  
  
-   INCLUDE, qui doit pointer vers le sous\-répertoire \\include de votre installation Visual C\+\+.  
  
-   LIBPATH, qui spécifie les répertoires où rechercher les fichiers de métadonnées référencés avec [\#using](../../preprocessor/hash-using-directive-cpp.md).  Consultez `#using` pour plus d'informations sur LIBPATH.  
  
 Vous pouvez définir la variable d'environnement CL ou \_CL\_ en utilisant la syntaxe suivante :  
  
```  
SET CL=[ [option] ... [file] ...] [/link link-opt ...]  
SET _CL_=[ [option] ... [file] ...] [/link link-opt ...]  
```  
  
 Pour plus d'informations sur les arguments pour les variables d'environnement CL et \_CL\_, consultez [Syntaxe de la ligne de commande du compilateur](../../build/reference/compiler-command-line-syntax.md).  
  
 Vous pouvez utiliser ces variables d'environnement pour définir les fichiers et options que vous utilisez le plus souvent, et utiliser la ligne de commande afin de définir des fichiers et des options spécifiques pour des objectifs spécifiques.  Les variables d'environnement CL et \_CL\_ sont limitées à 1 024 caractères \(limite d'entrée sur la ligne de commande\).  
  
 Vous ne pouvez pas utiliser l'option \/D pour définir un symbole qui utilise un signe égal \(\=\).  Vous pouvez remplacer le signe égal par un signe dièse \(\#\).  De cette façon, vous pouvez utiliser les variables d'environnement CL ou \_CL\_ pour définir les constantes du préprocesseur avec des valeurs explicites : par exemple, `/DDEBUG#1` pour définir `DEBUG=1`.  
  
 Pour plus d'informations, consultez [Définir des variables d'environnement](../../build/setting-the-path-and-environment-variables-for-command-line-builds.md).  
  
## Exemples  
 Voici un exemple de définition de la variable d'environnement CL :  
  
```  
SET CL=/Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ  
```  
  
 Quand cette variable d'environnement est définie, si vous entrez `CL INPUT.C` sur la ligne de commande, la commande effective est :  
  
```  
CL /Zp2 /Ox /I\INCLUDE\MYINCLS \LIB\BINMODE.OBJ INPUT.C  
```  
  
 Dans l'exemple suivant, une commande CL simple compile les fichiers sources FILE1.c et FILE2.c, puis lie les fichiers objets FILE1.obj, FILE2.obj et FILE3.obj :  
  
```  
SET CL=FILE1.C FILE2.C  
SET _CL_=FILE3.OBJ  
CL  
  
```  
  
 Cela a le même effet que la ligne de commande suivante :  
  
```  
CL FILE1.C FILE2.C FILE3.OBJ  
```  
  
## Voir aussi  
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)