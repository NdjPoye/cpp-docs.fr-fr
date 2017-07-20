---
title: "Introduction à Visual C++ pour les utilisateurs UNIX | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- UNIX [C++]
ms.assetid: 36108b31-e7fa-49a8-a1f7-7077fcbec873
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: 3c1955bece0c8cdadb4a151ee06fa006402666a4
ms.openlocfilehash: 524be35ec1e1db511b7fd4c2ab2b87d83c54325c
ms.contentlocale: fr-fr
ms.lasthandoff: 06/08/2017

---
# <a name="introduction-to-visual-c-for-unix-users"></a>Introduction à Visual C++ pour les utilisateurs UNIX
Cette rubrique fournit des informations aux utilisateurs UNIX qui débutent avec Visual C++ et souhaitent être plus productifs.  
  
## <a name="getting-started-on-the-command-line"></a>Débuter sur la ligne de commande  
 Vous pouvez utiliser Visual C++ à partir de la ligne de commande, comme vous le feriez dans un environnement de ligne de commande UNIX. Vous compilez à partir de l'invite de commandes, à l'aide du compilateur de ligne de commande C et C++ (CL.EXE), et d'outils tels que NMAKE.EXE, la version Microsoft de l'utilitaire UNIX.  
  
 Sous UNIX, les commandes sont installées dans un dossier commun, tel que /usr/bin. Dans Visual C++, les outils en ligne de commande sont installés dans votre répertoire d’installation dans VC\bin (et pour une installation par défaut, dans Program Files\Microsoft Visual Studio 8\VC\bin). Pour utiliser les outils en ligne de commande, exécutez vsvars32.bat, qui se trouve dans votre répertoire d'installation dans Common7\Tools. Cela ajoute le répertoire bin à votre chemin d’accès et définit les autres chemins d’accès nécessaires pour compiler les programmes Visual C++ à partir de la ligne de commande. Pour plus d’informations, consultez [Génération à partir de la ligne de commande](../build/building-on-the-command-line.md) et [Procédure pas à pas : compilation d’un programme C++ natif sur la ligne de commande](../build/walkthrough-compiling-a-native-cpp-program-on-the-command-line.md).  
  
> [!NOTE]
>  Si vous ouvrez une invite de commandes avec l’**invite de ligne de commandes Visual Studio** à partir du menu **Démarrer**, vsvars32.bat s’exécute.  
  
 Pour profiter de fonctionnalités plus puissantes, telles que le débogueur Visual Studio, la saisie semi-automatique des instructions, etc., vous devez utiliser l’environnement de développement.  
  
## <a name="debugging-your-code"></a>Débogage de votre code  
 Si vous utilisez la ligne de commande et exécutez vos applications sur votre station de travail de développement, vous verrez qu'une boîte de dialogue permettant d'exécuter le débogueur [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] s'affiche quand votre code rencontre une violation d'accès mémoire, une exception non gérée ou d'autres erreurs irrécupérables. Si vous cliquez sur **OK**, l’environnement de développement Visual Studio se lance et le débogueur s’ouvre au point de défaillance. Il est possible de déboguer vos applications de cette façon et, dans ce cas, votre code source ne sera disponible que si vous avez effectué la compilation avec le commutateur [/Z7, /Zi, /ZI (format des informations de débogage)](../build/reference/z7-zi-zi-debug-information-format.md). Pour plus d’informations, consultez [Débogage du code natif](/visualstudio/debugger/debugging-native-code) et [Utilisation de l’IDE de Visual Studio pour le développement de bureau C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## <a name="using-the-development-environment"></a>Utilisation de l'environnement de développement  
 Il est plus facile d’utiliser l’environnement de développement pour modifier et générer votre code source dans un *projet*. Un projet est une collection de fichiers sources et de fichiers connexes qui seront compilés en une seule unité, telle qu’une bibliothèque ou un fichier exécutable. Un projet contient également des informations sur la façon dont les fichiers doivent être générés. Les informations sur les projets sont stockées dans un fichier projet avec l’extension .prj.  
  
 Les applications composées de plusieurs bibliothèques et fichiers exécutables (chacun ayant pu être généré avec un jeu différent d’options du compilateur ou même dans un langage différent) sont stockées dans plusieurs projets qui font partie d’une seule et même *solution*. Une solution est une abstraction pour un conteneur qui regroupe plusieurs projets. Les informations sur les solutions sont stockées dans un fichier solution avec l’extension .sln. Pour plus d’informations, consultez [Solutions et projets dans Visual Studio](/visualstudio/ide/solutions-and-projects-in-visual-studio) et [Utilisation de l’IDE de Visual Studio pour le développement de bureau C++](../ide/using-the-visual-studio-ide-for-cpp-desktop-development.md).  
  
