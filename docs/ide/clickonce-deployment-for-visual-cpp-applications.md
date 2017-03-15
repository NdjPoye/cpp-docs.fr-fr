---
title: "D&#233;ploiement de ClickOnce pour les applications Visual C++ | Microsoft Docs"
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
  - "déploiement d’applications [C++], ClickOnce"
  - "application, déploiement [C++], ClickOnce"
  - "ClickOnce, déploiement [C++], applications C++"
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;ploiement de ClickOnce pour les applications Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] proposent deux technologies différentes pour déployer les applications Windows : le déploiement ClickOnce ou le déploiement [Windows Installer](http://msdn.microsoft.com/library/cc185688).  
  
## Déploiement ClickOnce en C\+\+  
 L'environnement de développement de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ne prend pas directement en charge le déploiement de projets [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] avec [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)], mais les outils pour l'utiliser sont disponibles.  
  
> [!NOTE]
>  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] prend en charge [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] dans les environnements de développement [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)] et [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)].  Si votre projet [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] est une dépendance d'un projet [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)], vous pouvez publier l'application \(y compris ses dépendances\) à l'aide du déploiement [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)] à partir de l'environnement de développement [!INCLUDE[csprcs](../ide/includes/csprcs_md.md)].  
  
 Pour déployer une application [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] à l'aide de [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)], vous devez tout d'abord générer un [ClickOnce Application Manifest](../Topic/ClickOnce%20Application%20Manifest.md) et un [ClickOnce Deployment Manifest](../Topic/ClickOnce%20Deployment%20Manifest.md) à l'aide de [Mage.exe \(outil Manifest Generation and Editing\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md) ou de sa version avec interface utilisateur graphique \(pour plus d'informations, consultez [MageUI.exe \(Manifest Generation and Editing Tool, Graphical Client\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)\).  
  
 Utilisez d'abord Mage.exe pour générer le manifeste d'application ; le fichier résultant portera l'extension .manifest.  Utilisez ensuite Mage.exe pour générer le manifeste de déploiement ; le fichier résultant portera l'extension .application.  Signez alors les manifestes.  
  
 Le manifeste d'application doit spécifier le processeur cible \(**x86**, **x64** ou **ARM**\).  Consultez [Composants requis pour le déploiement d'applications 64 bits](../Topic/Deploying%20Prerequisites%20for%2064-bit%20Applications.md) pour plus d'informations sur ces options.  
  
 Par ailleurs, les noms de l'application et des manifestes de déploiement doivent être différents du nom de l'application C\+\+.  Cela évite le conflit entre le manifeste d'application, créé par Mage.exe, et le manifeste externe, qui fait partie de l'application C\+\+.  
  
 Votre déploiement devra installer les bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] dont votre application dépend.  Pour déterminer les dépendances d'une application particulière, vous pouvez utiliser depends.exe ou l'utilitaire DUMPBIN avec l'option \/DEPENDENTS.  Pour plus d'informations sur les dépendances, consultez [Fonctionnement des dépendances d'une application Visual C\+\+](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md).  Vous aurez peut\-être besoin d'exécuter VCRedist.exe ; cet utilitaire installe des bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] sur l'ordinateur cible.  
  
 Vous devrez peut\-être également générer un programme d'amorçage \(programme d'installation de composants requis\) de votre application pour déployer des composants requis ; pour plus d'informations sur le programme d'amorçage, consultez [Création de packages de programme d'amorçage](../Topic/Creating%20Bootstrapper%20Packages.md).  
  
 Pour une description détaillée de la technologie, consultez [ClickOnce Security and Deployment](../Topic/ClickOnce%20Security%20and%20Deployment.md).  Pour un exemple détaillé de déploiement [!INCLUDE[ndptecclick](../ide/includes/ndptecclick_md.md)], consultez [Walkthrough: Manually Deploying a ClickOnce Application](../Topic/Walkthrough:%20Manually%20Deploying%20a%20ClickOnce%20Application.md).  
  
## Voir aussi  
 [Mage.exe \(outil Manifest Generation and Editing\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md)   
 [MageUI.exe \(Manifest Generation and Editing Tool, Graphical Client\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)   
 [Makecert.exe \(Certificate Creation Tool\)](../Topic/Makecert.exe%20\(Certificate%20Creation%20Tool\).md)   
 [Déploiement des applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Déploiement d'applications, de services et de composants](../Topic/Deploying%20Applications,%20Services,%20and%20Components.md)   
 [Windows Installer Deployment](http://msdn.microsoft.com/fr-fr/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [ClickOnce Security and Deployment](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [Création de packages de programme d'amorçage](../Topic/Creating%20Bootstrapper%20Packages.md)   
 [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md)