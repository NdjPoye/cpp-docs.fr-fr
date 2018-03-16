---
title: "Détermination des DLL à redistribuer | Documents Microsoft"
ms.custom: 
ms.date: 03/13/2018
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
- DLLs [C++], redistributing
- dependencies [C++], application deployment and
- application deployment [C++], DLL redistribution
- deploying applications [C++], DLL redistribution
ms.assetid: f7a2cb42-fb48-42ab-abd2-b35e2fd5601a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a6f942b01dd9379aea0c0ea2ab3751a6f140ef2a
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="determining-which-dlls-to-redistribute"></a>Détermination des DLL à redistribuer

Lorsque vous générez une application qui utilise la DLL de bibliothèque fournis par Visual Studio, les utilisateurs de votre application doivent également disposer ces DLL sur leurs ordinateurs pour exécuter l’application. Comme il est probable que la plupart des utilisateurs n'ont pas installé Visual Studio, vous devez les leur fournir. Visual Studio apporte ces DLL disponibles en tant que *fichiers redistribuables* que vous pouvez inclure dans votre programme d’installation de l’application.

Pour faciliter l’inclure les DLL redistribuables avec votre programme d’installation, ils sont disponibles en mode autonome *packages redistribuables*. Il s’agit des exécutables spécifiques à une architecture qui utilisent le déploiement central pour installer les fichiers redistribuables sur l’ordinateur d’un utilisateur. Par exemple, vcredist\_x86.exe installe les bibliothèques de 32 bits pour x86 ordinateurs, vcredist\_x64.exe installe les bibliothèques 32 bits et 64 bits pour x64 ordinateurs et vcredist\_ARM.exe installe les bibliothèques pour ARM ordinateurs. Nous vous recommandons de déploiement central, car Microsoft peut utiliser le service Windows Update pour mettre à jour indépendamment de ces bibliothèques. En plus de la copie dans votre installation de Visual Studio, les packages redistribuables actuelles sont disponibles pour téléchargement sur [VisualStudio.com/Downloads](https://www.visualstudio.com/downloads/) dans la section autres outils et infrastructures.

Le numéro de version majeure du package redistribuable que vous déployez doit correspondre à la version de l’ensemble d’outils de Visual Studio permet de créer votre application. Visual Studio 2017 et Visual Studio 2015 ont des numéros de version de l’ensemble d’outils compatible, ce qui signifie que le Visual 2017 Studio fichiers redistribuables peuvent être utilisés par les applications générées à l’aide de l’ensemble d’outils 2015. Pendant qu’ils soient compatibles, nous ne pas en charge en utilisant les fichiers redistribuables 2015 dans les applications générées à l’aide de l’ensemble d’outils 2017. Nous prenons en charge uniquement à l’aide d’un package redistribuable est identique ou plus récent que votre version de la boîte à outils. Pour consulter des packages plus récents pris en charge redistribuables pour les ensembles d’outils plus anciens, voir [le plus récent pris en charge les téléchargements de Visual C++](https://support.microsoft.com/en-us/help/2977003/the-latest-supported-visual-c-downloads). Vous trouverez des versions antérieures des packages redistribuables en recherchant le [Microsoft Download Center](http://go.microsoft.com/fwlink/p/?LinkId=158431) pour « Packages redistribuables Visual C++ ».

Une autre consiste à inclure les DLL redistribuables avec votre programme d’installation à utiliser *de modules de fusion*. Ces modules Microsoft Installer sont inclus dans et installés par le programme d’installation de votre application. Modules de fusion pour les DLL redistribuables sont trouvent dans votre répertoire d’installation de Visual Studio sous \\VC\\Redist\MSVC\\*version*\\MergeModules\\ . Dans les versions antérieures de Visual Studio, ces fichiers se trouvent dans votre \\Program Files ou \\du répertoire Program Files (x86) dans un fichiers communs\\sous-répertoire de Modules de fusion. Pour plus d’informations sur l’utilisation de ces fichiers, consultez [redistribution des composants à l’aide de Modules de fusion](../ide/redistributing-components-by-using-merge-modules.md).

Les DLL redistribuables individuelles sont également inclus dans votre installation de Visual Studio. Par défaut, ils sont installés dans le répertoire d’installation de Visual Studio dans le \\VC\\Redist\\MSVC\\*version* dossier. Le *version* numéros peuvent représenter des nombres de différentes build mineure un ensemble commun de fichiers redistribuables. Utilisez la dernière version de n’importe quel fichier DLL de bibliothèque, un package redistribuable ou un module de fusion trouvé dans ces répertoires. Vous pouvez utiliser ces bibliothèques pour le déploiement local, en les installant dans le même répertoire que votre application. Nous déconseillons le déploiement local, car il vous est chargée de fournir des mises à jour pour vos applications déployées. Déploiement central en utilisant les packages redistribuables est recommandée.

Pour identifier les DLL à redistribuer avec votre application, collectez une liste des DLL dont dépend votre application. Ils sont normalement indiqués comme entrées dans l’éditeur de liens de la bibliothèque d’importation. Certaines bibliothèques, telles que vcruntime et le Runtime C universel bibliothèque (UCRT), sont inclus par défaut. Si votre application ou une de ses dépendances utilise LoadLibrary dynamiquement charger une DLL, cette DLL peut ne pas figurer dans les entrées de l’éditeur de liens. Une façon de collecter la liste des DLL chargées dynamiquement consiste à exécuter Dependency Walker (depends.exe) sur votre application, comme décrit dans [comprendre les dépendances d’une Application Visual C++](../ide/understanding-the-dependencies-of-a-visual-cpp-application.md). Malheureusement, cet outil est obsolète et risque de signaler qu’il ne peut pas trouver certaines DLL.

Lorsque vous disposez de la liste des dépendances, comparez-la à la liste liée dans le fichier Redist.txt situé sous le répertoire d’installation de Microsoft Visual Studio ou à la « liste REDIST » des DLL redistribuables référencée dans la section « Fichiers de Code distribuable » du contrat de licence de logiciel Microsoft pour votre copie de Visual Studio. Pour Visual Studio 2017, consultez [Code distribuable pour Microsoft Visual Studio 2017 (inclut des utilitaires, l’extensibilité et fichiers BuildServer)](http://go.microsoft.com/fwlink/p/?linkid=823098). Pour Visual Studio 2015, consultez [Code distribuable pour Microsoft Visual Studio 2015 et Microsoft Visual Studio 2015 SDK (inclut des utilitaires et des fichiers BuildServer)](http://go.microsoft.com/fwlink/p/?linkid=799794). Pour Visual Studio 2013, la liste est disponible en ligne dans [Code distribuable pour Microsoft Visual Studio 2013 et Microsoft Visual Studio 2013 SDK](http://go.microsoft.com/fwlink/p/?LinkId=313603).

Dans les versions de Visual Studio antérieures à Visual Studio 2015, la bibliothèque Runtime C (CRT) a été inclus en tant que DLL redistribuable, en msvc*version*.dll. À partir de Visual Studio 2015, les fonctions dans la bibliothèque CRT ont été refactorisées dans le vcruntime et l’UCRT. La bibliothèque UCRT est désormais un composant système dans Windows 10, gérés par Windows Update. Il est disponible sur tous les systèmes d’exploitation de Windows 10. Pour déployer votre application sur les systèmes d’exploitation antérieurs, vous devrez peut-être redistribuer la bibliothèque UCRT également. Une version antérieure de l’UCRT est inclus dans les fichiers redistribuables Visual Studio, qui est installé uniquement sur les systèmes d’exploitation antérieurs à Windows 10, et uniquement si aucune version de la bibliothèque UCRT n’est déjà installée. Pour obtenir une version installable de l’UCRT pour les systèmes de niveau inférieur en tant qu’un package de mise à jour du système de Microsoft, consultez [Windows 10 universelles C Runtime](https://www.microsoft.com/en-us/download/details.aspx?id=48234) dans du Microsoft Download Center.

Vous ne pouvez pas redistribuer tous les fichiers inclus dans Visual Studio ; vous êtes uniquement autorisé à redistribuer les fichiers spécifiés dans Redist.txt ou dans la « liste REDIST » en ligne. Les versions Debug des applications et les diverses DLL de débogage Visual C++ ne sont pas redistribuables. Pour plus d’informations, consultez [choix d’une méthode de déploiement](../ide/choosing-a-deployment-method.md).

Le tableau suivant décrit certaines des DLL Visual C++ dont votre application peut dépendre.

|Bibliothèque Visual C++|Description|S'applique à|
|--------------------------|-----------------|----------------|
|vcruntime*version*.dll|Bibliothèque d’exécution pour le code natif.|Applications qui utilisent les normal C et C++ démarrage et arrêt de services de langage.|
|vccorlib*version*.dll|Bibliothèque d’exécution pour le code managé.|Applications qui utilisent les services de langage C++ pour le code managé.|
|msvcp*version*.dll et msvcp*version*_*dotnumber*.dll|Bibliothèque Standard C++ pour le code natif.|Les applications qui utilisent la [bibliothèque Standard C++](../standard-library/cpp-standard-library-reference.md).|
|concrt*version*.dll|Bibliothèque du Runtime d’accès concurrentiel pour le code natif.|Les applications qui utilisent la [Runtime d’accès concurrentiel](../parallel/concrt/concurrency-runtime.md).|
|mfc*version*.dll|Bibliothèque MFC (Microsoft Foundation Class).|Les applications qui utilisent la [bibliothèque MFC](../mfc/mfc-desktop-applications.md).|
|MFC*version* *langage*.dll|Microsoft Foundation Classes (MFC) les ressources de bibliothèque.|Applications qui utilisent des ressources de langue spécifique pour que MFC.|
|mfc*version*u.dll|Bibliothèque MFC avec prise en charge Unicode.|Les applications qui utilisent la [bibliothèque MFC](../mfc/mfc-desktop-applications.md) et requièrent la prise en charge Unicode.|
|mfcmifc80.dll|Bibliothèque d'interfaces gérées MFC.|Les applications qui utilisent la [bibliothèque MFC](../mfc/mfc-desktop-applications.md) avec [des contrôles Windows Forms](/dotnet/framework/winforms/controls/index).|
|mfcm*version*.dll|Bibliothèque managée MFC.|Les applications qui utilisent la [bibliothèque MFC](../mfc/mfc-desktop-applications.md) avec [des contrôles Windows Forms](/dotnet/framework/winforms/controls/index).|
|mfcm*version*u.dll|Bibliothèque managée MFC avec prise en charge Unicode.|Les applications qui utilisent la [bibliothèque MFC](../mfc/mfc-desktop-applications.md) avec [des contrôles Windows Forms](/dotnet/framework/winforms/controls/index) et requièrent la prise en charge Unicode.|
|vcamp*version*.dll|Bibliothèque AMP pour le code natif.|Les applications qui utilisent la [bibliothèque de C++ AMP](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md) code.|
|vcomp*version*.dll|Bibliothèque OpenMP pour le code natif.|Les applications qui utilisent la [bibliothèque C++ OpenMP](../parallel/openmp/openmp-in-visual-cpp.md) code.|

> [!NOTE]
> Vous n'avez plus besoin de redistribuer Active Template Library sous forme de DLL distincte. Sa fonctionnalité a été déplacée dans les en-têtes et une bibliothèque statique.

Pour plus d’informations sur la redistribution des DLL avec votre application, consultez [redistribution des fichiers Visual C++](../ide/redistributing-visual-cpp-files.md). Pour obtenir des exemples, consultez [des exemples de déploiement](../ide/deployment-examples.md).

En règle générale, vous n'avez pas besoin de redistribuer les DLL système, car elles font partie intégrante du système d'exploitation. Toutefois, il peut y avoir des exceptions, par exemple, lorsque votre application doit s'exécuter sur plusieurs versions de systèmes d'exploitation Microsoft. Dans ce cas, veillez à lire les termes du contrat de licence correspondants. De même, essayez d'effectuer la mise à niveau des DLL système via Windows Update, les Service Packs ou les packages redistribuables proposés par Microsoft.

## <a name="see-also"></a>Voir aussi

[Choix d’une méthode de déploiement](../ide/choosing-a-deployment-method.md)

[Déploiement d’Applications de bureau](../ide/deploying-native-desktop-applications-visual-cpp.md)
