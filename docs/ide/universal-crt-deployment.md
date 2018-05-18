---
title: Déploiement de CRT universel | Documents Microsoft
ms.custom: ''
ms.date: 05/11/2018
ms.technology:
- cpp-ide
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- deploying the CRT [C++]
- application CRT deployment [C++]
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 20006118d4bf27c379b78b84dc8807a4fd6c5e6c
ms.sourcegitcommit: 19a108b4b30e93a9ad5394844c798490cb3e2945
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/17/2018
---
# <a name="universal-crt-deployment"></a>Déploiement de CRT universel

À partir de Visual Studio .NET via Visual Studio 2013, chaque version majeure du compilateur C++ et des outils a inclus une nouvelle version autonome de la bibliothèque Microsoft C Runtime (CRT). Ces versions autonome de la bibliothèque CRT ont été indépendamment à partir d’et à différents degrés, incompatibles entre eux. Par exemple, la bibliothèque CRT utilisée par Visual Studio 2012 a été msvcr110.dll nommé de version 11, et la bibliothèque CRT utilisée par Visual Studio 2013 a été msvcr120.dll nommé 12, de version. À compter de Visual Studio 2015, cela n’est plus le cas. Visual Studio 2015 et versions ultérieures de Visual Studio tous les utilisent une bibliothèque Universal CRT.

La bibliothèque Universal CRT est un composant du système d’exploitation Microsoft Windows. Il est inclus dans le système d’exploitation Windows 10 et est disponible pour les systèmes d’exploitation plus anciens, Windows Vista par le biais de Windows 8.1, à l’aide de Windows Update. En outre, un déploiement local de la bibliothèque Universal CRT est pris en charge, avec quelques restrictions.

## <a name="central-deployment"></a>Déploiement central

La méthode recommandée pour installer la bibliothèque Universal CRT de façon centralisée est d’utiliser Microsoft Windows Update. La bibliothèque Universal CRT est qu'une mise à jour recommandé pour toutes les prises en charge les systèmes d’exploitation Microsoft Windows, par que défaut, la plupart des machines l’installer dans le cadre du processus de mise à jour régulière. La version initiale de la bibliothèque Universal CRT a été [KB2999226](https://support.microsoft.com/en-us/kb/2999226); une mise à jour ultérieur avec différentes résolutions de bogue a été effectuée dans [KB3118401](https://support.microsoft.com/en-us/kb/3118401), et ont été mises à jour supplémentaires avec les autres correctifs de bogues et de nouvelles fonctionnalités. Pour les mises à jour plus récentes, recherchez [support.microsoft.com](https://support.microsoft.com) Universal C Runtime ou Universal CRT.

Tous les ordinateurs Microsoft Windows installent régulièrement les mises à jour à l’aide de Windows Update, et certaines peut ne pas installer les mises à jour recommandées. Pour prendre en charge l’utilisation des applications créées à l’aide de Visual Studio 2015 et des ensembles d’outils C++ plus loin sur ces ordinateurs, Universal CRT redistribuables sont disponibles pour la distribution en mode hors connexion. Ces composants redistribuables peuvent être téléchargés à partir d’un des liens ci-dessus Ko. Notez que les composants redistribuables Universal CRT exigent que l’ordinateur a été mis à jour pour le service pack actuel. Ainsi, par exemple, le composant redistribuable pour Windows 7 uniquement installera sur Windows 7 SP1, pas Windows 7 RTM.

Étant donné que la bibliothèque Universal CRT est une dépendance fondamentale des bibliothèques C++, le package redistribuable Visual C++ (VCRedist) installe une version de base de la bibliothèque Universal CRT sur des ordinateurs qui n’ont pas une version déjà installée, suffisante pour répondre à la bibliothèque C++ dépendances. Si votre application dépend d’une version plus récente de la bibliothèque Universal CRT, vous devez installer cette version plus récente explicitement. Il est préférable d’installer ce avant l’installation de la VCRedist, pour éviter plusieurs potentiel requis le redémarrage.

## <a name="local-deployment"></a>Déploiement local

Déploiement local de la bibliothèque Universal CRT est pris en charge, mais pas recommandé pour des raisons de performances et sécurité.  Les DLL pour le déploiement local sont inclus dans le Kit de développement logiciel Windows, dans les Kits Windows\\10\\Redist\\ucrt\\sous-répertoire DLL, par l’architecture de l’ordinateur. Les DLL requises incluent particulier ucrtbase.dll et un ensemble de redirecteur de APISet DLL nommés api-ms-win -\*.dll. Le jeu de DLL requis sur chaque système d’exploitation varie en fonction, il est vivement recommandé d’inclure toutes les DLL lorsque vous déployez localement.

Il existe deux restrictions sur le déploiement local à connaître :

- Sur Windows 10, la bibliothèque Universal CRT dans le répertoire système est toujours utilisée, même si une application inclut une copie de local de l’application de la bibliothèque Universal CRT. Cela est vrai même si la copie locale de la bibliothèque Universal CRT est la plus récente. Il s’agit, car la bibliothèque Universal CRT est un composant de système d’exploitation de base sur Windows 10.

- Dans les versions de Windows antérieures à Windows 8, le CRT universel ne peut pas être empaqueté localement avec un plug-in qui se trouve dans un répertoire autre que le répertoire qui contient le fichier exécutable principal de votre application. Le redirecteur APISet DLL ne peuvent pas résoudre le particulier ucrtbase.dll avec succès dans ce cas. Certaines solutions alternatives recommandées incluent :

  - Lier statiquement la bibliothèque Universal CRT,
  - Déployer de manière centralisée la bibliothèque Universal CRT, ou
  - Placez les fichiers de la bibliothèque Universal CRT dans le même répertoire que l’application.

## <a name="deployment-on-microsoft-windows-xp"></a>Déploiement sur Microsoft Windows XP

Visual Studio 2015 et Visual Studio 2017 continuent à prendre en charge le développement de logiciels pour une utilisation sur Microsoft Windows XP. Pour cela, une version de la bibliothèque Universal CRT fonctionne sur Microsoft Windows XP. Le système d’exploitation Microsoft Windows XP n’est plus prise en charge standard ou étendue, donc déploiement central de la bibliothèque Universal CRT sur Microsoft Windows XP est différent d’autres systèmes d’exploitation.

Lorsque Visual C++ redistributable est installé sur Windows XP, il directement installe le CRT universel et toutes ses dépendances dans le répertoire système, sans installer ou selon une mise à jour de Windows. Les modules de fusion redistribuables, les Microsoft_VC*version*_CRT_\*fichiers .msm, procédez de la même.

Déploiement local de la bibliothèque Universal CRT sur Windows XP est la même que dans d’autres systèmes d’exploitation pris en charge.

## <a name="see-also"></a>Voir aussi

- [Déploiement dans Visual C++](deployment-in-visual-cpp.md)
