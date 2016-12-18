---
title: "Versions release | Microsoft Docs"
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
  - "versions debug, convertir en version release"
  - "déboguer (C++), versions release"
  - "versions release"
ms.assetid: fa9a78fa-f4b5-4722-baf4-aec655c4ff0f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Versions release
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une version release utilise des optimisations.  Lorsque vous faites appel aux optimisations pour créer une version release, le compilateur ne produit pas d'informations de débogage symboliques.  L'absence d'informations de débogage symboliques et de code généré pour des appels TRACE et ASSERT signifie que la taille du fichier exécutable est réduite et que l'exécution de celui\-ci sera plus rapide.  
  
 Cette section contient des informations qui expliquent pourquoi et quand vous pouvez souhaiter passer d'une version debug à une version release.  Elle décrit également certains des problèmes que vous êtes susceptible de rencontrer en passant d'une version debug à une version release :  
  
-   [Création d'une version release](../../build/reference/how-to-create-a-release-build.md)  
  
-   [Problèmes courants lors de la création d'une version release](../../build/reference/common-problems-when-creating-a-release-build.md)  
  
-   [Résolution de problèmes liés à la version release](../../build/reference/fixing-release-build-problems.md)  
  
    -   [Examen des instructions ASSERT](../../build/reference/using-verify-instead-of-assert.md)  
  
    -   [Utilisation de la version debug pour vérifier les remplacements de mémoire](../../build/reference/using-the-debug-build-to-check-for-memory-overwrite.md)  
  
    -   [Débogage d'une version release](../../build/reference/how-to-debug-a-release-build.md)  
  
    -   [Vérification des remplacements de mémoire](../../build/reference/checking-for-memory-overwrites.md)  
  
## Voir aussi  
 [Génération de projets C\+\+ dans Visual Studio](../../ide/building-cpp-projects-in-visual-studio.md)   
 [Référence à la génération C\/C\+\+](../../build/reference/c-cpp-building-reference.md)