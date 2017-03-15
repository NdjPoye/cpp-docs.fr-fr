---
title: "Concepts relatifs au d&#233;ploiement | Microsoft Docs"
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
  - "déploiement d'applications (C++), à propos du déploiement d'applications"
  - "dépendances (C++), déploiement d'applications et"
  - "déployer des applications (C++), à propos du déploiement des applications"
  - "bibliothèques (C++), problèmes de déploiement d'applications"
  - "Windows Installer (C++)"
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# Concepts relatifs au d&#233;ploiement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette section traite des principaux éléments à prendre en considération pour déployer des applications C\+\+.  
  
## Déploiement de Windows Installer en C\+\+  
 Les projets Visual C\+\+ utilisent en général l'installation traditionnelle par Windows Installer pour le déploiement.  Pour préparer un déploiement Windows Installer, vous empaquetez votre application dans un fichier setup.exe et distribuez ce fichier, ainsi qu'un package d'installation \(.msi\).  Les utilisateurs exécutent ensuite setup.exe pour installer votre application.  
  
 Vous empaquetez votre application en ajoutant un projet d'installation à votre solution ; une fois généré, celui\-ci crée les fichiers du package de configuration et d'installation que vous distribuez aux utilisateurs.  Pour plus d'informations, consultez [Choix d'une méthode de déploiement](../ide/choosing-a-deployment-method.md).  
  
## Dépendances des bibliothèques  
 Lorsqu'une application C\/C\+\+ est générée à l'aide des fonctionnalités offertes par les bibliothèques Visual C\+\+, elle devient dépendante de la présence de ces bibliothèques pendant l'exécution.  Pour que l'application s'exécute, elle doit être liée, statiquement ou dynamiquement, aux bibliothèques Visual C\+\+ appropriées.  Si une application est dynamiquement liée à une bibliothèque Visual C\+\+, la présence de cette dernière est nécessaire lors de l'exécution pour qu'elle puisse être chargée.  En revanche, si l'application est statiquement liée à une bibliothèque Visual C\+\+, il n'est pas nécessaire que les DLL correspondantes soient présentes sur l'ordinateur de l'utilisateur.  Toutefois, la liaison statique a des effets négatifs, par exemple l'augmentation de la taille des fichiers de l'application et la difficulté d'assurer la maintenance.  Pour plus d'informations, consultez [Avantages de l'utilisation des DLL](../build/advantages-of-using-dlls.md).  
  
## Empaquetage et redistribution  
 Les bibliothèques Visual C\+\+ sont empaquetées sous forme de DLL, et toutes les bibliothèques nécessaires pour les applications C\/C\+\+ sont installées par Visual Studio sur l'ordinateur du développeur.  Toutefois, lors du déploiement de votre application chez vos utilisateurs, il n'est généralement pas possible de leur demander d'installer Visual Studio pour exécuter votre application.  Il est important de pouvoir redistribuer les éléments de Visual C\+\+ requis par votre application pour qu'elle s'exécute correctement.  
  
 Pour plus d'informations sur l'empaquetage et la redistribution, consultez les rubriques suivantes :  
  
-   [Détermination des DLL à redistribuer](../ide/determining-which-dlls-to-redistribute.md).  
  
-   [Choix d'une méthode de déploiement](../ide/choosing-a-deployment-method.md).  
  
 Pour obtenir des exemples de déploiement et des suggestions de dépannage, consultez :  
  
-   [Exemples de déploiement](../ide/deployment-examples.md).  
  
-   [Dépannage](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
## Voir aussi  
 [Déploiement des applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Fonctionnement des dépendances d'une application Visual C\+\+](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)   
 [Windows Installer Deployment](http://msdn.microsoft.com/fr-fr/121be21b-b916-43e2-8f10-8b080516d2a0)