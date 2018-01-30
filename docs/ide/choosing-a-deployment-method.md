---
title: "Choix d’une méthode de déploiement | Documents Microsoft"
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
- redistributing DLLs
- manifests [C++]
- DLLs [C++], redistributing
- side-by-side assemblies [C++]
- dynamic linking [C++]
- application deployment [C++], methods
- deploying applications [C++], methods
- static linking [C++]
- libraries [C++], application deployment issues
ms.assetid: fd8eb956-f4a0-4ffb-b401-328c73e66986
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4e4336f200f736ea7656af11c7c7c43ca32f27f9
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2018
---
# <a name="choosing-a-deployment-method"></a>Choix d'une méthode de déploiement
À moins que votre application Visual C++ est autonome et peut être déployée à l’aide d’une commande de copie, nous recommandons d’utiliser Windows Installer pour le déploiement. Windows Installer prend en charge l'installation, la réparation, et la désinstallation. Il prend également en charge la mise à jour atomique des fichiers, des dépendances et des entrées de registre de l'application.  
  
> [!NOTE]
>  Bien que [ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment) déploiement pour les applications Visual C++ natives est possible dans Visual Studio, il requiert des étapes supplémentaires. Pour plus d’informations, consultez [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md).  
  
## <a name="visual-c-libraries-are-shared-dlls"></a>Les bibliothèques Visual C++ sont des DLL partagées  
 Les bibliothèques Visual C++ étant installées dans le répertoire %windir%\system32\ par le programme d'installation de Visual Studio, toute application Visual C++ que vous développerez avec des dépendances à celles-ci fonctionnera comme prévu. Toutefois, avant de déployer l'application sur des ordinateurs où Visual Studio peut être absent, nous vous recommandons de vérifier que les bibliothèques sont installées sur ceux-ci en même temps que l'application.  
  
## <a name="redistributing-visual-c-libraries"></a>Redistribution des bibliothèques Visual C++  
 Dans vos déploiements, vous pouvez redistribuer n'importe quelle version d'une bibliothèque Visual C++ dont la redistribution est autorisée. Voici trois manières de les déployer :  
  
-   Déploiement centralisé à l’aide de packages redistribuables, qui installe les bibliothèques Visual C++ en tant que DLL partagées dans %windir%\system32\\. (L’installation dans ce dossier requiert des droits d’administrateur). Vous pouvez créer un script ou un programme d'installation qui exécute le package redistribuable avant d'installer l'application sur l'ordinateur cible. Il existe des packages redistribuables pour les plateformes x86, x64 et ARM (VCRedist_x86.exe, VCRedist_x64.exe, ou VCRedist_arm.exe). Visual Studio inclut ces packages dans % ProgramFiles% (x86) %\Microsoft Visual Studio `version`\VC\Redist\\`locale ID`\\. Vous pouvez également les télécharger à partir de la [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?linkid=132793). (Sur le centre de téléchargement, recherchez le « Package redistribuable Visual C++ *mise à jour et la version de Visual Studio*» qui correspond à votre application. Par exemple, si vous avez utilisé la mise à jour 4 de Visual Studio 2012 pour générer votre application, recherchez « Visual C++ Redistributable Package 2012 update 4 ».) Pour plus d’informations sur l’utilisation d’un package redistribuable, consultez [procédure pas à pas : déploiement d’un Visual C++ Application à l’aide du Package redistribuable Visual C++](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).  
  
-   Déploiement centralisé à l’aide de modules de fusion, chacun installant une bibliothèque Visual C++ particulière en tant que DLL partagé dans %windir%\system32\\. (L’installation dans ce dossier requiert des droits d’administrateur). Les modules de fusion font partie des fichiers d’installation .msi de votre application. Les modules de fusion redistribuables Visual C++ sont inclus dans Visual Studio, dans \Program Files (x86) \Common Modules\\. Pour plus d’informations, consultez [redistribution à l’aide de Modules de fusion](../ide/redistributing-components-by-using-merge-modules.md).  
  
-   Un déploiement local, dans lequel vous copiez certaines DLL Visual C++ dans votre installation de Visual Studio, généralement dans \Program Files (x86) \Microsoft Visual Studio `version`\VC\Redist\\`platform`\\`library`\—and les installer sur les ordinateurs cibles dans le même dossier que l’exécutable d’application. Vous pouvez utiliser cette méthode de déploiement pour permettre l'installation par des utilisateurs ne possédant pas de droits d'administrateur, ou pour les applications exécutables à partir d'un partage réseau.  
  
 Si un déploiement utilise des modules de fusion redistribuables et une installation est exécutée par un utilisateur ne disposant pas de droits d’administration, les DLL Visual C++ ne sont pas installés, et l’application s’exécutera pas. De plus, les programmes d’installation d’application, générés avec des modules de fusion permettant l’installation par des utilisateurs individuels, installent les bibliothèques dans un emplacement partagé qui affecte tous les utilisateurs du système. Vous pouvez utiliser le déploiement local pour installer les DLL Visual C++ requis dans le répertoire de l’application d’un utilisateur particulier sans affecter d’autres utilisateurs ou exiger des droits d’administrateur. Étant donné que cela peut créer des problèmes de facilité de gestion, nous déconseillons de déploiement local des DLL redistribuables Visual C++.  
  
 Une redistribution incorrecte des bibliothèques Visual C++ peut provoquer des erreurs pendant l'exécution d'une application qui en dépend. Lorsque le système d’exploitation se charge de l’application, il utilise l’ordre de recherche décrit dans [LoadLibraryEx](http://go.microsoft.com/fwlink/p/?linkid=132792)  
  
## <a name="dynamic-linking-is-better-than-static-linking"></a>La liaison dynamique est supérieure à la liaison statique  
 Nous vous recommandons d’éviter la liaison statique lorsque vous redistribuez des bibliothèques Visual C++. Bien que la liaison statique n’améliore presque jamais de manière significative les performances des applications, elle en rend la maintenance presque toujours plus coûteuse. Par exemple, considérez une application statiquement liée à une bibliothèque en cours de mise à jour avec des améliorations de sécurité. Celle-ci ne pourra pas bénéficier des ces améliorations à moins d'être recompilée et redéployée. À la place, nous vous recommandons de lier vos applications dynamiquement aux bibliothèques desquelles elles dépendent, de manière à en permettre la mise à jour dans tous les emplacements où elles sont déployées.  
  
## <a name="see-also"></a>Voir aussi  
 [Déploiement d’Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)   
 [Sécurité et déploiement ClickOnce](/visualstudio/deployment/clickonce-security-and-deployment)   
 [Exemples de déploiement](../ide/deployment-examples.md)