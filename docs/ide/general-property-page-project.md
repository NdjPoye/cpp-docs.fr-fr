---
title: "Page de propriétés Général (projet) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCConfiguration.IntermediateDirectory
- VC.Project.VCConfiguration.ConfigurationType
- VC.Project.VCConfiguration.ManagedExtensions
- VC.Project.VCConfiguration.BuildBrowserInformation
- VC.Project.VCConfiguration.BuildLogFile
- VC.Project.VCConfiguration.PlatformToolset
- VC.Project.VCConfiguration.TargetName
- VC.Project.VCConfiguration.
- VC.Project.VCConfiguration.TargetExt
- VC.Project.VCConfiguration.ATLMinimizesCRunTimeLibraryUsage
- VC.Project.VCConfiguration.ReferencesPath
- VC.Project.VCConfiguration.DeleteExtensionsOnClean
- VC.Project.VCConfiguration.useOfMfc
- VC.Project.VCConfiguration.CharacterSet
- VC.Project.VCGeneralMakefileSettings.ConfigurationType
- VC.Project.VCConfiguration.OutputDirectory
- VC.Project.VCConfiguration.AppSupport
- VC.Project.VCConfiguration.ToolFiles
- VC.Project.VCConfiguration.useOfATL
dev_langs:
- C++
helpviewer_keywords:
- Clean Build option
- output files, setting directory
- Unicode, creating C++ build configuration
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 772192a4b367760e85bb1631f1ef7b50650af0c1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="general-property-page-project"></a>Général, page de propriétés (Projet)

Lorsque vous cliquez sur un nœud de projet dans l’Explorateur de solutions et sélectionnez **propriétés**, le **général** page de propriétés sous la **propriétés de Configuration** nœud dans le volet de gauche affiche deux sections de propriétés :

- Général

- Paramètres par défaut du projet

Pour les projets non Windows, consultez [référence de Page de propriété Linux C++](../linux/prop-pages-linux.md)<!-- or [C++ Cross Platform Property Page Reference](../linux/prop-pages-linux.md)-->.

## <a name="general"></a>Général

Les propriétés de la section Général affectent l’emplacement des fichiers qui sont créés dans le processus de génération et les fichiers à supprimer quand le **Clean** option (**générer** menu) est sélectionné.

**Plateforme cible**  
Spécifie la plateforme sur laquelle le projet s'exécutera. Par exemple Windows, Android ou iOS. La valeur **Windows 10** signifie que le projet cible la plateforme Windows universelle. Si vous ciblez des versions antérieures de Windows, la version n’est pas répertoriée et que la valeur de ce champ est simplement **Windows**. Il s'agit d'un champ en lecture seule qui est défini quand vous créez un projet.

**Version du Kit de développement logiciel Windows**  
Pour la plateforme cible Windows, spécifie la version du SDK Windows nécessaires à votre projet. Lorsque vous installez une charge de travail C++ à l’aide du programme d’installation de Visual Studio, les parties requises du SDK Windows sont également installés. Si vous avez d’autres versions du Kit de développement logiciel Windows sur votre ordinateur, chaque version des outils de kit de développement logiciel que vous avez installée figure dans la liste déroulante.

Pour cibler Windows 7 ou Windows Vista, utilisez la valeur **8.1**, puisque kit SDK Windows 8.1 offre une compatibilité descendante avec ces plateformes. En outre, vous devez définir la valeur appropriée pour **_WIN32_WINNT** dans targetver.h. Pour Windows 7, il s'agit de 0x0601. Consultez [modification de WINVER et _WIN32_WINNT](../porting/modifying-winver-and-win32-winnt.md).

