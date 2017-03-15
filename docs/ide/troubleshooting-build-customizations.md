---
title: "D&#233;pannage des personnalisations de g&#233;n&#233;ration | Microsoft Docs"
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
  - "événements de build (C++), dépanner"
  - "étapes de génération (C++), dépanner"
  - "générations (C++), événements de build"
  - "générations (C++), dépanner"
  - "étapes de génération personnalisée (C++), dépanner"
  - "événements (C++), build"
  - "dépanner (C++), builds"
ms.assetid: e4ceb177-fbee-4ed3-a7d7-80f0d78c1d07
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# D&#233;pannage des personnalisations de g&#233;n&#233;ration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vos étapes de build personnalisée ou événements de build ne se comportent pas comme prévu, il existe plusieurs choses que vous pouvez faire pour essayer de comprendre ce qui ne va pas.  
  
-   Assurez\-vous que les fichiers que vos étapes de build personnalisée génèrent correspondent aux fichiers que vous déclarez en tant que sorties.  
  
-   Si vos étapes de build personnalisée génèrent des fichiers qui sont des entrées ou des dépendances d'autres étapes de build \(personnalisée ou autre\), assurez\-vous que ces fichiers sont ajoutés à votre projet.  Assurez\-vous également que les outils qui consomment ces fichiers s'exécutent après l'étape de génération personnalisée.  
  
-   Pour afficher ce que fait réellement l'étape de génération personnalisée, ajoutez `@echo on` comme première commande.  Les événements et étapes de build sont placés dans un fichier .bat temporaire et exécutés lorsque le projet est généré.  Par conséquent, vous pouvez ajouter la vérification des erreurs à vos commandes d'événement de build ou d'étape de génération.  
  
-   Examinez le journal de génération dans le répertoire de fichiers intermédiaires pour voir ce qui a réellement été exécuté.  Le chemin d'accès et le nom du journal de génération sont représentés par l'expression de macro **MSBuild**, **$\(IntDir\)\\$\(MSBuildProjectName\).log**.  
  
-   Modifiez les paramètres de votre projet pour collecter davantage que la quantité d'informations par défaut du journal de génération.  Dans le menu **Outils**, cliquez sur **Options**.  Dans la boîte de dialogue **Options**, cliquez sur le nœud **Projets et solutions** puis sur le nœud **Générer et exécuter**.  Puis, dans la zone **Commentaires du fichier journal de génération du projet MSBuild**, cliquez sur **Détaillé**.  
  
-   Vérifiez les valeurs des macros de nom de fichier ou de répertoire que vous utilisez.  Vous pouvez répercuter des macros individuellement, ou vous pouvez ajouter `copy %0 command.bat` au début de votre étape de génération personnalisée, qui copiera les commandes de votre étape de génération personnalisée vers command.bat avec toutes les macros développées.  
  
-   Exécutez individuellement les étapes de build personnalisée et les événements de build pour vérifier leur comportement.  
  
## Voir aussi  
 [Présentation des étapes de génération personnalisée et des événements de build](../ide/understanding-custom-build-steps-and-build-events.md)