---
title: "Quand pr&#233;compiler le code source | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "fichiers d'en-tête précompilés, quand précompiler"
  - "code source, précompiler"
ms.assetid: eb8ba193-fd87-40d3-9545-c75deabe37cb
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Quand pr&#233;compiler le code source
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le code précompilé est utile pendant le cycle de développement car il permet de réduire le temps de compilation, notamment si :  
  
-   Vous utilisez toujours un corps de code volumineux qui change peu fréquemment.  
  
-   Votre programme comprend plusieurs modules, qui utilisent tous un jeu standard de fichiers include et les mêmes options de compilation.  Dans ce cas, tous les fichiers include peuvent être précompilés en un seul en\-tête précompilé.  
  
 La première compilation — celle qui crée le fichier d'en\-tête précompilé — prend un peu plus de temps que les compilations suivantes.  Les compilations ultérieures s'exécutent plus rapidement grâce au code précompilé inclus.  
  
 Vous pouvez précompiler des programmes à la fois en C et C\+\+.  En programmation C\+\+, il est courant de séparer les informations d'interface de classe en fichiers d'en\-tête.  Ces fichiers d'en\-tête sont par la suite inclus dans des programmes utilisant la classe.  En précompilant ces en\-têtes, vous pouvez réduire la durée de compilation d'un programme.  
  
> [!NOTE]
>  Même si vous êtes limité à un fichier d'en\-tête précompilé \(.pch\) par fichier source, vous pouvez utiliser plusieurs fichiers .pch dans un projet.  
  
## Voir aussi  
 [Création de fichiers d'en\-tête précompilés](../../build/reference/creating-precompiled-header-files.md)