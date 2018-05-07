---
title: Déploiement dans Visual C++ | Documents Microsoft
ms.custom: ''
ms.date: 03/13/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying applications [C++]
- application deployment [C++]
ms.assetid: d4b4ffc0-d2bd-4e4a-84a6-62f1c26f6a09
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d9880272a09cde3bec0dbbbe03bfc30821591d6b
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="deployment-in-visual-c"></a>Déploiement dans Visual C++

Installation de votre application sur un ordinateur autre que votre ordinateur de développement est appelée *déploiement*. Lorsque vous déployez une application Visual C++ vers un autre ordinateur, vous devez installer l’application et tous les fichiers bibliothèques qu'il dépend. Visual Studio permet de trois façons de déployer les bibliothèques Visual C++ avec votre application : *déploiement central*, *déploiement local*, et *liaison statique*. Déploiement central place les fichiers de bibliothèque sous le répertoire Windows, où le service Windows Update peut les mettre à jour automatiquement. Déploiement local place les fichiers de bibliothèque dans le même répertoire que votre application. Vous devez redéployer toutes les bibliothèques déployées localement afin de les mettre à jour. La liaison statique, le code de bibliothèque est liée dans votre application. Vous devez recompiler et redéployer votre application pour tirer parti de toutes les mises à jour pour les bibliothèques lorsque vous utilisez la liaison statique.

## <a name="central-deployment"></a>Déploiement central

Dans un déploiement centralisé, les fichiers DLL de bibliothèque sont installés dans le répertoire Windows\System32, ou pour les fichiers de bibliothèques 32 bits sur x64 systèmes, le répertoire Windows\SysWow64. Microsoft met automatiquement à jour les bibliothèques qui sont déployées de manière centralisée. Pour les bibliothèques Visual C++ qui sont déployées localement ou liées de manière statique, vous devez fournir les mises à jour.

Pour déployer de manière centralisée les bibliothèques Visual C++, vous pouvez utiliser une de ces deux sources pour les fichiers à installer :

- *Package redistribuable* fichiers, qui sont des exécutables de ligne de commande autonomes qui contiennent toutes les bibliothèques de package redistribuables Visual C++ dans un format compressé, ou

- *Modules de fusion redistribuables* (fichiers .msm), qui vous permet de déployer des bibliothèques spécifiques, et que vous incluez dans le fichier Windows Installer (.msi) de votre application.

Un fichier de package redistribuable installe toutes les bibliothèques Visual C++ pour une architecture système particulière. Par exemple, si votre application est générée pour x64, vous pouvez utiliser le package redistribuable vcredist_x64.exe pour installer toutes les bibliothèques Visual C++ de que votre application utilise. Vous pouvez programmer votre programme d’installation de l’application pour exécuter le package redistribuable comme composant requis avant d’installer votre application.

Un module de fusion permet l’inclusion de logique d’installation d’une bibliothèque Visual C++ spécifique dans un fichier d’installation de Windows Installer. Vous pouvez inclure des modules de fusion autant ou aussi peu que votre application requiert. Utilisez les modules de fusion lorsque vous avez besoin réduire la taille des fichiers binaires de votre déploiement.

Étant donné que le déploiement centralisé à l’aide d’un package redistribuable ou des modules de fusion permet à Windows Update pour mettre à jour automatiquement les bibliothèques Visual C++, nous recommandons que vous utilisez la DLL de la bibliothèque dans votre application au lieu de bibliothèques statiques et central déploiement au lieu d’un déploiement local.

## <a name="local-deployment"></a>Déploiement local

Dans un déploiement local, les fichiers bibliothèques sont installés dans votre dossier d’application avec le fichier exécutable. Différentes versions des bibliothèques redistribuables Visual C++ peuvent être installées dans le même dossier, car le nom de fichier de chaque version inclut son numéro de version. Par exemple, la version 12 de la bibliothèque runtime C++ est msvcp120.dll et la version 14 est msvcp140.dll.

Une bibliothèque peut-être être répartie sur plusieurs DLL supplémentaires, appelés *point bibliothèques*. Par exemple, certaines fonctionnalités dans la bibliothèque standard publiée dans Visual Studio 2017 version 15,6 a été ajoutée à msvcp140_1.dll, à preverve la compatibilité ABI de msvcp140.dll. Si vous utilisez la version de Visual Studio 2017 15,6 (ensemble d’outils 14.13) ou un ensemble d’outils ultérieur à partir de Visual Studio 2017, vous devrez peut-être déployer localement de ces bibliothèques point ainsi que la bibliothèque principale. Ces bibliothèques point distincts sont ensuite ajoutées dans la prochaine version majeure de la bibliothèque de base lorsque l’ABI est modifiée.

Étant donné que Microsoft ne peut pas automatiquement mise à jour localement déployée des bibliothèques Visual C++, nous ne recommandons pas de déploiement local de ces bibliothèques. Si vous décidez de recourir au déploiement local des bibliothèques redistribuables, nous vous recommandons d'appliquer votre propre méthode de mise à jour automatique des bibliothèques déployées localement.

## <a name="static-linking"></a>Liaison statique

En plus des bibliothèques liées dynamiquement, Visual Studio fournit la plupart de ses bibliothèques en tant que bibliothèques statiques. Vous pouvez statiquement lier une bibliothèque statique à votre application, autrement dit, lier le code objet de bibliothèque directement dans l’application. Cette opération crée un seul fichier binaire sans une dépendance de la DLL, afin que vous n’êtes pas obligé de déployer les fichiers de bibliothèque Visual C++ séparément. Toutefois, nous déconseillons cette approche, car les bibliothèques liées statiquement ne peut pas être mis à jour sur place. Si vous utilisez la liaison statique et souhaitez mettre à jour une bibliothèque liée, vous devez recompiler et redéployer votre application.

## <a name="troubleshooting-deployment-issues"></a>Résolution des problèmes de déploiement

L’ordre de chargement des bibliothèques Visual C++ est dépendante du système. Pour diagnostiquer des problèmes liés au chargeur, utilisez depends.exe ou where.exe. Pour plus d’informations, consultez [ordre de recherche de bibliothèque de liens dynamiques (Windows)](http://msdn.microsoft.com/library/windows/desktop/ms682586.aspx).

## <a name="see-also"></a>Voir aussi

[Déploiement d’Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)