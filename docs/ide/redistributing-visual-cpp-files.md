---
title: Redistribution des fichiers Visual C++ | Documents Microsoft
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
- application deployment [C++], file redistributing
- redistributing applications [C++]
- deploying applications [C++], file redistributing
- file redistribution [C++]
- redistributing applications [C++], about redistributing applications
ms.assetid: d201b2ce-36f1-44e5-a96c-0db81a1ba652
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 45035847befc08f667c95238ede0604651c7e9b6
ms.sourcegitcommit: 30ab99c775d99371ed22d1a46598e542012ed8c6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
# <a name="redistributing-visual-c-files"></a>Redistribution des fichiers Visual C++

> [!NOTE]
> Êtes-vous ici, car vous cherchez un téléchargement de l’un des fichiers exécutables Visual C++ ? Accédez à la [Microsoft](http://www.microsoft.com/) site Web et entrez **Visual C++ Redistributable** dans la zone de recherche. Téléchargez et installez le package redistribuable pour l’architecture de votre ordinateur (par exemple, x64 si vous exécutez Windows 64 bits) et la version de Visual C++ (par exemple, 2015) dont vous avez besoin.

Lorsque vous déployez une application, vous devez également déployer les fichiers qui sont requis pour sa prise en charge. Si l'un de ces fichiers est fourni par Microsoft, vérifiez si vous êtes autorisé à le redistribuer. Pour passer en revue les termes du contrat de licence de Visual Studio, consultez le lien de termes du contrat de licence dans la boîte de dialogue à propos de Microsoft Visual Studio dans l’IDE, ou télécharger le [termes du contrat de licence de logiciel Microsoft](http://go.microsoft.com/fwlink/p/?LinkId=831114) fichier. Pour afficher la « liste REDIST » référencée dans la section « Code distribuable » des termes du contrat de licence logiciel Microsoft de certaines éditions de Visual Studio, consultez [Code distribuable pour Microsoft Visual Studio 2017 et Microsoft Visual Studio 2017 Kit de développement logiciel (inclut des utilitaires et des fichiers BuildServer)](http://go.microsoft.com/fwlink/p/?LinkId=823098), ou pour Visual Studio 2015, consultez [Code distribuable pour Microsoft Visual Studio 2015 et Microsoft Visual Studio 2015 SDK](http://go.microsoft.com/fwlink/p/?LinkId=523763). Pour plus d’informations sur les fichiers redistribuables, consultez [détermination des DLL à redistribuer](../ide/determining-which-dlls-to-redistribute.md) et [des exemples de déploiement](../ide/deployment-examples.md).

Pour déployer les fichiers redistribuables Visual C++, vous pouvez utiliser les Packages redistribuables Visual C++ (VCRedist\_x86.exe, VCRedist\_x64.exe ou VCRedist\_arm.exe) qui sont inclus dans Visual Studio. Dans Visual Studio 2017, vous pouvez trouver ces fichiers dans les fichiers de programme [(x86)]\\Microsoft Visual Studio\\2017\\_édition_\\VC\\Redist\\ MSVC\\_lib-version_ dossier, où _édition_ est installée, l’édition de Visual Studio et _lib-version_ est la version de la bibliothèques à redistribuer. Dans Visual Studio 2015, ces fichiers sont accessibles sous le répertoire d’installation de Visual Studio dans Program Files [(x 86)] \Microsoft Visual Studio *version*\VC\redist\\*paramètres régionaux* \\. Une autre option consiste à utiliser des modules de fusion redistribuables (fichiers .msm), qui, dans Visual Studio 2017 se trouvent dans les fichiers de programme [(x 86)]\\Microsoft Visual Studio\\2017\\_édition_ \\ VC\\Redist\\MSVC\\_lib-version_\\MergeModules\\ dossier. Dans Visual Studio 2015 ces se trouve dans Program Files [(x 86)] \Common Modules\\. Il est également possible d’installer directement les DLL Visual C++ redistribuables dans le *dossier local de l’application*, qui est le dossier qui contient votre fichier d’application exécutable. Pour des raisons liées à la maintenance, il est déconseillé d'utiliser cet emplacement d'installation.

Les packages redistribuables Visual C++ installent et inscrivent toutes les bibliothèques Visual C++. Si vous en utilisez un, vous devez le définir de sorte qu'il s'exécute sur le système cible en tant que condition préalable à l'installation de l'application. Nous vous recommandons d'utiliser ces packages pour les déploiements car ils permettent une mise à jour automatique des bibliothèques Visual C++. Pour obtenir un exemple sur l’utilisation de ces packages, consultez [procédure pas à pas : déploiement d’un Visual C++ Application à l’aide du Package redistribuable Visual C++](../ide/deploying-visual-cpp-application-by-using-the-vcpp-redistributable-package.md).

Chaque package redistribuable Visual C++ vérifie l'existence d'une version plus récente sur l'ordinateur. Si une version plus récente est trouvée, le package n'est pas installé. Depuis Visual Studio 2015, les packages redistribuables affichent un message d'erreur indiquant que l'installation a échoué. Si un package est exécuté à l’aide de la **/quiet/** indicateur, aucun message d’erreur s’affiche. Dans les deux cas, une erreur est enregistrée par le programme d'installation de Microsoft, et un résultat d'erreur est retourné à l'appelant. À partir de packages de Visual Studio 2015, vous pouvez éviter cette erreur en consultant le Registre pour déterminer si une version plus récente est installée. La version actuellement installée est stockée dans le \Microsoft\VisualStudio HKEY_LOCAL_MACHINE\SOFTWARE [\Wow6432Node]\\_vs-version_\VC\Runtimes\\{x86 | x64 | Clé ARM}, où _vs-version_ est le numéro de version pour Visual Studio (14.0 pour Visual Studio 2015 et Visual Studio 2017, étant donné que la mise à jour 2017 redistribuable est compatible binaire avec la version 2015), et où la clé est ARM, x 86 ou x64 selon les versions installées de vcredist pour la plateforme. (Vous n’avez pas besoin de vérifier sous la sous-clé Wow6432Node sauf si vous utilisez RegEdit pour afficher la version de le x86 installé le package sur un x64 plateforme.) Le numéro de version est stocké dans la valeur de chaîne REG_SZ **Version** et également dans l’ensemble de **majeure**, **secondaire**, **Bld**et **Rbld** valeurs REG_DWORD. Pour éviter une erreur au moment de l’installation, vous devez ignorer l’installation du package redistribuable si la version actuellement installée est plus récente.

Si vous utilisez un module de fusion qui contient une DLL Visual C++, vous devez l’inclure dans le package Windows Installer (ou dans un package d’installation similaire) que vous utilisez pour déployer l’application. Pour plus d’informations, consultez [redistribution à l’aide de Modules de fusion](../ide/redistributing-components-by-using-merge-modules.md). Pour obtenir un exemple, consultez [procédure pas à pas : déploiement d’un Visual C++ Application à l’aide d’un projet d’installation](../ide/walkthrough-deploying-a-visual-cpp-application-by-using-a-setup-project.md), qui montre également comment utiliser InstallShield Limited Edition pour créer un package d’installation.

## <a name="potential-run-time-errors"></a>Erreurs d'exécution potentielles

Si Windows ne peut pas trouver un de la bibliothèque redistribuable DLL requis pour votre application, un message semblable à celle-ci peut s’afficher : « cette application n’a pas pu démarrer car *bibliothèque*.dll est introuvable. Réinstallez l’application pourrait résoudre ce problème. »

Pour résoudre ce genre d’erreur, assurez-vous que votre programme d’installation de l’application se génère correctement et que les bibliothèques redistribuables sont déployées correctement sur le système cible. Pour plus d’informations, consultez [comprendre les dépendances d’une Application Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md).

## <a name="related-topics"></a>Rubriques connexes

|Titre|Description|
|-----------|-----------------|
|[Redistribution à l’aide des Modules de fusion](../ide/redistributing-components-by-using-merge-modules.md)|Décrit comment utiliser des modules de fusion redistribuables Visual C++ pour installer les bibliothèques runtime Visual C++ en tant que DLL partagées dans le dossier %windir%\system32\.|
|[Redistribution de contrôles ActiveX Visual C++](../ide/redistributing-visual-cpp-activex-controls.md)|Décrit comment redistribuer une application qui utilise les contrôles ActiveX.|
|[Redistribution de fichiers de prise en charge de base de données](../ide/redistributing-database-support-files.md)|Explique comment redistribuer des fichiers de prise en charge pour les objets d'accès aux données (DAO) et les technologies de bases de données se trouvant dans le Kit de développement Microsoft Data Access SDK.|
|[Redistribution de la bibliothèque MFC](../ide/redistributing-the-mfc-library.md)|Décrit comment redistribuer une application qui utilise MFC.|
|[Redistribution d’une application ATL](../ide/redistributing-an-atl-application.md)|Décrit comment redistribuer une application qui utilise ATL. Depuis Visual Studio 2012, aucune bibliothèque redistribuable pour ATL n'est requise.|
|[Exemples de déploiement](../ide/deployment-examples.md)|Fournit des liens vers des exemples qui illustrent le déploiement d'applications Visual C++.|
|[Déploiement d’Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)|Présente les concepts et les technologies de déploiement de Visual C++.|