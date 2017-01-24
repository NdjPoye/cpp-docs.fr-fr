---
title: "G&#233;n&#233;ral, page de propri&#233;t&#233;s (Projet) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCConfiguration.IntermediateDirectory"
  - "VC.Project.VCConfiguration.ConfigurationType"
  - "VC.Project.VCConfiguration.ManagedExtensions"
  - "VC.Project.VCConfiguration.BuildBrowserInformation"
  - "VC.Project.VCConfiguration.BuildLogFile"
  - "VC.Project.VCConfiguration.PlatformToolset"
  - "VC.Project.VCConfiguration.TargetName"
  - "VC.Project.VCConfiguration."
  - "VC.Project.VCConfiguration.TargetExt"
  - "VC.Project.VCConfiguration.ATLMinimizesCRunTimeLibraryUsage"
  - "VC.Project.VCConfiguration.ReferencesPath"
  - "VC.Project.VCConfiguration.DeleteExtensionsOnClean"
  - "VC.Project.VCConfiguration.useOfMfc"
  - "VC.Project.VCConfiguration.CharacterSet"
  - "VC.Project.VCGeneralMakefileSettings.ConfigurationType"
  - "VC.Project.VCConfiguration.OutputDirectory"
  - "VC.Project.VCConfiguration.AppSupport"
  - "VC.Project.VCConfiguration.ToolFiles"
  - "VC.Project.VCConfiguration.useOfATL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Nettoyer (option du menu Générer)"
  - "fichiers de sortie, définition du répertoire"
  - "Unicode, création de la configuration de build C++"
ms.assetid: 593b383c-cd0f-4dcd-ad65-9ec9b4b19c45
caps.latest.revision: 30
caps.handback.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# G&#233;n&#233;ral, page de propri&#233;t&#233;s (Projet)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand vous cliquez avec le bouton droit sur un nœud de projet dans l'Explorateur de solutions et que vous sélectionnez **Propriétés**, la page de propriétés **Général** sous le nœud **Propriétés de configuration** dans le volet gauche affiche deux sections de propriétés :  
  
-   Général  
  
-   Paramètres par défaut du projet  
  
