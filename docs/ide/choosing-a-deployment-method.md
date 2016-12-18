---
title: "Choix d&#39;une m&#233;thode de d&#233;ploiement | Microsoft Docs"
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
  - "déploiement d'applications (C++), méthodes"
  - "déployer des applications (C++), méthodes"
  - "DLL (C++), redistribuer"
  - "liaison dynamique (C++)"
  - "bibliothèques (C++), problèmes de déploiement d'applications"
  - "manifestes (C++)"
  - "redistribuer des DLL"
  - "assemblys côte à côte (C++)"
  - "liaison statique (C++)"
ms.assetid: fd8eb956-f4a0-4ffb-b401-328c73e66986
caps.latest.revision: 35
caps.handback.revision: 35
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Choix d&#39;une m&#233;thode de d&#233;ploiement
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

À moins que votre application [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] soit autonome et déployable à l'aide d'une commande de copie, nous vous recommandons d'utiliser Windows Installer pour le déploiement.  Windows Installer prend en charge l'installation, la réparation, et la désinstallation. Il prend également en charge la mise à jour atomique des fichiers, des dépendances et des entrées de registre de l'application.  
  
> [!NOTE]
>  Bien que le déploiement [ClickOnce](../Topic/ClickOnce%20Security%20and%20Deployment.md) des applications natives [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] soit possible dans Visual Studio, il requiert des étapes supplémentaires.  Pour plus d'informations, consultez [Déploiement de ClickOnce pour les applications Visual C\+\+](../ide/clickonce-deployment-for-visual-cpp-applications.md).  
  
## Les bibliothèques Visual C\+\+ sont des DLL partagées  
 Les bibliothèques Visual C\+\+ étant installées dans le répertoire %windir%\\system32\\ par le programme d'installation de Visual Studio, toute application Visual C\+\+ que vous développerez avec des dépendances à celles\-ci fonctionnera comme prévu.  Toutefois, avant de déployer l'application sur des ordinateurs où Visual Studio peut être absent, nous vous recommandons de vérifier que les bibliothèques sont installées sur ceux\-ci en même temps que l'application.  
  
## Redistribution des bibliothèques Visual C\+\+  
 Dans vos déploiements, vous pouvez redistribuer n'importe quelle version d'une bibliothèque Visual C\+\+ dont la redistribution est autorisée.  Voici trois manières de les déployer :  
  
-   Le déploiement centralisé, à l'aide de packages redistribuables, qui installe les bibliothèques Visual C\+\+ en tant que DLL partagées dans %windir%\\system32\\. \(L'installation dans ce dossier requiert des droits d'administrateur\). Vous pouvez créer un script ou un programme d'installation qui exécute le package redistribuable avant d'installer l'application sur l'ordinateur cible.  Il existe des packages redistribuables pour les plateformes x86, x64 et ARM \(VCRedist\_x86.exe, VCRedist\_x64.exe, ou VCRedist\_arm.exe\).  Visual Studio inclut ces packages dans %ProgramFiles\(x86\)%\\Microsoft Visual Studio `version`\\VC\\Redist \\`locale ID`\\.  Vous pouvez également les télécharger à partir du [Centre de téléchargement Microsoft](http://go.microsoft.com/fwlink/?LinkId=132793). \(Sur le centre de téléchargement, recherchez le « package redistribuable *Visual Studio version and update*de [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] » qui correspond à votre application.  Par exemple, si vous avez utilisé la mise à jour 4 de Visual Studio 2012 pour générer votre application, recherchez « Visual C\+\+ Redistributable Package 2012 update 4 ».\) Pour plus d'informations sur l'utilisation d'un package redistribuable, consultez [Procédure pas à pas : déploiement d'une application Visual C\+\+ à l'aide de Visual C\+\+ Redistributable Package](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
-   Le déploiement centralisé à l'aide des modules de fusion, chacun installant une bibliothèque Visual C\+\+ particulière en tant que DLL partagé dans %windir%\\system32\\. \(L'installation dans ce dossier requiert des droits d'administrateur\). Les modules de fusion font partie des fichiers d'installation .msi de votre application.  Les modules de fusion redistribuables Visual C\+\+ sont inclus dans Visual Studio sous \\Program Files \(x86\)\\Common Files\\Merge Modules\\.  Pour plus d'informations, consultez [Redistribution à l'aide de modules de fusion](../ide/redistributing-components-by-using-merge-modules.md).  
  
-   Le déploiement local, qui consiste à copier certaines DLL Visual C\+\+ de votre installation Visual Studio, généralement de Program Files \(x86\)\\Microsoft Visual Studio `version`\\VC\\Redist\\`platform`\\`library`\\, et à les installer ensuite sur les ordinateurs cibles dans le même dossier que le fichier exécutable de l'application.  Vous pouvez utiliser cette méthode de déploiement pour permettre l'installation par des utilisateurs ne possédant pas de droits d'administrateur, ou pour les applications exécutables à partir d'un partage réseau.  
  
 Lorsqu'un déploiement utilise des modules de fusion redistribuables et que l'installation est exécutée par un utilisateur dépourvu des droits d'administrateur, les DLL [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] ne sont pas installées et l'application ne s'exécute pas.  De plus, les programmes d'installation d'application, générés avec des modules de fusion permettant l'installation par des utilisateurs individuels, installent les bibliothèques dans un emplacement partagé qui affecte tous les utilisateurs du système.  Vous pouvez utiliser le déploiement local pour installer les DLL [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] requises dans le répertoire d'application d'un utilisateur particulier, et ce, sans affecter d'autres utilisateurs ou exiger des droits d'administrateur.  En raison de problèmes de maintenance possibles, nous déconseillons le déploiement local des DLL redistribuables [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  
  
 Une redistribution incorrecte des bibliothèques Visual C\+\+ peut provoquer des erreurs pendant l'exécution d'une application qui en dépend.  Lorsque le système d'exploitation charge l'application, il utilise l'ordre de recherche décrit dans [LoadLibraryEx](http://go.microsoft.com/fwlink/?LinkId=132792)  
  
## La liaison dynamique est supérieure à la liaison statique  
 Nous vous recommandons d'éviter une liaison statique lorsque vous redistribuez des bibliothèques [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)].  Bien que la liaison statique n'améliore presque jamais de manière significative les performances des applications, elle en rend la maintenance presque toujours plus coûteuse.  Par exemple, considérez une application statiquement liée à une bibliothèque en cours de mise à jour avec des améliorations de sécurité. Celle\-ci ne pourra pas bénéficier des ces améliorations à moins d'être recompilée et redéployée.  À la place, nous vous recommandons de lier vos applications dynamiquement aux bibliothèques desquelles elles dépendent, de manière à en permettre la mise à jour dans tous les emplacements où elles sont déployées.  
  
## Voir aussi  
 [Déploiement des applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Not in Build: Choosing a Deployment Strategy](http://msdn.microsoft.com/fr-fr/ecd632d8-063c-4028-b785-81bba045107b)   
 [Windows Installer Deployment Overview](http://msdn.microsoft.com/fr-fr/3ce4610a-b54f-404e-b650-42f4a55dfc3b)   
 [ClickOnce Security and Deployment](../Topic/ClickOnce%20Security%20and%20Deployment.md)   
 [Exemples de déploiement](../ide/deployment-examples.md)