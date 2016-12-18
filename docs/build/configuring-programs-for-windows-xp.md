---
title: "Configuration des programmes C++ 11 pour Windows XP | Microsoft Docs"
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
ms.assetid: 1e4487b3-d815-4123-878b-5718b22f0fd5
caps.latest.revision: 14
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Configuration des programmes C++ 11 pour Windows XP
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Comme [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] prend en charge plusieurs ensembles d'outils de plateforme, vous pouvez cibler les systèmes d'exploitation et les bibliothèques Runtime qui ne sont pas pris en charge par l'ensemble d'outils par défaut.  Par exemple, vous pouvez utiliser les améliorations du langage C\+\+11, les compilateurs, les bibliothèques et autres fonctionnalités implémentées dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] pour créer des applications qui ciblent [!INCLUDE[winxp](../build/includes/winxp_md.md)] et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  Vous pouvez utiliser des ensembles d'outils de plateforme plus anciens pour maintenir le code hérité compatible binaire et continuer à tirer parti des dernières fonctionnalités de l'IDE [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
> [!NOTE]
>  Vous devez installer la mise à jour 4 de [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] afin d'ajouter la prise en charge d'ensembles d'outils de plateforme pour [!INCLUDE[winxp](../build/includes/winxp_md.md)] et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] à [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)].  Pour télécharger et installer une copie de la mise à jour 4 de [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)], consultez [Microsoft Visual Studio Express 2012 pour Windows Desktop](http://go.microsoft.com/fwlink/?LinkID=265464) dans le Centre de téléchargement Microsoft.  Puis, installez [Visual Studio 2012 Update 4](http://go.microsoft.com/fwlink/?LinkID=335900) pour obtenir l'ensemble d'outils de plateforme v110\_xp.  Utilisez Windows Update pour recevoir les dernières mises à jour logicielles après l'installation.  
  
## Ciblage de Windows XP  
 L'ensemble d'outils de plateforme Windows XP fourni dans [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] est une version du Kit de développement logiciel \(SDK\) [!INCLUDE[win7](../build/includes/win7_md.md)] inclus dans [!INCLUDE[vs_dev10_long](../build/includes/vs_dev10_long_md.md)], mais il utilise le compilateur C\+\+ actuel.  Il configure également les propriétés du projet avec les valeurs par défaut appropriées : par exemple, la spécification d'un éditeur de liens compatible pour le ciblage de bas niveau.  Seules les applications de bureau Windows créées avec l'ensemble d'outils de plateforme Windows XP s'exécutent sur [!INCLUDE[winxp](../build/includes/winxp_md.md)] et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], mais ces applications peuvent aussi s'exécuter sur des systèmes d'exploitation plus récents \(par exemple, Windows Vista, [!INCLUDE[win7](../build/includes/win7_md.md)], [!INCLUDE[winsvr08](../build/includes/winsvr08_md.md)], [!INCLUDE[win8](../build/includes/win8_md.md)] ou [!INCLUDE[winserver8](../build/includes/winserver8_md.md)]\).  
  
#### Pour cibler Windows XP  
  
1.  Dans l'**Explorateur de solutions**, ouvrez le menu contextuel de votre projet et choisissez **Propriétés**.  
  
2.  Dans la boîte de dialogue **Pages de propriétés** du projet, sous **Propriétés de configuration**, **Général**, définissez la propriété **Ensemble d'outils de plateforme** avec l'ensemble d'outils Windows XP souhaité.  Par exemple, choisissez **Visual Studio 2012 – Windows XP \(v110\_xp\)** pour créer un code compatible binaire avec les bibliothèques Microsoft Visual C\+\+ 2012 Redistributable.  
  
### Prise en charge du runtime C\+\+  
 Avec l'ensemble d'outils de plateforme Windows XP, la bibliothèque Runtime C \(CRT\), la bibliothèque STL \(Standard Template Library\), la bibliothèque ATL \(Active Template\), la bibliothèque du runtime d'accès concurrentiel \(ConCRT\), la bibliothèque de modèles parallèles \(PPL\), la bibliothèque MFC \(Microsoft Foundation Class\) et la bibliothèque C\+\+ AMP \(C\+\+ Accelerated Massive Programming\) incluent la prise en charge du runtime pour [!INCLUDE[winxp](../build/includes/winxp_md.md)] et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  Pour ces systèmes d'exploitation, les versions prises en charge sont [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 3 \(SP3\) pour x86, [!INCLUDE[winxp](../build/includes/winxp_md.md)] Service Pack 2 \(SP2\) pour x64 et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)] Service Pack 2 \(SP2\) pour x86 et x64.  
  
 Ces bibliothèques sont prises en charge par les ensembles d'outils de plateforme installés par [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)], en fonction de la cible :  
  
