---
title: Déploiement d’Applications de bureau natives (Visual C++) | Documents Microsoft
ms.custom: ''
ms.date: 05/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
- Visual C++, application deployment
- application deployment [C++], about application deployment
- deploying applications [C++], about deploying applications
- distributing applications [C++]
ms.assetid: 37f1691e-d67c-41e4-926e-528a237a9bac
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4f4aa355c132b4c94f085cbdf7aa73785357d0f0
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
---
# <a name="deploying-native-desktop-applications-visual-c"></a>Déploiement des applications de bureau natives (Visual C++)

Un déploiement est le processus par lequel vous distribuez une application ou un composant terminé pour l’installer sur d’autres ordinateurs. La planification du déploiement commence quand l’application est créée sur l’ordinateur d’un développeur. Un déploiement se termine quand l’application est installée et prête à être exécutée sur l’ordinateur d’un utilisateur.

Visual Studio fournit différentes technologies pour déployer des applications Windows. Celles-ci incluent le déploiement ClickOnce et déploiement de Windows Installer.

- ClickOnce peut être utilisé pour déployer des applications C++ qui ciblent le common language runtime (CLR), assemblys mixtes, pures et vérifiables. Bien que vous pouvez utiliser Windows Installer pour déployer une application managée, nous vous recommandons d’utiliser ClickOnce, car il tire parti des fonctionnalités de sécurité .NET Framework tels que la signature de manifeste. ClickOnce ne prend pas en charge le déploiement des applications C++ natives. Pour plus d’informations, consultez [ClickOnce Deployment for Visual C++ Applications](../ide/clickonce-deployment-for-visual-cpp-applications.md).

- La technologie Windows Installer peut être utilisée pour déployer des applications C++ natives ou des applications C++ qui ciblent le CLR.

Les articles de cette section de la documentation expliquent comment vous assurer qu’une application Visual C++ native s’exécute sur tout ordinateur qui fournit une plateforme cible prise en charge, quels fichiers vous devez inclure dans un package d’installation et les méthodes recommandées pour redistribuer les composants dont votre application dépend.

## <a name="in-this-section"></a>Dans cette section

- [Déploiement dans Visual C++](../ide/deployment-in-visual-cpp.md)

- [Concepts relatifs au déploiement](../ide/deployment-concepts.md)

- [Fonctionnement des dépendances d’une application Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md)

- [Détermination des DLL à redistribuer](../ide/determining-which-dlls-to-redistribute.md)

- [Choix d’une méthode de déploiement](../ide/choosing-a-deployment-method.md)

- [Déploiement de CRT universel](universal-crt-deployment.md).

- [Redistribution des fichiers Visual C++](../ide/redistributing-visual-cpp-files.md)

- [Exemples de déploiement](../ide/deployment-examples.md)

- [Redistribution d’applications clientes web](../ide/redistributing-web-client-applications.md)

- [Déploiement de ClickOnce pour les applications Visual C++](../ide/clickonce-deployment-for-visual-cpp-applications.md)

- [Exécution d’une Application C++ /clr sur une Version antérieure du Runtime](../ide/running-a-cpp-clr-application-on-a-previous-runtime-version.md)

## <a name="related-sections"></a>Rubriques connexes

- [Génération d’applications isolées et d’assemblys côte à côte C/C++](../build/building-c-cpp-isolated-applications-and-side-by-side-assemblies.md)

- [Déploiement](/dotnet/framework/deployment/index)

- [Dépannage d’applications isolées et d’assemblys côte à côte C/C++](../build/troubleshooting-c-cpp-isolated-applications-and-side-by-side-assemblies.md)