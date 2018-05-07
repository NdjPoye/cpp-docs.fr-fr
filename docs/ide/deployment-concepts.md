---
title: Concepts de déploiement | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows Installer [C++]
- dependencies [C++], application deployment and
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- libraries [C++], application deployment issues
ms.assetid: ebd7f246-ab54-40e8-87fa-dac02c0047b3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4fa40373e268c76caca17f3466573bc3e830757
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="deployment-concepts"></a>Concepts relatifs au déploiement
Cette section décrit les principales considérations pour déployer des applications C++.  
  
## <a name="windows-installer-deployment-in-c"></a>Déploiement de Windows Installer en C++  
 Projets Visual C++ utilisent en général, l’installation de Windows Installer traditionnelle pour le déploiement. Pour préparer un déploiement Windows Installer, vous empaquetez votre application dans un fichier setup.exe et distribuez ce fichier, ainsi que d’un package d’installation (.msi). Les utilisateurs ensuite exécuter setup.exe pour installer votre application.  
  
 Vous empaquetez votre application en ajoutant un projet d’installation à votre solution ; lors de la génération, il crée le programme d’installation et le programme d’installation des fichiers de package que vous distribuez aux utilisateurs. Pour plus d’informations, consultez [choix d’une méthode de déploiement](../ide/choosing-a-deployment-method.md).  
  
## <a name="library-dependencies"></a>Dépendances de bibliothèque  
 Lorsqu’une application C/C++ est générée à l’aide des fonctionnalités fournies par les bibliothèques Visual C++, elle devient dépendante de la présence de ces bibliothèques lors de l’exécution. Afin que l’application s’exécute, elle doit être liée, statiquement ou dynamiquement aux bibliothèques Visual C++ nécessaires. Si une application dynamiquement dans une bibliothèque Visual C++, puis lors de l’exécution que la bibliothèque de liens doivent être présents afin de pouvoir être chargé. En revanche, si l’application est statiquement liée à une bibliothèque Visual C++, puis il est inutile les DLL correspondants se trouvent sur l’ordinateur de l’utilisateur. La liaison statique, toutefois, a des effets négatifs, tels que l’augmentation de la taille des fichiers de l’application et potentiellement plus difficile d’assurer la maintenance. Pour plus d’informations, consultez [les avantages de l’utilisation des DLL](../build/dlls-in-visual-cpp.md#advantages-of-using-dlls).  
  
## <a name="packaging-and-redistributing"></a>Empaquetage et redistribution  
 Bibliothèques Visual C++ sont empaquetés en tant que DLL, et toutes les bibliothèques nécessaires pour les applications C/C++ sont installés par Visual Studio sur l’ordinateur du développeur. Toutefois, lorsque vous déployez votre application à vos utilisateurs, il n’est pas possible dans la plupart des cas pour leur demander d’installer Visual Studio pour exécuter votre application. Il est important de pouvoir redistribuer les éléments de Visual C++ qui sont requises par votre application pour s’exécuter correctement.  
  
 Pour plus d’informations sur l’empaquetage et la redistribution, consultez les rubriques suivantes :  
  
-   [Détermination des DLL à redistribuer](../ide/determining-which-dlls-to-redistribute.md).  
  
-   [Choix d’une méthode de déploiement](../ide/choosing-a-deployment-method.md).  
  
 Pour des exemples de déploiement et les suggestions de dépannage, consultez :  
  
-   [Exemples de déploiement](../ide/deployment-examples.md).  
  
-   [Résolution des problèmes de C/C++ d’Applications isolées et les assemblys côte à côte](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Déploiement d’Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Fonctionnement des dépendances d’une Application Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)   
 [Déploiement de Windows Installer](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)