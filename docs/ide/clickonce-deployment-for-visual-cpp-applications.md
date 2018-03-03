---
title: "Déploiement ClickOnce pour les Applications Visual C++ | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++], ClickOnce
- application deployment [C++], ClickOnce
- ClickOnce deployment [C++], C++ applications
ms.assetid: 9988c546-0936-452c-932f-9c76daa42157
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e1a036a1520a747448c5541f367f0b43711e30b1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="clickonce-deployment-for-visual-c-applications"></a>Déploiement de ClickOnce pour les applications Visual C++
Visual Studio fournit deux technologies différentes pour déployer des applications Windows : le déploiement ClickOnce ou [Windows Installer](http://msdn.microsoft.com/library/cc185688) déploiement.  
  
## <a name="clickonce-deployment-in-c"></a>Déploiement ClickOnce en C++  
 L’environnement de développement Visual C++ ne prend pas directement en charge le déploiement de projets Visual C++ avec ClickOnce, mais les outils sont disponibles pour l’utiliser.  
  
> [!NOTE]
>  Visual Studio ne prend pas en charge ClickOnce dans les environnements de développement Visual c# et Visual Basic. Si votre projet Visual C++ est une dépendance d’un projet Visual c#, vous pouvez publier l’application (y compris ses dépendances) à l’aide du déploiement ClickOnce à partir de l’environnement de développement Visual c#.  
  
 Pour déployer une application Visual C++ à l’aide de ClickOnce, vous devez tout d’abord créer un [manifeste d’Application ClickOnce](/visualstudio/deployment/clickonce-application-manifest) et un [le manifeste de déploiement ClickOnce](/visualstudio/deployment/clickonce-deployment-manifest) à l’aide de la [Mage.exe (manifeste Outil Generation and Editing)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) ou sa version de l’interface utilisateur graphique (pour plus d’informations, consultez [MageUI.exe (Manifest Generation and Editing Tool, Graphical Client)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)).  

  
 Utilisez d’abord Mage.exe pour générer le manifeste d’application ; le fichier résultant portera l’extension .manifest. Utilisez ensuite Mage.exe pour générer le manifeste de déploiement ; le fichier résultant portera l’extension .application. Signez alors les manifestes.  
  
 Le manifeste d’application doit spécifier le processeur cible (**x86**, **x64**, ou **ARM**). Consultez [déploiement des composants requis pour les Applications 64 bits](/visualstudio/deployment/deploying-prerequisites-for-64-bit-applications) pour plus d’informations sur ces options.  
  
 Par ailleurs, les noms de l'application et des manifestes de déploiement doivent être différents du nom de l'application C++. Cela évite le conflit entre le manifeste d'application, créé par Mage.exe, et le manifeste externe, qui fait partie de l'application C++.  
  
 Votre déploiement devra installer les bibliothèques Visual C++ dont dépend votre application. Pour déterminer les dépendances d'une application particulière, vous pouvez utiliser depends.exe ou l'utilitaire DUMPBIN avec l'option /DEPENDENTS. Pour plus d’informations sur les dépendances, consultez [comprendre les dépendances d’une Application Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Vous devrez peut-être exécuter VCRedist.exe ; Cet utilitaire installe des bibliothèques Visual C++ sur l’ordinateur cible.  
  
 Vous devez également créer un programme d’amorçage (programme d’installation des composants requis) pour votre application à déployer les composants requis ; Pour plus d’informations sur le programme d’amorçage, consultez [création de Packages de programme d’amorçage](/visualstudio/deployment/creating-bootstrapper-packages).  
  
 Pour obtenir une description plus détaillée de la technologie, consultez [sécurité et déploiement ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment). Pour obtenir un exemple détaillé de déploiement ClickOnce, consultez [procédure pas à pas : déploiement manuel d’une Application ClickOnce](/visualstudio/deployment/walkthrough-manually-deploying-a-clickonce-application).  
  
## <a name="see-also"></a>Voir aussi  
 [Mage.exe (outil Manifest Generation and Editing)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool)   
 [MageUI.exe (outil Manifest Generation and Editing, client graphique)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)   
 [Makecert.exe (outil de la création du certificat)](https://msdn.microsoft.com/library/windows/desktop/aa386968)   
 [Déploiement d’Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Déploiement d’Applications, Services et composants](/visualstudio/deployment/deploying-applications-services-and-components)   
 [Déploiement de Windows Installer](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)   
 [Sécurité et déploiement ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)   
 [Création de Packages de programme d’amorçage](/visualstudio/deployment/creating-bootstrapper-packages)   
 [Programmation .NET avec c++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)   
 [Interopérabilité native et .NET](../dotnet/native-and-dotnet-interoperability.md)