## <a name="importing-your-existing-code"></a>Importation de votre code existant  
 Dans Visual C++, vous pouvez utiliser du code existant qui est configuré pour être compilé avec ou sans makefile, et le placer dans un projet [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)]. Pour plus d’informations, consultez **Assistant Créer un projet à partir de fichiers de code existants**. Pour plus d’informations, consultez [Guide pratique pour créer un projet C++ à partir d’un code existant](../ide/how-to-create-a-cpp-project-from-existing-code.md).  
  
## <a name="creating-a-new-project"></a>Création d'un projet  
 Vous pouvez créer des projets dans l'environnement de développement. Visual C++ propose de nombreux modèles qui fournissent du code standard pour différents projets courants. Vous pouvez utiliser les Assistants Application pour générer des projets à l'aide de schémas de code visant divers types d'application.  
  
 Vous pouvez démarrer avec un projet vide dans l’**Assistant Application Console (Win32)**. Cochez la case **Projet vide**. Vous pourrez par la suite ajouter au projet de nouveaux fichiers et des fichiers existants.  
  
 Quand vous créez un projet, vous devez lui attribuer un nom. Par défaut, le nom du projet est celui de la bibliothèque de liens dynamiques (DLL) ou du fichier exécutable généré par le projet. Pour plus d’informations, consultez [Création de solutions et de projets](/visualstudio/ide/creating-solutions-and-projects).  
  
## <a name="microsoft-specific-modifiers"></a>Modificateurs Microsoft spécifiques  
 Visual C++ contient plusieurs extensions au langage de programmation C++ standard. Ces extensions servent à spécifier des attributs de classe de stockage, des conventions d'appel de fonction et des fonctions d'adressage, entre autres choses. Pour obtenir une liste complète de toutes les extensions Visual C++, consultez [Modificateurs spécifiques Microsoft](../cpp/microsoft-specific-modifiers.md).  
  
 Vous pouvez désactiver toutes les extensions spécifiques Microsoft pour C++ à l’aide de l’option **/Za** du compilateur. Cette option est recommandée si vous souhaitez écrire du code devant s'exécuter sur plusieurs plateformes. Pour plus d’informations sur l’option **/Za** du compilateur, consultez [/Za, /Ze (désactiver les extensions de langage)](../build/reference/za-ze-disable-language-extensions.md). Pour plus d’informations sur la conformité de Visual C++, consultez [Comportement non standard](../cpp/nonstandard-behavior.md).  
  
## <a name="precompiled-headers"></a>En-têtes précompilés  
 Les compilateurs Microsoft C et C++ offrent des options pour la précompilation du code en C ou C++, y compris du code incorporé. Grâce à cela, vous pouvez compiler un corps de code stable, stocker l'état compilé du code dans un fichier et, lors des compilations suivantes, combiner le code précompilé avec du code qui est toujours en cours de développement. Les compilations ultérieures sont plus rapides, car le code stable n'a pas besoin d'être recompilé.  
  
 Par défaut, tout code précompilé est spécifié dans les fichiers **stdafx.h** et **stdafx.cpp**. L’Assistant **Nouveau projet** créera automatiquement ces fichiers, sauf si vous désélectionnez l’option **En-tête précompilé**. Pour plus d’informations, consultez [Création de fichiers d’en-têtes précompilés](../build/reference/creating-precompiled-header-files.md).  
  
## <a name="related-sections"></a>Rubriques connexes  
 Pour plus d’informations, consultez [Portage d’UNIX vers Win32](../porting/porting-from-unix-to-win32.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Génération de programmes C/C++](../build/building-c-cpp-programs.md)
