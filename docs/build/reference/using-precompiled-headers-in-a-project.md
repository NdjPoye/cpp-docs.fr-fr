---
title: "Utilisation d&#39;en-t&#234;tes pr&#233;compil&#233;s dans un projet | Microsoft Docs"
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
  - "en-têtes précompilés"
ms.assetid: 95010260-a035-4327-9d61-222016ac146c
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Utilisation d&#39;en-t&#234;tes pr&#233;compil&#233;s dans un projet
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les sections précédentes donnent une vue d'ensemble des en\-têtes précompilés : \/Yc et \/Yu, l'option \/Fp ainsi que le pragma [hdrstop](../../preprocessor/hdrstop.md).  Cette section décrit une méthode d'utilisation manuelle des options d'en\-tête précompilé dans un projet ; elle se termine par un exemple de makefile et de code qu'il manage.  
  
 Pour une autre approche en matière d'utilisation manuelle des options d'en\-tête précompilé dans un projet, étudiez l'un des makefiles qui se trouvent dans le répertoire MFC\\SRC créé lors de l'installation par défaut de Visual C\+\+.  Ces makefiles adoptent une approche similaire à celle qui est présentée dans cette section, mais font davantage appel aux macros NMAKE \(Microsoft Program Maintenance Utility\) et permettent un meilleur contrôle du processus de génération.  
  
 Cette section contient les rubriques suivantes :  
  
-   [Fichiers PCH utilisés dans le processus de génération](../../build/reference/pch-files-in-the-build-process.md)  
  
-   [Exemple de makefile pour PCH](../../build/reference/sample-makefile-for-pch.md)  
  
-   [Exemple de code pour PCH](../../build/reference/example-code-for-pch.md)  
  
## Voir aussi  
 [Création de fichiers d'en\-tête précompilés](../../build/reference/creating-precompiled-header-files.md)