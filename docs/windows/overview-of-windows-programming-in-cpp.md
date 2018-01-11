---
title: "Vue d’ensemble de la programmation Windows en C++ | Documents Microsoft"
ms.custom: 
ms.date: 11/27/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9bf25d8f3653d2146774efd333daff74a5fb33e2
ms.sourcegitcommit: 54035dce0992ba5dce0323d67f86301f994ff3db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/03/2018
---
# <a name="overview-of-windows-programming-in-c"></a>Vue d'ensemble de la programmation Windows en C++

Vous pouvez utiliser Visual C++ pour écrire une large gamme de programmes qui s'exécutent sur un PC Windows (x86, x64 ou ARM), sur un serveur Windows, dans le cloud ou sur Xbox. Les programmes C++ bien écrits sont rapides, efficaces, économes en énergie et capables de tirer pleinement profit d'appareils dotés de plusieurs cœurs, voire de nombreux cœurs, du calcul générique sur processeur graphique (GPGPU) et d'autres avancées récentes dans le domaine du matériel informatique.

Il existe plusieurs grandes catégories d'applications Windows que vous pouvez développer avec Visual C++. Ces catégories ont des modèles de programmation différents ou des modèles d'application, ce qui signifie qu'elles utilisent différentes bibliothèques et API qui permettent d'accéder à la plateforme et fournissent une interface utilisateur.

