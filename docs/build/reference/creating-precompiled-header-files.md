---
title: "Cr&#233;ation de fichiers d&#39;en-t&#234;te pr&#233;compil&#233;s | Microsoft Docs"
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
  - "pch"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fichiers .pch, créer"
  - "compilateur cl.exe, précompiler le code"
  - "fichiers PCH, créer"
  - "fichiers d'en-tête précompilés, créer"
ms.assetid: e2cdb404-a517-4189-9771-c869c660cb1b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Cr&#233;ation de fichiers d&#39;en-t&#234;te pr&#233;compil&#233;s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les compilateurs Microsoft C et C\+\+ offrent des options pour la précompilation du code en C ou C\+\+, y compris du code incorporé.  Compte tenu de cette possibilité, vous pouvez compiler un corps de code stable, stocker l'état compilé du code dans un fichier et, lors des compilations suivantes, combiner le code précompilé avec du code qui est encore en cours de développement.  Les compilations ultérieures sont plus rapides car le code stable n'a pas besoin d'être recompilé.  
  
 Cette section traite des sujets suivants relatifs aux en\-têtes précompilés :  
  
-   [Quand précompiler le code source](../../build/reference/when-to-precompile-source-code.md)  
  
-   [Deux méthodes au choix pour la précompilation du code](../../build/reference/two-choices-for-precompiling-code.md)  
  
-   [Règles de cohérence s'appliquant aux en\-têtes précompilés](../../build/reference/precompiled-header-consistency-rules.md)  
  
-   [Utilisation d'en\-têtes précompilés dans un projet](../../build/reference/using-precompiled-headers-in-a-project.md)  
  
 Pour obtenir des informations de référence sur les options de compilation relatives aux en\-têtes précompilés, consultez [\/Y \(En\-têtes précompilés\)](../../build/reference/y-precompiled-headers.md).  
  
## Voir aussi  
 [Référence à la génération C\/C\+\+](../../build/reference/c-cpp-building-reference.md)   
 [Options du compilateur](../../build/reference/compiler-options.md)