Vous pouvez installer les outils de plateforme Windows XP inclus dans Visual Studio pour utiliser la version actuelle des bibliothèques pour générer des projets Windows XP et Windows Server 2003. Pour plus d’informations sur la façon d’obtenir et d’utiliser cet ensemble d’outils de plateforme, consultez [configuration des programmes pour Windows XP](../build/configuring-programs-for-windows-xp.md). Pour plus d’informations sur la modification de l’ensemble d’outils de plateforme, consultez [Guide pratique pour modifier le framework cible et l’ensemble d’outils de la plateforme](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

**Version minimale de la plateforme cible**  
Spécifie la version la plus basse de la plateforme sur laquelle le projet peut s'exécuter. Cette propriété apparaît uniquement si le type de projet la prend en charge (comme dans les projets d'application Windows universelle). Si votre application peut tirer parti des fonctionnalités offertes par une nouvelle version du Kit SDK Windows tout en pouvant s'exécuter sur des versions antérieures sans ces fonctionnalités (éventuellement avec une perte de fonctionnalité), la valeur de ces deux propriétés peut être différente. Dans ce cas, votre code doit vérifier au moment de l'exécution la version de la plateforme sur laquelle il s'exécute et ne pas essayer d'utiliser des fonctionnalités qui ne sont pas disponibles dans les versions antérieures de la plateforme.

Notez que Visual C++ n'applique pas cette option. Elle est fournie par souci de cohérence avec d'autres langages, tels que C# et JavaScript, et comme guide pour toute personne qui utilise votre projet. Visual C++ ne génère pas d’erreur si vous utilisez une fonctionnalité qui n’est pas disponible dans la version minimale.

**Répertoire de sortie**  
Spécifie le répertoire dans lequel des outils, tels que l'éditeur de liens, placent tous les fichiers de sortie finaux créés pendant le processus de génération. En règle générale, cela inclut la sortie d'outils comme l'éditeur de liens, le Générateur de bibliothèques ou BSCMake. Par défaut, cette propriété est le répertoire spécifié par les macros $(SolutionDir) $(Configuration) \.

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.OutputDirectory%2A>.

**Répertoire intermédiaire**  
Spécifie le répertoire dans lequel des outils, tels que le compilateur, placent tous les fichiers intermédiaires créés pendant le processus de génération. En règle générale, cela inclut la sortie d'outils tels que le compilateur C/C++, MIDL et le compilateur de ressources. Par défaut, cette propriété est le répertoire spécifié par la macro $(Configuration) \.

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.IntermediateDirectory%2A>.

**Nom de la cible**  
Spécifie le nom de fichier généré par ce projet. Par défaut, cette propriété est le nom de fichier spécifié par la macro $(ProjectName).

**Extension de la cible**  
Spécifie l’extension de nom de fichier générée par ce projet, par exemple .exe ou .dll.

**Extensions à supprimer lors du nettoyage**  
Le **Clean** option (**générer** menu) supprime les fichiers du répertoire intermédiaire où la configuration d’un projet est générée. Les fichiers portant les extensions spécifiées avec cette propriété seront supprimés quand **Clean** est exécuté, soit quand vous effectuez une régénération. Outre les fichiers qui figurent dans le répertoire intermédiaire avec ces extensions, le système de génération supprime également toute sortie connue de la génération, quel que soit l’emplacement où elle se trouve (y compris les sorties intermédiaires telles que les fichiers .obj). Notez que vous pouvez spécifier des caractères génériques.

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.DeleteExtensionsOnClean%2A>.

**Fichier journal de génération**  
Vous permet de spécifier un emplacement autre que l'emplacement par défaut pour le fichier journal créé chaque fois que vous générez un projet. L’emplacement par défaut est spécifié par le .log de $(MSBuildProjectName) de macros $(IntDir).

Vous pouvez utiliser des macros de projet pour modifier l'emplacement du répertoire. Consultez [Macros communs pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md).

**Outils de plateforme**  
Permet au projet de cibler une version différente des bibliothèques Visual C++ et du compilateur. Projets Visual C++ peuvent cibler soit l’ensemble d’outils de valeur par défaut installé par Visual Studio, ou les ensembles d’outils installés par plusieurs versions précédentes de Visual Studio, y compris les ensembles d’outils qui créent des fichiers exécutables pouvant s’exécuter sur Windowx XP. Pour plus d’informations sur la modification de l’ensemble d’outils de plateforme, consultez [Comment : modifier le Framework cible et un ensemble d’outils de plateforme](../build/how-to-modify-the-target-framework-and-platform-toolset.md).

