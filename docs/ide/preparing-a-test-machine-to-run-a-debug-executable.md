---
title: "Pr&#233;paration d&#39;un ordinateur de test pour lancer un ex&#233;cutable de d&#233;bogage | Microsoft Docs"
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
  - "exécutable de débogage, préparer un ordinateur de test pour lancer un"
ms.assetid: f0400989-cc2e-4dce-9788-6bdbe91c6f5a
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Pr&#233;paration d&#39;un ordinateur de test pour lancer un ex&#233;cutable de d&#233;bogage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour préparer un ordinateur à tester la version debug d'une application développée en Visual C\+\+, vous devez déployer les versions debug des DLLs des bibliothèques Visual C\+\+ dont l'application dépend.  Pour identifier les DLLs à déployer, suivez les étapes présentées dans [Fonctionnement des dépendances d'une application Visual C\+\+](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md).  En général, les versions debug des DLL de bibliothèque Visual C\+\+ ont un nom qui se termine par « d » ; par exemple, la version debug de msvcr100.dll se nomme msvcr100d.dll.  
  
> [!NOTE]
>  Les versions debug d'une application ne sont pas redistribuables , et les versions debug des DLLs de la bibliothèques Visual C\+\+ ne le sont pas non plus.  Vous pouvez déployer les versions debug des applications et les DLL Visual C\+\+ uniquement à vos ordinateurs, dans le seul but du débogage et du test des applications sur un ordinateur qui ne dispose pas Visual Studio installée.  Pour plus d'informations, consultez [Redistribution des fichiers Visual C\+\+](../ide/redistributing-visual-cpp-files.md).  
  
 Il existe trois façons de déployer les versions debug des DLLs de la bibliothèques Visual C\+\+ en même temps que la version debug d'une application :  
  
-   Utilisez le déploiement central pour installer une version debug d'une DLL Visual C\+\+ particulière dans le répertoire %windir%\\system32\\ en utilisant un projet d'installation qui inclut les modules de fusion pour la bonnes version de bibliothèque et architecture de votre application.  Les modules de fusion sont trouvés dans Program Files ou Program Files \(x86\) répertoire\\Fichiers communs\\Modules de fusion\\.  La version Debug d'un module de fusion a le débogage dans l'exemple de namefor, Microsoft\_VC110\_DebugCRT\_x86.msm.  Un exemple de ce déploiement se trouve dans [Procédure pas à pas : déploiement d'une application Visual C\+\+ à l'aide d'un projet d'installation](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md).  
  
-   Utilisez le déploiement local pour installer une version debug d'une DLL Visual C\+\+ particulière dans le répertoire d'installation de l'application en utilisant des fichiers qui sont fournis dans le répertoire Program Files ou Program Files \(x86\) \\Microsoft Visual Studio \<version\>\\VC\\redist\\Debug\_NonRedist\\.  
  
    > [!NOTE]
    >  Pour le débogage distant de votre application générée à l'aide de Visual C\+\+ 2005 ou Visual C\+\+ 2008 sur un autre ordinateur, vous devez déployer les versions Debug des DLL de bibliothèque Visual C\+\+ comme assemblys côte à côte partagés.  Utilisez soit un projet d'installation soit Windows Installer pour installer les modules de fusion correspondants.  
  
-   Utilisez l'option**Déployer** dans la boîte de dialogue **Gestionnaire de configurations** dans Visual Studio pour copier la sortie de projet et d'autres fichiers sur l'ordinateur distant.  Un exemple de ce déploiement se trouve dans [Configuration du débogage distant pour un projet Visual Studio](../Topic/Set%20Up%20Remote%20Debugging%20for%20a%20Visual%20Studio%20Project.md).  
  
 Après avoir installé les bibliothèques Visual C\+\+, exécutez un débogueur distant sur un partage réseau.  Pour plus d'informations sur le débogage distant, consultez [Configurer les outils de contrôle à distance sur le périphérique](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md).  
  
## Voir aussi  
 [Configurer les outils de contrôle à distance sur le périphérique](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)   
 [Déploiement dans Visual C\+\+](../ide/deployment-in-visual-cpp.md)   
 [Options de ligne de commande Windows Installer](http://msdn.microsoft.com/library/windows/desktop/aa367988.aspx)   
 [Exemples de déploiement](../ide/deployment-examples.md)