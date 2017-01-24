---
title: "C++, d&#233;marrage et terminaison de programme | Microsoft Docs"
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
  - "contrôle (flux de texte)"
  - "fonction Main (procédures)"
  - "main (fonction), démarrage du programme"
  - "bibliothèque C++ standard, programme (démarrage et terminaison)"
  - "code de démarrage, et terminaison du programme (C++)"
  - "terminer l'exécution"
ms.assetid: f72c8f76-f507-4ddd-a270-7b60f4fed625
caps.latest.revision: 9
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# C++, d&#233;marrage et terminaison de programme
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le programme actuelle c \+\+ effectue les mêmes opérations que le programme en cours c effectué au démarrage du programme et l'arrêt du programme, ainsi que certains plus à tracer les grandes lignes ici.  
  
 Avant que l'environnement cible appelle la fonction `main`, et après qu'il enregistre toutes les valeurs initiales constantes que vous spécifiez dans tous les objets dont la durée statique, le programme exécute toutes autres constructeurs pour ces objets statiques.  L'ordre d'exécution n'est pas spécifiée entre les unités de traduction, mais vous pouvez néanmoins en supposant que certains objets d'[iostreams](../standard-library/iostreams-conventions.md) sont correctement initialisés destinée à ces constructeurs statiques.  Ces flux de texte du contrôle sont :  
  
-   [cin](../Topic/cin.md) — pour l'entrée standard.  
  
-   [cout](../Topic/cout.md) — pour la sortie standard.  
  
-   [cerr](../Topic/cerr.md) — pour la sortie d'erreur standard non tamponnée.  
  
-   [entrave](../Topic/clog.md) — pour la sortie d'erreur standard mise en mémoire tampon.  
  
 Vous pouvez également utiliser ces objets dans les destructeurs appelés des objets statiques, pendant l'arrêt du programme.  
  
 Comme avec l'Assistant De c, retour d'`main` ou appelant `exit` appelle les fonctions stockées avec `atexit` dans l'ordre inverse de Registre.  Une exception levée d'appels de fonction si `terminate`stockés.  
  
## Voir aussi  
 [Vue d'ensemble de la bibliothèque STL](../standard-library/cpp-standard-library-overview.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)