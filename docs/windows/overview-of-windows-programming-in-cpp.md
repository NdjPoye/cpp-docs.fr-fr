---
title: "Vue d&#39;ensemble de la programmation Windows en C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: efc691d7-21f3-47ae-ae56-cab999ccf59d
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Vue d&#39;ensemble de la programmation Windows en C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser Visual C\+\+ pour écrire une large gamme de programmes qui s'exécutent sur un PC Windows \(x86, x64 ou ARM\), sur un serveur Windows, dans le cloud ou sur Xbox. Les programmes C\+\+ bien écrits sont rapides, efficaces, économes en énergie et capables de tirer pleinement profit d'appareils dotés de plusieurs cœurs, voire de nombreux cœurs, du calcul générique sur processeur graphique \(GPGPU\) et d'autres avancées récentes dans le domaine du matériel informatique.  
  
 Il existe plusieurs grandes catégories d'applications Windows que vous pouvez développer avec Visual C\+\+. Ces catégories ont des modèles de programmation différents ou des modèles d'application, ce qui signifie qu'elles utilisent différentes bibliothèques et API qui permettent d'accéder à la plateforme et fournissent une interface utilisateur.  
  
-   [Applications Windows universelles](#BK_WindowsUniversal). La troisième catégorie d'applications Windows a été introduite avec Windows 8 et la prise en charge de cette catégorie continue dans Windows 10. Ces applications sont souvent appelées simplement « applications Windows » et elles incluent des applications mobiles et de bureau qui ciblent divers appareils. Vous pouvez écrire ces applications en C\+\+\/CX, un dialecte de C\+\+ qui inclut la prise en charge du développement Windows Runtime, ou en C\+\+ standard avec COM qui utilise la bibliothèque WRL \(Windows Runtime Library\). Ces applications ont été conçues initialement pour s'exécuter en mode plein écran, bien que les utilisateurs de Windows 10 aient la possibilité de les exécuter dans une fenêtre du bureau. Elles intègrent des fonctions tactiles, mais il est facile d'utiliser la souris pour les faire fonctionner si les utilisateurs le préfèrent ou en l'absence d'un écran tactile. Ces applications sont distribuées à partir du Windows Store, ce qui a conduit à les appeler « applications du Windows Store ».  
  
-   [Applications et jeux de bureau, serveur et cloud](#BK_Native). Cette catégorie inclut les applications de bureau Windows, parfois appelées applications Win32 dans la mesure où ces applications utilisaient l'API Win32. Avant Windows 8, toutes les applications Windows figuraient dans cette catégorie. Les applications de cette catégorie peuvent utiliser MFC comme interface utilisateur et ATL pour interagir avec les composants Windows, qui sont en général des objets COM.  
  
     Les applications, les composants et les bibliothèques écrits en C\+\+ standard entrent également dans cette catégorie.  
  
     Cette catégorie inclut également l'utilisation de C\+\+ pour les composants principaux et le code de calcul dans le contexte de la programmation serveur et cloud. Parfois, le code exigeant en performances situé au cœur d'une application serveur ou cloud est écrit en C\+\+ pour optimiser les performances. Vous pouvez compiler ce code dans une DLL et l'utiliser à partir de C\# ou de Visual Basic.  
  
-   **Applications .NET Framework**. La plupart des applications .NET Framework sont écrites en C\# ou Visual Basic, mais elles peuvent également l'être en C\+\+\/CLI \(option de compilateur \/clr dans Visual C\+\+\). Nous vous recommandons d'utiliser C\+\+\/CLI pour une couche d'interopérabilité minimale dans une application plus importante qui inclut du code managé et natif.  
  
##  <a name="BK_WindowsUniversal"></a> Applications Windows universelles  
 Avec Windows 10, les applications peuvent s'exécuter sur tous les appareils Windows 10, tels que les tablettes et les téléphones mobiles, ainsi que sur le bureau. Sur le bureau, elles peuvent s'exécuter sous la forme d'une fenêtre du bureau au lieu de toujours s'exécuter en mode plein écran. Ces applications peuvent également s'exécuter sur la Xbox et sur les appareils futurs.  Le modèle de programmation utilisé pour ces deux types d'applications est différent de celui utilisé pour les applications de bureau Win32. Ces applications Windows s'exécutent sur le Windows Runtime, qui fournit les éléments d'interface utilisateur, les services essentiels pour ces applications, ainsi qu'une interface pour les divers périphériques matériels pris en charge. Ces applications sont compilées en code natif et possèdent une interface utilisateur XAML, ou utilisent DirectX. Vous pouvez également écrire les composants [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] en code natif que les autres applications Windows peuvent exploiter, telles que des applications écrites en C\#, Visual Basic ou JavaScript. Pour plus d’informations, consultez [Créer votre première application du Windows Store en C\+\+](http://go.microsoft.com/fwlink/?LinkID=534976), [Create your first Windows Store game using DirectX](http://go.microsoft.com/fwlink/p/?LinkId=244656) \(Créer votre premier jeu du Windows Store utilisant DirectX\) et [Création de composants Windows Runtime en C\+\+](http://go.microsoft.com/fwlink/p/?LinkId=244658).  
  
 Pour obtenir des exemples pour la plateforme Windows universelle, consultez les [exemples Windows universels sur GitHub](https://github.com/Microsoft/Windows-universal-samples)  
  
 Si vous souhaitez porter un projet Windows 8.1 existant vers Windows 10, consultez [Portage vers la plateforme Windows universelle](../porting/porting-to-the-universal-windows-platform-cpp.md). Si vous souhaitez intégrer des bibliothèques et du code Win32 de bureau classiques dans une application UWP, consultez [Comment : utiliser le code C\+\+ existant dans une application pour la plateforme Windows universelle](../porting/how-to-use-existing-cpp-code-in-a-universal-windows-platform-app.md).  
  
 Vous pouvez également écrire des applications, des jeux et des composants Windows universels sans utiliser les [!INCLUDE[cppwrt](../build/reference/includes/cppwrt_md.md)] \([!INCLUDE[cppwrt_short](../build/reference/includes/cppwrt_short_md.md)]\). À la place, vous pouvez utiliser la [!INCLUDE[cppwrl](../windows/includes/cppwrl_md.md)] \([!INCLUDE[cppwrl_short](../windows/includes/cppwrl_short_md.md)]\). Pour plus d'informations, consultez [Bibliothèque de modèles Windows Runtime C\+\+ \(WRL\)](../windows/windows-runtime-cpp-template-library-wrl.md).  
  
 Avec [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)], vous pouvez développer des applications Windows universelles qui s'exécutent sur les appareils mobiles et de bureau dotés de Windows 10. Vous pouvez également développer des applications Windows 8.1 et Windows Phone 8.1 dans [!INCLUDE[cpp_dev14_long](../porting/includes/cpp_dev14_long_md.md)] et, pour ce faire, vous devez commencer par installer Visual Studio 2013 sur le même ordinateur, puis configurer votre projet pour utiliser l'ensemble d'outils **Visual Studio 2013 \(v120\)**. Pour configurer ce paramètre dans votre projet, ouvrez les propriétés du projet et, dans la section **Général**, définissez **Ensemble d'outils de plateforme** sur **Visual Studio 2013 \(v120\)**.  
  
 Si vous installez les outils Phone 8.0 au cours de l'installation de Visual Studio, vous pouvez également cibler Windows Phone 8.0.  
  
 Un nouveau concept introduit dans Windows 10, appelé Contrats d'API, remplace l'ancienne pratique visant à cibler des versions spécifiques de Windows. À la place, vous pouvez choisir les contrats d'API dont votre application a besoin et elle pourra ensuite s'exécuter sur n'importe quel périphérique Windows qui prend en charge ces contrats. Un contrat d'API est un ensemble d'API stables qui permettent d'accéder à des ressources de plateforme ou de périphérique. Les contrats d'API peuvent être inclus en tant que références dans le système de projet. Dans un projet Visual Studio, si vous ajoutez une référence à un kit SDK d’extension particulier, Visual Studio ajoute les contrats d’API appropriés.  
  
 Pour plus d’informations sur l’ensemble de ces concepts, consultez [Guide des applications de plateforme Windows universelle](http://go.microsoft.com/fwlink/?LinkId=534605).  
  
##  <a name="BK_Win32"></a> Applications et jeux de bureau, serveur et Cloud  
 Dans le cloud, vous pouvez écrire des assemblys de code natif Azure en C\+\+ et les appeler à partir de rôles Web créés en C\#. Pour plus d’informations, consultez le [SDK Azure](http://go.microsoft.com/fwlink/p/?LinkId=256416).  
  
 Pour connaître les principes de base de la création d’applications clientes Windows pour le bureau, consultez [Developing Windows Applications in C\+\+](http://msdn.microsoft.com/vstudio//hh304489) \(Développement d’applications Windows utilisant C\+\+\) et [Introduction to Windows Programming in C\+\+](http://msdn.microsoft.com/library/windows/desktop/ff381398\(v=vs.85\).aspx) \(Introduction à la programmation Windows en C\+\+\).  
  
 Sur Windows 10, vous pouvez utiliser Visual C\+\+ pour créer de nombreux types de programmes :  
  
-   Applications et utilitaires en ligne de commande. Pour plus d'informations, consultez [Applications console](../windows/console-applications-in-visual-cpp.md).  
  
-   Jeux DirectX qui s'exécutent sur PC ou Xbox. Pour plus d’informations, consultez le [Centre de développement DirectX](http://go.microsoft.com/fwlink/p/?LinkId=256418).  
  
-   Applications grand public dotées d'interfaces graphiques utilisateur sophistiquées. Pour plus d’informations, consultez [Hilo: Developing C\+\+ Applications for Windows](http://go.microsoft.com/fwlink/p/?LinkId=256417) \(Hilo : développement d’applications C\+\+ pour Windows\)  
  
-   Applications d'entreprise et métier qui s'exécutent sur .NET Framework ou qui font office de pont entre les applications .NET Framework et les applications ou les composants écrits en code natif. Pour plus d'informations, consultez [Programmation .NET avec C\+\+\/CLI](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md).  
  
-   Clients de base de données SQL qui s'exécutent en code natif. Pour plus d’informations, consultez [SQL Server Native Client](http://go.microsoft.com/fwlink/p/?LinkId=256419).  
  
-   Compléments pour les applications Microsoft Office. Pour plus d’informations, consultez [Génération d’un complément C\+\+ pour Outlook 2010](http://go.microsoft.com/fwlink/p/?LinkId=256420)  
  
-   Pilotes de périphérique. Pour plus d’informations, consultez [Windows Driver Kit \(WDK\)](http://go.microsoft.com/fwlink/p/?LinkId=256421)  
  
-   Les services Windows. Pour plus d'informations, consultez [Introduction to Windows Service Applications](../Topic/Introduction%20to%20Windows%20Service%20Applications.md).  
  
 Vous pouvez utiliser Visual C\+\+ pour empaqueter quasiment tout type de fonctionnalité personnalisée à hautes performances dans des DLL Win32 ou dans des DLL COM qui peuvent être utilisées par les applications C\+\+ ou par des applications écrites dans d'autres langages, tels que C\# ou Visual Basic. Pour plus d’informations sur les DLL Win32, consultez [DLL en Visual C\+\+](../build/dlls-in-visual-cpp.md). Pour plus d’informations sur le développement COM, consultez [Component Object Model \(COM\)](http://msdn.microsoft.com/fr-fr/375d29a7-a1f3-4bd8-8621-bad7a049b2aa).  
  
## SDK et fichiers d'en\-tête  
 Visual C\+\+ inclut les bibliothèques C et C\+\+ standard, la bibliothèque STL \(Standard Template Library\) et d'autres bibliothèques spécifiques de Microsoft. Les dossiers include qui contiennent les fichiers d'en\-tête de ces bibliothèques sont situés soit dans le répertoire d'installation de Visual Studio, dans le dossier \\VC\\, soit, dans le cas de la Bibliothèque Runtime C \(CRT\), dans le dossier d'installation du kit SDK Windows, par exemple, Windows Kits\\10 dans votre dossier Program Files pour le Kit de développement logiciel \(SDK\) Windows 10.  Les bibliothèques Microsoft incluent :  
  
-   Bibliothèque MFC \(Microsoft Foundation Classes\) : infrastructure orientée objet conçue pour la création de programmes Windows traditionnels \(notamment des applications d’entreprise\) qui possèdent des interfaces utilisateur riches dotées de boutons, de zones de liste, d’arborescences et d’autres contrôles. Pour plus d'informations, consultez [MFC, applications de bureau](../mfc/mfc-desktop-applications.md).  
  
-   Bibliothèque ATL \(Active Template Library\) : bibliothèque d'assistance puissante pour créer des composants COM. Pour plus d'informations, consultez [ATL COM Desktop Components](../atl/atl-com-desktop-components.md).  
  
-   C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\) : bibliothèque qui permet un travail de calcul général à hautes performances sur le GPU. Pour plus d'informations, consultez [C\+\+ AMP \(C\+\+ Accelerated Massive Parallelism\)](../parallel/amp/cpp-amp-cpp-accelerated-massive-parallelism.md).  
  
-   Runtime d'accès concurrentiel : bibliothèque qui simplifie le travail de programmation parallèle et asynchrone pour les appareils dotés de plusieurs cœurs, voire de nombreux cœurs. Pour plus d'informations, consultez [Concurrency Runtime](../parallel/concrt/concurrency-runtime.md).  
  
 De nombreux scénarios de programmation Windows requièrent également le Kit de développement logiciel Windows, qui inclut les fichiers d'en\-tête qui permettent l'accès aux composants du système d'exploitation Windows. Par défaut, toutes les éditions de [!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] installent le Kit de développement logiciel \(SDK\) Windows, qui permet le développement d'applications Windows universelles. Pour développer des applications Windows universelles pour Windows 10, vous avez besoin de la version Windows 10 du Kit de développement logiciel \(SDK\) Windows. Pour plus d’informations sur le SDK Windows 10, consultez [SDK Windows 10](http://go.microsoft.com/fwlink/p/?LinkId=534603). \(Pour plus d’informations sur les SDK Windows de versions antérieures, consultez [Overview of the Windows SDK](../Topic/Overview%20of%20the%20Windows%20SDK.md).\)  
  
 D'autres plateformes, telles que Xbox et Azure, possèdent leurs propres Kits de développement logiciel que vous pouvez être amené à installer. Pour plus d'informations, consultez le Centre de développement DirectX et le Centre de développement Azure.  
  
## Outils de développement  
 Visual Studio inclut un débogueur puissant pour le code natif, des outils d’analyse statique, des outils de débogage graphique, un éditeur de code complet, la prise en charge des tests unitaires et de nombreux autres outils et utilitaires. Pour plus d’informations, consultez [Développement d’applications dans Visual Studio](http://msdn.microsoft.com/fr-fr/97490c1b-a247-41fb-8f2c-bc4c201eff68) et [IDE et outils de développement](../ide/ide-and-tools-for-visual-cpp-development.md).  
  
## Articles connexes  
  
|Titre|Description|  
|-----------|-----------------|  
|[Visual C\+\+](../top/visual-cpp-in-visual-studio-2015.md)|Rubrique parente pour le contenu MSDN Library consacré à C\+\+.|