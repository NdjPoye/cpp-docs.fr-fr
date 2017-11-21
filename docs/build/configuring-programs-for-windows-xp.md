---
title: Configuration des programmes pour Windows XP | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b92eb646b152a7bbd4588fe953a762389ce111dc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="configuring-programs-for-windows-xp"></a>Configuration des programmes pour Windows XP
Étant donné que Visual Studio prend en charge plusieurs ensembles d’outils de plateforme, vous pouvez cibler des systèmes d’exploitation et les bibliothèques runtime qui ne sont pas pris en charge par l’ensemble d’outils par défaut. Par exemple, en basculant l’ensemble d’outils de plateforme, vous pouvez utiliser C ++ 11, C ++ 14 et améliorations du langage C ++ 17 pris en charge par le compilateur Visual C++ dans Visual Studio pour créer des applications qui ciblent [!INCLUDE[winxp](../build/includes/winxp_md.md)] et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Vous pouvez également utiliser des ensembles d’outils de plateforme plus anciens pour maintenir le code hérité compatible binaire et tirer parti des fonctionnalités plus récentes de l’IDE de Visual Studio.  
  
> [!NOTE]
>  Si vous utilisez [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)], vous devez installer [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] mise à jour 4 pour ajouter la prise en charge des ensemble d’outils de plateforme de [!INCLUDE[winxp](../build/includes/winxp_md.md)] et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Pour télécharger et installer une copie de [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] mise à jour 4, consultez [Microsoft Visual Studio Express 2012 pour Windows Desktop](http://go.microsoft.com/fwlink/?LinkID=265464) dans du Microsoft Download Center. Puis installez [Visual Studio 2012 Update 4](http://go.microsoft.com/fwlink/?LinkID=335900) pour obtenir l’ensemble d’outils de plateforme v110_xp. Utilisez Windows Update pour recevoir les dernières mises à jour logicielles après l'installation.  
  
## <a name="windows-xp-targeting-experience"></a>Ciblage de Windows XP  
 L’ensemble d’outils de plateforme Windows XP qui est inclus dans Visual Studio est une version de la [!INCLUDE[win7](../build/includes/win7_md.md)] Kit de développement logiciel qui a été inclus dans [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)], mais elle utilise le compilateur C++ actuel. Il configure également les propriétés du projet avec les valeurs par défaut appropriées : par exemple, la spécification d'un éditeur de liens compatible pour le ciblage de bas niveau. Windows uniquement les applications de bureau qui sont créées à l’aide de l’ensemble d’outils de plateforme Windows XP s’exécutent sur [!INCLUDE[winxp](../build/includes/winxp_md.md)] et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], mais ces applications peuvent également s’exécuter sur les systèmes d’exploitation Windows plus récentes.  
  
#### <a name="to-target-windows-xp"></a>Pour cibler Windows XP  
  
1.  Dans l’**Explorateur de solutions**, ouvrez le menu contextuel de votre projet et choisissez **Propriétés**.  
  
2.  Dans le **Pages de propriétés** boîte de dialogue pour le projet, sous **propriétés de Configuration**, **général**, définissez le **ensemble d’outils de plateforme** propriété à l’ensemble d’outils Windows XP souhaité. Par exemple, choisir **Visual Studio 2015 - Windows XP (v140_xp)** pour créer le code pour [!INCLUDE[winxp](../build/includes/winxp_md.md)] et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] en utilisant le compilateur Microsoft Visual C++ 2015.  
  
