---
title: "Pr&#233;sentation des &#233;tapes de g&#233;n&#233;ration personnalis&#233;e et des &#233;v&#233;nements de build | Microsoft Docs"
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
  - "événements de build (C++), ordre des événements et étapes de génération"
  - "étapes de génération (C++)"
  - "étapes de génération (C++), événements de build"
  - "générations (C++), étapes de génération personnalisée"
  - "générations (C++), événements"
  - "étapes de génération personnalisée (C++)"
  - "étapes de génération personnalisée (C++), personnaliser les générations"
  - "événements (C++), build"
ms.assetid: beb2f017-3e9f-4b2c-9b57-2572fd2628e4
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Pr&#233;sentation des &#233;tapes de g&#233;n&#233;ration personnalis&#233;e et des &#233;v&#233;nements de build
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Au sein de l'environnement de développement de Visual C\+\+, il existe trois façons de personnaliser le processus de génération :  
  
 **Étapes de build personnalisée**  
 Une étape de génération personnalisée est une règle de génération associée à un projet.  L'étape de build personnalisée peut spécifier une ligne de commande à exécuter, n'importe quel fichier d'entrée ou de sortie supplémentaire et un message à afficher.  Pour plus d'informations, consultez [Comment : ajouter une étape de génération personnalisée à des projets MSBuild](../build/how-to-add-a-custom-build-step-to-msbuild-projects.md).  
  
 **Outils de génération personnalisée**  
 Un outil de génération personnalisée est une règle de génération associée à un ou plusieurs fichiers.  Une étape de génération personnalisée peut passer des fichiers d'entrée à un outil de génération personnalisée, qui se traduit par un ou plusieurs fichiers de sortie.  Par exemple, les fichiers d'aide dans une application MFC sont générés avec un outil de génération personnalisée.  Pour plus d’informations, consultez [Comment : ajouter des outils de génération personnalisée à des projets MSBuild](../build/how-to-add-custom-build-tools-to-msbuild-projects.md) et [Spécification des outils de génération personnalisée](../ide/specifying-custom-build-tools.md).  
  
 **Événements de build**  
 Les événements de build permettent de personnaliser la génération d'un projet.  Il existe trois événements de build : *pré\-build*, *avant l'édition des liens* et *post\-build*.  Un événement de build permet de spécifier une action qui doit survenir à un moment précis au cours du processus de génération.  Par exemple, vous pouvez utiliser un événement de build pour enregistrer un fichier avec **regsvr32.exe** une fois que le projet a fini la génération.  Pour plus d'informations, consultez [Spécification d'événements de build](../ide/specifying-build-events.md).  
  
 [Dépannage des personnalisations de génération](../ide/troubleshooting-build-customizations.md) peut vous aider à vérifier que vos étapes de génération et événements de build personnalisées sont exécutés comme attendu.  
  
 Le format de sortie d'une étape de build personnalisée ou d'un événement de build peut également améliorer l'accessibilité de l'outil.  Pour plus d'informations, consultez [Mise en forme de la sortie d'une étape de génération personnalisée ou d'un événement de build](../ide/formatting-the-output-of-a-custom-build-step-or-build-event.md).  
  
 Les événements de build et les étapes de build personnalisée s'exécutent dans l'ordre suivant, en même temps que d'autres étapes de build :  
  
1.  Événement pre\-build  
  
2.  Outils de génération personnalisée sur les fichiers individuels  
  
3.  MIDL  
  
4.  Compilateur de ressources  
  
5.  Compilateur C\/C\+\+  
  
6.  Événement avant l'édition des liens  
  
7.  Éditeur de liens ou générateur de bibliothèques \(selon le cas\)  
  
8.  Outil Manifeste  
  
9. BSCMake  
  
10. Étape de build personnalisée appliquée au projet  
  
11. Événement post\-build  
  
 `custom build step on the project` et `post-build event` s'exécutent en séquence à l'issue de tout autre processus de génération.  
  
## Voir aussi  
 [Génération de projets C\+\+ dans Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)   
 [Macros pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md)   
 [Tool Build Order Dialog Box](http://msdn.microsoft.com/fr-fr/6204c5b1-7ce9-4948-9ff6-0268642ee14c)