- [Applications Windows universelles](#BK_WindowsUniversal). La troisième catégorie d'applications Windows a été introduite avec Windows 8 et la prise en charge de cette catégorie continue dans Windows 10. Ces applications sont souvent appelées simplement « applications Windows » et elles incluent des applications mobiles et de bureau qui ciblent divers appareils. Vous pouvez écrire ces applications en C++/CX, un dialecte de C++ qui inclut la prise en charge du développement Windows Runtime, ou en C++ standard avec COM qui utilise la bibliothèque WRL (Windows Runtime Library). Ces applications ont été conçues initialement pour s'exécuter en mode plein écran, bien que les utilisateurs de Windows 10 aient la possibilité de les exécuter dans une fenêtre du bureau. Elles intègrent des fonctions tactiles, mais il est facile d'utiliser la souris pour les faire fonctionner si les utilisateurs le préfèrent ou en l'absence d'un écran tactile. Ces applications sont distribuées à partir du Windows Store, ce qui a conduit à les appeler « applications du Windows Store ».

- [Applications et jeux de bureau, serveur et cloud](#BK_Native). Cette catégorie inclut les applications de bureau Windows, parfois appelées applications Win32 dans la mesure où ces applications utilisaient l'API Win32. Avant Windows 8, toutes les applications Windows figuraient dans cette catégorie. Les applications de cette catégorie peuvent utiliser MFC comme interface utilisateur et ATL pour interagir avec les composants Windows, qui sont en général des objets COM.

   Les applications, les composants et les bibliothèques écrits en C++ standard entrent également dans cette catégorie.

   Cette catégorie inclut également l'utilisation de C++ pour les composants principaux et le code de calcul dans le contexte de la programmation serveur et cloud. Parfois, le code exigeant en performances situé au cœur d'une application serveur ou cloud est écrit en C++ pour optimiser les performances. Vous pouvez compiler ce code dans une DLL et l'utiliser à partir de C# ou de Visual Basic.

- **Applications .NET Framework**. La plupart des applications .NET Framework sont écrites en C# ou Visual Basic, mais elles peuvent également l'être en C++/CLI (option de compilateur /clr dans Visual C++). Nous vous recommandons d'utiliser C++/CLI pour une couche d'interopérabilité minimale dans une application plus importante qui inclut du code managé et natif.

##  <a name="BK_WindowsUniversal"></a> Windows Universal Apps

Avec Windows 10, les applications peuvent s'exécuter sur tous les appareils Windows 10, tels que les tablettes et les téléphones mobiles, ainsi que sur le bureau. Sur le bureau, elles peuvent s'exécuter sous la forme d'une fenêtre du bureau au lieu de toujours s'exécuter en mode plein écran. Ces applications peuvent également s'exécuter sur la Xbox et sur les appareils futurs.  Le modèle de programmation utilisé pour ces deux types d'applications est différent de celui utilisé pour les applications de bureau Win32. Ces applications Windows s'exécutent sur le Windows Runtime, qui fournit les éléments d'interface utilisateur, les services essentiels pour ces applications, ainsi qu'une interface pour les divers périphériques matériels pris en charge. Ces applications sont compilées en code natif et possèdent une interface utilisateur XAML, ou utilisent DirectX. Vous pouvez également écrire des composants Windows Runtime en code natif qui consomment les autres applications Windows, notamment les applications qui sont écrites en c#, Visual Basic ou JavaScript. Pour plus d’informations, consultez [créer une application de plateforme Windows universelle en C++](http://go.microsoft.com/fwlink/p/?linkid=534976), [créer votre premier jeu de plateforme Windows universelle à l’aide de DirectX](http://go.microsoft.com/fwlink/p/?LinkId=244656), et [des composants de création de Windows Runtime en C++](http://go.microsoft.com/fwlink/p/?LinkId=244658).

> [!TIP]
> Pour Windows 10, vous pouvez utiliser le convertisseur d’application de bureau pour empaqueter votre application de bureau existante pour le déploiement via le Windows Store. Pour plus d’informations, consultez [Using Visual C++ Runtime in Centennial project](https://blogs.msdn.microsoft.com/vcblog/2016/07/07/using-visual-c-runtime-in-centennial-project) et [Déplacer votre application de bureau vers la plateforme universelle Windows (UWP) avec le pont du bureau](https://msdn.microsoft.com/en-us/windows/uwp/porting/desktop-to-uwp-root).

Pour obtenir des exemples pour la plateforme Windows universelle, consultez les [exemples Windows universels sur GitHub](https://github.com/Microsoft/Windows-universal-samples)

Si vous avez un projet de Windows 8.1 et voulez le porter vers Windows 10 existants, consultez [portage vers la plateforme Windows universelle](../porting/porting-to-the-universal-windows-platform-cpp.md). Si vous avez existant de bibliothèques de bureau Win32 classiques et le code que vous souhaitez intégrer dans une application UWP, consultez [Comment : utiliser le Code C++ existant dans une application de plateforme Windows universelle](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md).

Vous pouvez également écrire des applications Windows universelles, des jeux et des composants sans utiliser les C + c++ / CX ; au lieu de cela, vous pouvez utiliser la bibliothèque de modèles Windows Runtime C++ (bibliothèque de modèles Windows Runtime C++). Pour plus d’informations, consultez [bibliothèque de modèles Windows Runtime C++ (WRL)](../windows/windows-runtime-cpp-template-library-wrl.md).

Avec [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], vous pouvez développer des applications Windows universelles qui s'exécutent sur les appareils mobiles et de bureau dotés de Windows 10. Vous pouvez également développer des applications Windows 8.1 et Windows Phone 8.1 dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)]et, pour ce faire, vous devez commencer par installer Visual Studio 2013 sur le même ordinateur, puis configurer votre projet pour utiliser l'ensemble d'outils **Visual Studio 2013 (v120)** . Pour configurer ce paramètre dans votre projet, ouvrez les propriétés du projet et, dans la section **Général** , définissez **Ensemble d'outils de plateforme** sur **Visual Studio 2013 (v120)**.

Si vous installez les outils Phone 8.0 au cours de l'installation de Visual Studio, vous pouvez également cibler Windows Phone 8.0.

Un nouveau concept introduit dans Windows 10, appelé Contrats d'API, remplace l'ancienne pratique visant à cibler des versions spécifiques de Windows. À la place, vous pouvez choisir les contrats d'API dont votre application a besoin et elle pourra ensuite s'exécuter sur n'importe quel périphérique Windows qui prend en charge ces contrats. Un contrat d'API est un ensemble d'API stables qui permettent d'accéder à des ressources de plateforme ou de périphérique. Les contrats d'API peuvent être inclus en tant que références dans le système de projet. Dans un projet Visual Studio, si vous ajoutez une référence à un kit SDK d’extension particulier, Visual Studio ajoute les contrats d’API appropriés.

Pour plus d’informations sur l’ensemble de ces concepts, consultez [Guide pour les applications Windows universelles](http://go.microsoft.com/fwlink/p/?linkid=534605).

##  <a name="BK_Native"></a> Applications et jeux de bureau, serveur et Cloud

Dans le cloud, vous pouvez écrire des assemblys de code natif Azure en C++ et les appeler à partir de rôles Web créés en C#. Pour plus d’informations, consultez le [SDK Azure](http://go.microsoft.com/fwlink/p/?LinkId=256416).

Pour connaître les principes de base de la création d’applications clientes Windows pour le bureau, consultez [Developing Windows Applications in C++](http://msdn.microsoft.com/vstudio//hh304489) (Développement d’applications Windows utilisant C++) et [Introduction to Windows Programming in C++](http://msdn.microsoft.com/library/windows/desktop/ff381398\(v=vs.85\).aspx)(Introduction à la programmation Windows en C++).

Sur Windows 10, vous pouvez utiliser Visual C++ pour créer de nombreux types de programmes :

- Applications et utilitaires en ligne de commande. Pour plus d’informations, consultez [Applications Console](../windows/console-applications-in-visual-cpp.md).

- Jeux DirectX qui s'exécutent sur PC ou Xbox. Pour plus d’informations, consultez le [Centre de développement DirectX](http://go.microsoft.com/fwlink/p/?LinkId=256418).

- Applications grand public dotées d'interfaces graphiques utilisateur sophistiquées. Pour plus d’informations, consultez [Hilo: Developing C++ Applications for Windows](http://go.microsoft.com/fwlink/p/?LinkId=256417)(Hilo : développement d’applications C++ pour Windows)

- Applications d'entreprise et métier qui s'exécutent sur .NET Framework ou qui font office de pont entre les applications .NET Framework et les applications ou les composants écrits en code natif. Pour plus d’informations, consultez [programmation .NET avec C++ / CLI (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).

- Clients de base de données SQL qui s'exécutent en code natif. Pour plus d’informations, consultez [SQL Server Native Client](http://go.microsoft.com/fwlink/p/?LinkId=256419).

- Compléments pour les applications Microsoft Office. Pour plus d’informations, consultez [Génération d’un complément C++ pour Outlook 2010](http://go.microsoft.com/fwlink/p/?LinkId=256420)

- Pilotes de périphérique. Pour plus d’informations, consultez [Windows Driver Kit (WDK)](http://go.microsoft.com/fwlink/p/?LinkId=256421)

- Les services Windows. Pour plus d'informations, consultez [Introduction to Windows Service Applications](/dotnet/framework/windows-services/introduction-to-windows-service-applications).

Vous pouvez utiliser Visual C++ pour empaqueter quasiment tout type de fonctionnalité personnalisée à hautes performances dans des DLL Win32 ou dans des DLL COM qui peuvent être utilisées par les applications C++ ou par des applications écrites dans d'autres langages, tels que C# ou Visual Basic. Pour plus d’informations sur les DLL Win32, consultez [DLLs in Visual C++](../build/dlls-in-visual-cpp.md). Pour plus d’informations sur le développement COM, consultez [modèle COM (Component Object)](https://msdn.microsoft.com/library/windows/desktop/ms680573).

## <a name="sdks-and-header-files"></a>SDK et fichiers d'en-tête

Visual C++ inclut la bibliothèque Runtime C (CRT), de la bibliothèque Standard C++ et d’autres bibliothèques spécifiques de Microsoft. Les dossiers include qui contiennent les fichiers d’en-tête de ces bibliothèques sont situés soit dans le répertoire d’installation de Visual Studio dans le dossier \VC\, ou dans le cas le CRT, dossier d’installation du SDK Windows, par exemple, Windows Kits\10 dans vos fichiers de programme dossier pour le SDK Windows 10.  Les bibliothèques Microsoft incluent :

- Bibliothèque MFC (Microsoft Foundation Classes) : infrastructure orientée objet conçue pour la création de programmes Windows traditionnels (notamment des applications d’entreprise) qui possèdent des interfaces utilisateur riches dotées de boutons, de zones de liste, d’arborescences et d’autres contrôles. Pour plus d'informations, consultez [MFC Desktop Applications](../mfc/mfc-desktop-applications.md).

- Bibliothèque ATL (Active Template Library) : bibliothèque d'assistance puissante pour créer des composants COM. Pour plus d'informations, consultez [ATL COM Desktop Components](../atl/atl-com-desktop-components.md).

- C++ AMP (C++ Accelerated Massive Parallelism) : bibliothèque qui permet un travail de calcul général à hautes performances sur le GPU. Pour plus d'informations, consultez [C++ AMP (C++ Accelerated Massive Parallelism)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md).

- Runtime d'accès concurrentiel : bibliothèque qui simplifie le travail de programmation parallèle et asynchrone pour les appareils dotés de plusieurs cœurs, voire de nombreux cœurs. Pour plus d'informations, consultez [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md).

De nombreux scénarios de programmation Windows requièrent également le Kit de développement logiciel Windows, qui inclut les fichiers d'en-tête qui permettent l'accès aux composants du système d'exploitation Windows. Par défaut, Visual Studio installe le Kit de développement logiciel Windows, qui permet le développement d’applications Windows universelles. Pour développer des applications Windows universelles pour Windows 10, vous avez besoin de la version Windows 10 du Kit de développement logiciel (SDK) Windows. Pour plus d’informations sur le SDK Windows 10, consultez [SDK Windows 10](https://dev.windows.com/downloads/windows-10-sdk). (Pour plus d’informations sur les kits de développement logiciel Windows pour les versions antérieures de Windows, consultez le [archive du Kit de développement logiciel Windows](https://developer.microsoft.com/windows/downloads/sdk-archive)).

D'autres plateformes, telles que Xbox et Azure, possèdent leurs propres Kits de développement logiciel que vous pouvez être amené à installer. Pour plus d'informations, consultez le Centre de développement DirectX et le Centre de développement Azure.

## <a name="development-tools"></a>Outils de développement

Visual Studio inclut un débogueur puissant pour le code natif, des outils d’analyse statique, des outils de débogage graphique, un éditeur de code complet, la prise en charge des tests unitaires et de nombreux autres outils et utilitaires. Pour plus d’informations, consultez [prise en main du développement avec Visual Studio](/visualstudio/ide/get-started-developing-with-visual-studio), et [IDE et outils de développement](../ide/ide-and-tools-for-visual-cpp-development.md).

## <a name="related-articles"></a>Articles connexes

|Titre|Description|
|-----------|-----------------|
|[Visual C++](../visual-cpp-in-visual-studio.md)|Rubrique parente pour le contenu du développeur Visual C++.|