---
title: Préparation d’un ordinateur de Test pour exécuter un exécutable de débogage | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- debug executable, preparing a test machine to run
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33683ebe349fbfdcb3fd51179ed6bc3140510c00
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="preparing-a-test-machine-to-run-a-debug-executable"></a>Préparation d'un ordinateur de test pour lancer un exécutable de débogage
Pour préparer un ordinateur à tester la version debug d'une application développée en Visual C++, vous devez déployer les versions debug des DLL de la bibliothèque Visual C++ dont l'application dépend. Pour identifier les DLL doivent être déployées, suivez les étapes de [comprendre les dépendances d’une Application Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). En général, les versions debug des DLL de la bibliothèque Visual C++ ont un nom qui se termine par "d" ; par exemple, la version debug de msvcr100.dll se nomme msvcr100d.dll.  
  
> [!NOTE]
>  Les versions debug d'une application ne sont pas redistribuables, et les versions debug des DLL de la bibliothèque Visual C++ ne le sont pas non plus. Vous pouvez déployer les versions debug des applications et des DLL Visual C++ uniquement sur vos autres ordinateurs, dans le seul but de déboguer et de tester les applications sur un ordinateur où Visual Studio n'est pas installé. Pour plus d'informations, consultez [Redistributing Visual C++ Files](../ide/redistributing-visual-cpp-files.md).  
  
 Il existe trois façons de déployer les versions debug des DLL de la bibliothèque Visual C++ ainsi que la version debug d'une application :  
  
-   Utilisez le déploiement central pour installer une version debug d’une DLL Visual C++ particulière dans le répertoire %windir%\system32\ en utilisant un projet d’installation qui inclut des modules de fusion pour la version et l’architecture de bibliothèque appropriées de votre application. Les modules de fusion se trouvent dans le répertoire Program Files (x86) \Common Modules ou de Program Files\\. La version debug d’un module de fusion a un nom contenant le mot Debug, par exemple, Microsoft_VC110_DebugCRT_x86.msm. Un exemple de ce déploiement se trouve dans [procédure pas à pas : déploiement d’un Visual C++ Application à l’aide d’un projet d’installation](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
-   Utilisez le déploiement local pour installer une version debug d’une DLL Visual C++ particulière dans le répertoire d’installation de l’application à l’aide de fichiers qui sont fournis dans le répertoire Program Files (x86) \Microsoft Visual Studio ou de Program Files \<version > \VC\redist\Debug_NonRedist\\.  
  
    > [!NOTE]
    >  Pour le débogage distant de votre application développée en Visual C++ 2005 ou Visual C++ 2008 sur un autre ordinateur, vous devez déployer les versions debug des DLL de la bibliothèque Visual C++ en tant qu'assemblys côte à côte partagés. Vous pouvez utiliser un projet d’installation ou Windows Installer pour installer les modules de fusion correspondants.  
  
-   Utilisez l’option**déployer** option dans le **Configuration Manager** boîte de dialogue dans Visual Studio pour copier la sortie du projet et autres fichiers à l’ordinateur distant. 
  
 Après avoir installé les DLL Visual C++, vous pouvez exécuter un débogueur distant sur un partage réseau. Pour plus d’informations sur le débogage distant, consultez [débogage distant](/visualstudio/debugger/remote-debugging.md).  
  
## <a name="see-also"></a>Voir aussi  
 
 [Déploiement dans Visual C++](../ide/deployment-in-visual-cpp.md)   
 [Options de ligne de commande de Windows Installer](http://msdn.microsoft.com/library/windows/desktop/aa367988.aspx)   
 [Exemples de déploiement](../ide/deployment-examples.md) [le débogage distant](/visualstudio/debugger/remote-debugging.md)