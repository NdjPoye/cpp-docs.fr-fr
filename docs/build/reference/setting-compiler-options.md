---
title: "D&#233;finition des options du compilateur | Microsoft Docs"
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
  - "compilateur cl.exe, définir des options"
  - "options du compilateur, définir"
ms.assetid: 4b079f5b-0017-4124-aad6-0d2b58e427e0
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;finition des options du compilateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les options de compilateur C et C\+\+peuvent être définies dans l'environnement de développement ou sur la ligne de commande.  
  
## Dans l'environnement de développement  
 Vous pouvez définir des options de compilateur pour chaque projet dans la boîte de dialogue **Pages de propriétés**.  Dans le volet gauche, sélectionnez **Propriétés de configuration**, **C\/C\+\+**, puis choisissez la catégorie de l'option de compilateur.  La rubrique relative à chaque option de compilateur explique comment définir cette dernière et où la trouver dans l'environnement de développement.  Pour obtenir une liste complète, consultez [Options du compilateur](../../build/reference/compiler-options.md).  
  
## En dehors de l'environnement de développement  
 Vous pouvez définir les options de compilateur \(CL.exe\) :  
  
-   [Sur la ligne de commande](../../build/reference/compiler-command-line-syntax.md)  
  
-   [Dans les fichiers de commandes](../../build/reference/cl-command-files.md)  
  
-   [Dans la variable d'environnement CL](../../build/reference/cl-environment-variables.md)  
  
 Les options spécifiées dans la variable d'environnement CL sont utilisées chaque fois qu'elle est appelée.  Si un fichier de commandes est nommé dans la variable d'environnement CL ou sur la ligne de commande, les options qu'il spécifie sont utilisées.  Contrairement à la ligne de commande ou à la variable d'environnement CL, un fichier de commandes vous permet d'utiliser plusieurs lignes d'options et de noms de fichiers.  
  
 Les options de compilateur sont traitées de « gauche à droite », et quand un conflit est détecté, la dernière option \(la plus à droite\) est celle qui prévaut.  La variable d'environnement CL est traitée avant la ligne de commande, de sorte qu'en cas de conflit entre CL et la ligne de commande, c'est cette dernière qui est prioritaire.  
  
## Rubriques supplémentaires relatives au compilateur  
  
-   [Compilation rapide](../../build/reference/fast-compilation.md)  
  
-   [CL appelle l'éditeur de liens](../../build/reference/cl-invokes-the-linker.md)  
  
## Voir aussi  
 [Référence à la génération C\/C\+\+](../../build/reference/c-cpp-building-reference.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)