|Bibliothèque|Ensemble d'outils de plateforme par défaut ciblant les applications de bureau Windows|Ensemble d'outils de plateforme par défaut ciblant les applications [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]|Ensemble d'outils de plateforme Windows XP ciblant [!INCLUDE[winxp](../build/includes/winxp_md.md)], [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]|  
|------------------|-------------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------|  
|CRT|X|X|X|  
|STL|X|X|X|  
|ATL|X|X|X|  
|ConCRT\/PPL|X|X|X|  
|MFC|X||X|  
|C\+\+ AMP|X|X||  
  
> [!NOTE]
>  Les applications écrites en C\+\+\/CLI et qui ciblent le .NET Framework 4 s'exécutent sur [!INCLUDE[winxp](../build/includes/winxp_md.md)] et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  
  
### Différences entre les ensembles d'outils  
 En raison de différences de prise en charge de plateforme et de bibliothèque, l'expérience de développement pour les applications qui utilisent un ensemble d'outils de plateforme Windows XP n'est pas aussi complète que pour les applications qui utilisent l'ensemble d'outils de plateforme par défaut [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)].  
  
-   **Fonctionnalités du langage C\+\+**  
  
     Seules les fonctionnalités du langage C\+\+11 implémentées dans [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] sont prises en charge dans les applications qui utilisent l'ensemble d'outils de plateforme v110\_xp.  Seules les fonctionnalités C\+\+11 implémentées dans [!INCLUDE[vs_dev12](../atl-mfc-shared/includes/vs_dev12_md.md)] sont prises en charge dans les applications qui utilisent l'ensemble d'outils de plateforme v120\_xp.  [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] utilise le compilateur correspondant lors du développement à l'aide d'ensembles d'outils de plateforme plus anciens.  Utilisez un ensemble d'outils de plateforme Windows XP plus récent pour tirer parti des fonctionnalités C\+\+11 additionnelles implémentées dans cette version.  
  
-   **Débogage distant**  
  
     Les outils de contrôle à distance de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] ne prennent pas en charge le débogage distant sur [!INCLUDE[winxp](../build/includes/winxp_md.md)] ou [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  Pour déboguer une application lorsqu'elle s'exécute sur [!INCLUDE[winxp](../build/includes/winxp_md.md)] ou [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], vous pouvez utiliser un débogueur à partir d'une version antérieure de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] pour un débogage local ou à distance.  L'expérience s'apparente à celle du débogage d'une application sur Windows Vista, qui est une cible d'exécution de l'ensemble d'outils de plateforme, mais pas une cible du débogage distant.  
  
-   **Analyse statique**  
  
     Les ensembles d'outils de plateforme Windows XP ne prennent pas en charge l'analyse statique, car les annotations SAL pour le Kit de développement logiciel \(SDK\) [!INCLUDE[win7](../build/includes/win7_md.md)] et les bibliothèques Runtime ne sont pas compatibles.  Lorsque vous souhaitez effectuer une analyse statique sur une application qui prend en charge [!INCLUDE[winxp](../build/includes/winxp_md.md)] ou [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)], vous pouvez basculer temporairement la solution afin de cibler l'ensemble d'outils de plateforme par défaut et d'effectuer l'analyse, puis revenir à l'ensemble d'outils de plateforme Windows XP pour générer l'application.  
  
-   **Débogage de DirectX Graphics**  
  
     Comme le débogueur Graphics ne prend pas en charge l'API Direct3D 9, il ne peut pas être utilisé pour déboguer les applications qui utilisent Direct3D sur [!INCLUDE[winxp](../build/includes/winxp_md.md)] ou [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)].  Cependant, si l'application implémente un autre convertisseur qui utilise les API Direct3D 10 ou Direct3D 11, le débogueur Graphics peut être utilisé pour diagnostiquer les problèmes liés à l'utilisation de ces API.  
  
-   **Développement HLSL**  
  
     Par défaut, l'ensemble d'outils Windows XP ne compile pas les fichiers de code source HLSL.  Pour compiler les fichiers HLSL, téléchargez et installez le Kit de développement logiciel \(SDK\) DirectX de juin 2010, puis définissez les répertoires VC du projet de façon à l'inclure.  Pour plus d'informations, consultez la section « SDK DirectX n'inscrit pas les chemins d'accès Include\/Bibliothèque avec Visual Studio 2010 » de la [page de téléchargement du Kit de développement logiciel \(SDK\) DirectX de juin 2010](http://www.microsoft.com/download/details.aspx?displaylang=en&id=6812).