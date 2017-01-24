---
title: "D&#233;ploiement des applications de bureau natives (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
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
  - "déployer des applications [C++]"
  - "déploiement d’applications [C++]"
  - "Visual C++, déploiement d’applications"
  - "déploiement d’applications [C++], à propos du déploiement d’applications"
  - "applications, déploiement [C++] (à propos du déploiement d’applications)"
  - "distribuer les applications [C++]"
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
caps.latest.revision: 28
caps.handback.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# D&#233;ploiement des applications de bureau natives (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un déploiement est le processus par lequel vous distribuez une application ou un composant terminé pour l’installer sur d’autres ordinateurs. La planification du déploiement commence quand l’application est créée sur l’ordinateur d’un développeur. Un déploiement se termine quand l’application est installée et prête à être exécutée sur l’ordinateur d’un utilisateur.  
  
 Visual Studio fournit différentes technologies pour déployer des applications Windows. Celles\-ci incluent le déploiement [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] et le déploiement Windows Installer.  
  
-   [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] peut être utilisé pour déployer des applications C\+\+ qui ciblent le CLR \(Common Language Runtime\) : des assemblys mixtes, purs et vérifiables. Bien que vous puissiez utiliser Windows Installer pour déployer une application managée, nous vous recommandons d’utiliser [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)], car il tire parti des fonctionnalités de sécurité du .NET Framework, comme la signature de manifeste.[!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] ne prend pas en charge le déploiement d’applications C\+\+ natives. Pour plus d’informations, consultez [Déploiement de ClickOnce pour les applications Visual C\+\+](../ide/clickonce-deployment-for-visual-cpp-applications.md).  
  
-   La technologie Windows Installer peut être utilisée pour déployer des applications C\+\+ natives ou des applications C\+\+ qui ciblent le CLR.  
  
 Les articles de cette section de la documentation expliquent comment vous assurer qu’une application Visual C\+\+ native s’exécute sur tout ordinateur qui fournit une plateforme cible prise en charge, quels fichiers vous devez inclure dans un package d’installation et les méthodes recommandées pour redistribuer les composants dont votre application dépend.  
  
## Dans cette section  
 [Déploiement dans Visual C\+\+](../ide/deployment-in-visual-cpp.md)  
  
 [Concepts relatifs au déploiement](../ide/deployment-concepts.md)  
  
 [Fonctionnement des dépendances d'une application Visual C\+\+](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)  
  
 [Détermination des DLL à redistribuer](../ide/determining-which-dlls-to-redistribute.md)  
  
 [Choix d'une méthode de déploiement](../ide/choosing-a-deployment-method.md)  
  
 [Redistribution des fichiers Visual C\+\+](../ide/redistributing-visual-cpp-files.md)  
  
 [Exemples de déploiement](../ide/deployment-examples.md)  
  
 [Redistribution d'applications clientes Web](../ide/redistributing-web-client-applications.md)  
  
 [Déploiement de ClickOnce pour les applications Visual C\+\+](../ide/clickonce-deployment-for-visual-cpp-applications.md)  
  
 [Exécution d'une application C\+\+ \/clr sur une version antérieure du runtime](../ide/running-a-cpp-clr-application-on-a-previous-runtime-version.md)  
  
## Rubriques connexes  
 [Génération d'applications isolées C\/C\+\+ et d'assemblys côte à côte](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)  
  
 [déploiement](../Topic/Deploying%20the%20.NET%20Framework%20and%20Applications.md)  
  
 [Dépannage](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)