## Général  
 Les propriétés de la section Général affectent l'emplacement des fichiers qui sont créés lors du processus de génération et les fichiers à supprimer quand l'option **Nettoyer** \(menu **Générer**\) est sélectionnée.  
  
 **Plateforme cible**  
 Spécifie la plateforme sur laquelle le projet s'exécutera. Par exemple Windows, Android ou iOS. La valeur **Windows 10** signifie que le projet cible la plateforme Windows universelle. Si vous ciblez des versions antérieures de Windows, la version n'est pas répertoriée et la valeur de ce champ est simplement **Windows**. Il s'agit d'un champ en lecture seule qui est défini quand vous créez un projet.  
  
 **Version de la plateforme cible**  
 Pour les plateformes Windows, spécifie la version du Kit de développement logiciel \(SDK\) Windows avec laquelle votre projet est généré. Pour Windows, il s'agit de la version du Kit SDK Windows.[!INCLUDE[vs_dev14](../ide/includes/vs_dev14_md.md)] est fourni avec le Kit SDK Windows 8.1. Si vous avez installé les [Outils pour Windows 10](http://go.microsoft.com/fwlink/p/?LinkId=617631), chaque version de ces outils figure dans la liste déroulante.  
  
 Pour cibler Windows 7 ou Windows Vista, utilisez la valeur **8.1**, puisque le Kit SDK Windows 8.1 offre une compatibilité descendante avec ces plateformes. En outre, vous devez définir la valeur appropriée pour \_WIN32\_WINNT dans targetver.h. Pour Windows 7, il s'agit de 0x0601. Consultez [Modification de WINVER et \_WIN32\_WINNT](../porting/modifying-winver-and-win32-winnt.md).  
  
 Vous pouvez installer l'ensemble d'outils de plateforme v110\_xp fourni avec [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] si vous voulez utiliser la version actuelle de [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] pour générer des projets Windows XP et [!INCLUDE[WinXPSvr](../build/includes/winxpsvr_md.md)]. Pour plus d’informations sur la façon d’obtenir et d’utiliser cet ensemble d’outils de plateforme, consultez [Configuration des programmes C\+\+ 11 pour Windows XP](../build/configuring-programs-for-windows-xp.md). Pour plus d’informations sur la modification de l’ensemble d’outils de plateforme, consultez [comment : modifier la version cible de .Net Framework et l'ensemble d'outils de la plateforme](../build/how-to-modify-the-target-framework-and-platform-toolset.md).  
  
 **Version minimale de la plateforme. Version**  
 Spécifie la version la plus basse de la plateforme sur laquelle le projet peut s'exécuter. Cette propriété apparaît uniquement si le type de projet la prend en charge \(comme dans les projets d'application Windows universelle\). Si votre application peut tirer parti des fonctionnalités offertes par une nouvelle version du Kit SDK Windows tout en pouvant s'exécuter sur des versions antérieures sans ces fonctionnalités \(éventuellement avec une perte de fonctionnalité\), la valeur de ces deux propriétés peut être différente. Dans ce cas, votre code doit vérifier au moment de l'exécution la version de la plateforme sur laquelle il s'exécute et ne pas essayer d'utiliser des fonctionnalités qui ne sont pas disponibles dans les versions antérieures de la plateforme.  
  
 Notez que Visual C\+\+ n'applique pas cette option. Elle est fournie par souci de cohérence avec d'autres langages, tels que C\# et JavaScript, et comme guide pour toute personne qui utilise votre projet. Visual C\+\+ ne génère pas d'erreur si vous utilisez une fonctionnalité qui n'est pas disponible dans la version minimale.  
  
 **Répertoire de sortie**  
 Spécifie le répertoire dans lequel des outils, tels que l'éditeur de liens, placent tous les fichiers de sortie finaux créés pendant le processus de génération. En règle générale, cela inclut la sortie d'outils comme l'éditeur de liens, le Générateur de bibliothèques ou BSCMake.  
  
 Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.OutputDirectory%2A>.  
  
 **Répertoire intermédiaire**  
 Spécifie le répertoire dans lequel des outils, tels que le compilateur, placent tous les fichiers intermédiaires créés pendant le processus de génération. En règle générale, cela inclut la sortie d'outils tels que le compilateur C\/C\+\+, MIDL et le compilateur de ressources.  
  
 Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.IntermediateDirectory%2A>.  
  
 **Nom de la cible**  
 Spécifie le nom de fichier généré par ce projet.  
  
 **Extension de la cible**  
 Spécifie l'extension de nom de fichier générée par ce projet, par exemple .exe ou .dll.  
  
 **Extensions à supprimer lors du nettoyage**  
 L'option **Nettoyer** \(menu **Générer**\) supprime les fichiers du répertoire intermédiaire où la configuration d'un projet est générée. Les fichiers portant les extensions spécifiées avec cette propriété sont supprimés quand vous exécutez la commande **Nettoyer** ou quand vous effectuez une régénération. Outre les fichiers qui figurent dans le répertoire intermédiaire avec ces extensions, le système de génération supprime également toute sortie connue de la génération, quel que soit l'emplacement où elle se trouve \(y compris les sorties intermédiaires telles que les fichiers .obj\). Notez que vous pouvez spécifier des caractères génériques.  
  
 Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>.  
  
 **Fichier journal de génération**  
 Vous permet de spécifier un emplacement autre que l'emplacement par défaut pour le fichier journal créé chaque fois que vous générez un projet.  
  
 Vous pouvez utiliser des macros de projet pour modifier l'emplacement du répertoire. Consultez [Macros pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md).  
  
 **Ensemble d'outils de plateforme**  
 Permet au projet de cibler une version différente des bibliothèques Visual C\+\+ et du compilateur. Les projets [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)] peuvent cibler l'ensemble d'outils par défaut dans [!INCLUDE[vs_dev11_long](../build/includes/vs_dev11_long_md.md)] \(**v100**\) ou l'ensemble d'outils qui crée des fichiers exécutables pouvant s'exécuter sur Windows XP.  
  
