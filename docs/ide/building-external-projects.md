---
title: "G&#233;n&#233;ration de projets externes | Microsoft Docs"
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
  - "générations (C++), projets externes"
  - "projets externes"
  - "projets Makefile, projets externes"
  - "projets (C++), projets externes"
  - "projets Visual C++, projets externes"
ms.assetid: 650b7803-ea91-489d-bee3-8f3e990e223c
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# G&#233;n&#233;ration de projets externes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un projet externe est un projet Visual C\+\+ qui utilise un makefile ou d'autres fonctionnalités qui se situent en dehors de l'environnement de développement Visual C\+\+ \(qui sont étrangères ou extérieures à celui\-ci\).  
  
 Si vous disposez d'un projet externe \(un projet de makefile, par exemple\) que vous voulez générer dans l'environnement de développement Visual C\+\+, créez un makefile et spécifiez la sortie et la commande de génération de votre projet dans l'Assistant Application Makefile.  Pour plus d'informations, consultez [Création d'un projet Makefile](../ide/creating-a-makefile-project.md).  
  
 Notez que Visual C\+\+ n'offre plus la possibilité d'exporter un makefile pour le projet actif à partir de l'environnement de développement.  Utilisez [Commutateurs de la ligne de commande Devenv](../Topic/Devenv%20Command%20Line%20Switches.md) pour générer des projets Visual Studio à partir de la ligne de commande.  
  
## Voir aussi  
 [Génération de projets C\+\+ dans Visual Studio](../ide/building-cpp-projects-in-visual-studio.md)