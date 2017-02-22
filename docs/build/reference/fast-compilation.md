---
title: "Compilation rapide | Microsoft Docs"
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
  - "compilateur cl.exe, performances"
  - "compilation, performances"
  - "compilation rapide"
  - "performances, cle.exe (compilateur)"
ms.assetid: 5fead136-ba69-40c8-8e25-236f89d5990a
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Compilation rapide
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour accélérer l'exécution des compilations :  
  
-   Utilisez une [régénération minimale](../../build/reference/gm-enable-minimal-rebuild.md), dans laquelle le compilateur C\+\+ recompile un fichier source uniquement s'il dépend des modifications apportées à une classe dans un fichier d'en\-tête.  
  
-   [Créez des fichiers précompilés et d'en\-tête](../../build/reference/creating-precompiled-header-files.md) et utilisez les [options d'en\-tête précompilées](../../build/reference/yc-create-precompiled-header-file.md).  
  
## Voir aussi  
 [Options du compilateur](../../build/reference/compiler-options.md)   
 [Définition des options du compilateur](../../build/reference/setting-compiler-options.md)