## Paramètres par défaut du projet  
 Les propriétés de la section Paramètres par défaut du projet représentent les propriétés par défaut que vous pouvez modifier. La définition de ces propriétés est accessible dans les fichiers .props dans *répertoire\_installation*\\VC\\VCProjectDefaults.  
  
 **Type de configuration**  
 Vous pouvez choisir parmi plusieurs types de configuration :  
  
-   **Application \(.exe\)** : affiche l'ensemble d'outils de l'éditeur de liens \(compilateur C\/C\+\+, MIDL, compilateur de ressources, éditeur de liens, BSCMake, Générateur proxy du service web XML, événements de build, prebuild, préliaison et postbuild personnalisés\).  
  
-   **Bibliothèque dynamique \(.dll\)** : affiche l'ensemble d'outils de l'éditeur de liens, spécifie l'option \/DLL de l'éditeur de liens et ajoute la définition \_WINDLL à CL.  
  
-   **Makefile** : affiche l'ensemble d'outils makefile \(NMake\).  
  
-   **Bibliothèque statique \(.lib\)** : affiche l'ensemble d'outils du Générateur de bibliothèques \(identique à celui de l'éditeur de liens, sauf qu'il contient le Générateur de bibliothèques au lieu de l'éditeur de liens et qu'il ne contient pas le Générateur proxy du service web XML\).  
  
-   **Utilitaire** : affiche l'ensemble d'outils d'utilitaires \(MIDL, événements de build, prebuild et postbuild personnalisés\).  
  
 Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.ConfigurationType%2A>.  
  
 **Utilisation des MFC**  
 Spécifie si le projet MFC sera lié de manière statique ou dynamique à la DLL MFC. Les projets non\-MFC peuvent sélectionner **Utiliser les bibliothèques Windows standard** pour établir des liaisons à différentes bibliothèques Win32 qui sont incluses quand vous utilisez MFC.  
  
 Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>.  
  
 **Utilisation des ATL**  
 Spécifie si le projet ATL sera lié de manière statique ou dynamique à la DLL ATL. Si vous sélectionnez une option autre que **N'utilisant pas ATL**, une définition est ajoutée à la page de propriétés **Ligne de commande** du compilateur.  
  
 Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfATL%2A>.  
  
 **Jeu de caractères**  
 Définit si \_UNICODE ou \_MBCS doit être défini. Affecte également le point d'entrée de l'éditeur de liens le cas échéant.  
  
 Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>.  
  
 **Prise en charge du Common Language Runtime**  
 Entraîne l'utilisation de l'option du compilateur [\/clr](../build/reference/clr-common-language-runtime-compilation.md).  
  
 Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>.  
  
 **Optimisation de l'ensemble du programme**  
 Spécifie l'option du compilateur [\/GL](../build/reference/gl-whole-program-optimization.md) et l'option de l'éditeur de liens [\/LTCG](../build/reference/ltcg-link-time-code-generation.md).  
  
 **Prise en charge d'applications du Windows Store**  
 Spécifie si ce projet prend en charge les applications [!INCLUDE[win8_appname_long](../build/includes/win8_appname_long_md.md)]. Pour plus d’informations, consultez [\/ZW \(compilation Windows Runtime\)](../build/reference/zw-windows-runtime-compilation.md) et le Centre de développement Windows.  
  
## Voir aussi  
 [Pages de propriétés](../ide/property-pages-visual-cpp.md)