**Activer la Build incrémentielle managée**  
Pour les projets managés, cette fonctionnalité permet de détection de visibilité externe lorsque vous générez des assemblys. Si une modification à un projet managé n’est pas visible à d’autres projets, projets dépendants ne sont pas reconstruits. Cela peut considérablement améliorer les durées de génération dans les solutions qui incluent des projets managés.

## <a name="project-defaults"></a>Paramètres par défaut du projet

Les propriétés de la section Paramètres par défaut du projet représentent les propriétés par défaut que vous pouvez modifier. La définition de ces propriétés sont accessibles dans les fichiers .props dans *répertoire d’Installation*\VC\VCProjectDefaults.

**Type de configuration**  
Vous pouvez choisir parmi plusieurs types de configuration :

- **Application (.exe)**, affiche l’ensemble d’outils de l’éditeur de liens (compilateur C/C++, MIDL, compilateur de ressources, éditeur de liens, BSCMake, Générateur Proxy de Service Web XML, génération personnalisée, prebuild, préliaison et événements).

- **Bibliothèque dynamique (.dll)**, affiche l’éditeur de liens, spécifie l’option /DLL de l’éditeur de liens et ajoute la définition _WINDLL à CL.

- **Makefile**, affiche le jeu d’outils makefile (NMake).

- **Bibliothèque statique (.lib)**, affiche l’ensemble d’outils (identique à l’ensemble d’outils de l’éditeur de liens, sauf le Générateur de bibliothèques de liens et Générateur de Proxy de Service Web XML).

- **Utilitaire**, affiche le jeu d’utilitaires (MIDL, événements de build personnalisée, prebuild et postbuild).

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProjectEngine.VCConfiguration.ConfigurationType%2A>.

**Utilisation des MFC**  
Spécifie si le projet MFC sera lié de manière statique ou dynamique à la DLL MFC. Les projets non-MFC peuvent sélectionner **utiliser les bibliothèques Windows Standard** à lier à différentes bibliothèques Win32 qui sont incluses lorsque vous utilisez MFC.

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfMfc%2A>.

**Utilisation des ATL**  
Spécifie si le projet ATL sera lié de manière statique ou dynamique à la DLL ATL. Si vous sélectionnez une option autre que **n’utilisant pas ATL**, une définition est ajoutée à du compilateur **ligne de commande** page de propriétés.

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.useOfATL%2A>.

**Jeu de caractères**  
Définit si _UNICODE ou _MBCS doit être défini. Affecte également le point d'entrée de l'éditeur de liens le cas échéant.

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.CharacterSet%2A>.

**Prise en charge de Common Language Runtime**  
Provoque la [/CLR](../build/reference/clr-common-language-runtime-compilation.md) option du compilateur à utiliser.

Pour accéder par programmation à cette propriété, consultez <xref:Microsoft.VisualStudio.VCProject.VCProjectConfigurationProperties.ManagedExtensions%2A>.

**Version cible du .NET Framework**  
Dans les projets managés, spécifie la version du .NET framework à cibler.

**Optimisation de l’ensemble du programme**  
Spécifie le [/GL](../build/reference/gl-whole-program-optimization.md) option du compilateur et [LTCG](../build/reference/ltcg-link-time-code-generation.md) option de l’éditeur de liens. Par défaut, il est désactivé pour les configurations Debug et activé pour les configurations de la vente au détail.

**Prise en charge des applications du Windows Store**  
Spécifie si ce projet prend en charge les applications Windows Runtime (plateforme Windows universelle). Pour plus d’informations, consultez [/ZW (Compilation Windows Runtime)](../build/reference/zw-windows-runtime-compilation.md)et le centre de développement Windows.

## <a name="see-also"></a>Voir aussi

[Pages de propriétés](../ide/property-pages-visual-cpp.md)  