### <a name="c-runtime-support"></a>Prise en charge du runtime C++  
 Avec l’ensemble d’outils de plateforme Windows XP, la bibliothèque de Runtime C (CRT), bibliothèque Standard C++, bibliothèque ATL (Active Template), la bibliothèque Runtime d’accès concurrentiel (ConCRT), bibliothèque de modèles parallèles (PPL), MFC Microsoft Foundation Class Library () et C++ AMP (C++ Accelerated Massive programmation) bibliothèque incluent la prise en charge du runtime pour [!INCLUDE[winxp](../build/includes/winxp_md.md)] et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Pour ces systèmes d’exploitation, les versions prises en charge minimales sont [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 3 (SP3) pour x86, [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 2 (SP2) pour x64, et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Service Pack 2 (SP2) pour x86 et x64.  
  
 Ces bibliothèques sont prises en charge par les ensembles d’outils de plateforme installés par Visual Studio, en fonction de la cible :  
  
|Bibliothèque|Ensemble d'outils de plateforme par défaut ciblant les applications de bureau Windows|Ensemble d'outils de plateforme par défaut ciblant les applications [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]|Ensemble d'outils de plateforme Windows XP ciblant [!INCLUDE[winxp](../build/includes/winxp_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]|  
|-------------|-------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------|  
|CRT|X|X|X|  
|Bibliothèque standard C++|X|X|X|  
|ATL|X|X|X|  
|ConCRT/PPL|X|X|X|  
|MFC|X||X|  
|C++ AMP|X|X||  
  
> [!NOTE]
>  Les applications écrites en C++/CLI et qui ciblent le .NET Framework 4 s'exécutent sur [!INCLUDE[winxp](../build/includes/winxp_md.md)] et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  
  
### <a name="differences-between-the-toolsets"></a>Différences entre les ensembles d'outils  
 En raison de différences de prise en charge de plateforme et de bibliothèque, l’expérience de développement d’applications qui utilisent un ensemble d’outils de plateforme Windows XP n’est pas aussi complète que pour les applications qui utilisent l’ensemble d’outils de plateforme de Visual Studio par défaut.  
  
-   **Fonctionnalités du langage C++**  
  
     Fonctionnalités du langage C++ uniquement implémentées dans [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] sont pris en charge dans les applications qui utilisent l’ensemble d’outils de plateforme v110_xp. Fonctionnalités du langage C++ uniquement implémentées dans [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] sont pris en charge dans les applications qui utilisent l’ensemble d’outils de plateforme v120_xp. Visual Studio utilise le compilateur correspondant lors de la génération à l’aide des ensembles d’outils de plateforme plus anciens. Utilisez l’ensemble d’outils de plateforme Windows XP plus récent pour tirer parti des fonctionnalités du langage C++ supplémentaires implémentées dans cette version du compilateur.  
  
-   **Débogage distant**  
  
     Les outils à distance pour Visual Studio ne prend pas en charge le débogage distant sur [!INCLUDE[winxp](../build/includes/winxp_md.md)] ou [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Pour déboguer une application lorsqu’elle s’exécute sur [!INCLUDE[winxp](../build/includes/winxp_md.md)] ou [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], vous pouvez utiliser un débogueur à partir d’une version antérieure de Visual Studio pour le déboguer localement ou à distance. L'expérience s'apparente à celle du débogage d'une application sur Windows Vista, qui est une cible d'exécution de l'ensemble d'outils de plateforme, mais pas une cible du débogage distant.  
  
-   **Analyse statique**  
  
     Les ensembles d'outils de plateforme Windows XP ne prennent pas en charge l'analyse statique, car les annotations SAL pour le Kit de développement logiciel (SDK) [!INCLUDE[win7](../build/includes/win7_md.md)] et les bibliothèques Runtime ne sont pas compatibles. Lorsque vous souhaitez effectuer une analyse statique sur une application qui prend en charge [!INCLUDE[winxp](../build/includes/winxp_md.md)] ou [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], vous pouvez basculer temporairement la solution afin de cibler l'ensemble d'outils de plateforme par défaut et d'effectuer l'analyse, puis revenir à l'ensemble d'outils de plateforme Windows XP pour générer l'application.  
  
-   **Débogage de DirectX graphics**  
  
     Comme le débogueur Graphics ne prend pas en charge l'API Direct3D 9, il ne peut pas être utilisé pour déboguer les applications qui utilisent Direct3D sur [!INCLUDE[winxp](../build/includes/winxp_md.md)] ou [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Cependant, si l'application implémente un autre convertisseur qui utilise les API Direct3D 10 ou Direct3D 11, le débogueur Graphics peut être utilisé pour diagnostiquer les problèmes liés à l'utilisation de ces API.  
  
-   **Développement HLSL**  
  
     Par défaut, l’ensemble d’outils Windows XP ne compile pas les fichiers de code source HLSL. Pour compiler les fichiers HLSL, téléchargez et installez le Kit de développement logiciel (SDK) DirectX de juin 2010, puis définissez les répertoires VC du projet de façon à l'inclure. Pour plus d’informations, consultez le « SDK DirectX n’inscrit pas chemins d’accès Include/bibliothèque avec Visual Studio 2010 « section de la [juin 2010 page de téléchargement du SDK DirectX](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).