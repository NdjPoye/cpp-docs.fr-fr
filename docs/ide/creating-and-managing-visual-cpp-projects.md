---
title: "Création et gestion de projets Visual C++ | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vcprojects
- creatingmanagingVC
dev_langs: C++
helpviewer_keywords:
- ATL projects, creating
- Visual C++ projects, creating
- projects [C++], creating
- Visual C++ projects
- ATL projects
ms.assetid: 11003cd8-9046-4630-a189-a32bf3b88047
caps.latest.revision: "28"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c38f4c75a41de8b2f2b494941c6a52b1ff46fa4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="creating-and-managing-msbuild-based-visual-c-projects"></a>Création et gestion des projets MSBuild se Visual C++
MSBuild est le système de génération native pour Visual C++ et est généralement que la meilleure build système à utiliser pour les applications UWP, ainsi que des applications de bureau qui utilisent les bibliothèques MFC ou ATL. MSBuild est étroitement intégré à l’IDE de Visual Studio et le système de projet, mais vous pouvez également l’utiliser à partir de la ligne de commande. À partir de Visual Studio 2017, Visual C++ prend en charge les [CMake et d’autres systèmes non MSBuild via la fonctionnalité Ouvrir le dossier](non-msbuild-projects.md).

Un projet MSBuild a un fichier de projet au format XML (.vcxproj) qui spécifie tous les fichiers et les ressources nécessaires à la compilation du programme, ainsi que d’autres paramètres de configuration, par exemple la plateforme cible (x 86, x64 ou ARM) et si vous générez un version finale ou version debug du programme. Un projet (ou de nombreux projets) sont contenus dans une *solution*. Par exemple, une solution peut contenir plusieurs projets de DLL Win32 et une seule application console Win32 qui utilise ces DLL. Quand vous générez le projet, le moteur MSBuild consomme le fichier projet. En outre, il produit le fichier exécutable et/ou toute autre sortie personnalisée que vous avez spécifiée.

Vous pouvez créer des projets Visual C++ en choisissant **fichier &#124; Nouveau &#124; Projet**, en vérifiant que Visual C++ est sélectionné dans le volet gauche, puis en choisissant dans la liste des modèles de projet dans le volet central. Lorsque vous cliquez sur un modèle, dans de nombreux cas un Assistant s’affiche qui vous permet de définir différentes propriétés de projet avant la création du projet. Vous pouvez afficher et modifier ces propriétés ultérieurement à l’aide des pages de propriétés du projet (**projet &#124; Propriétés**).  
  
 Vous pouvez également créer des projets comme suit :  
  
-   en choisissant **fichier &#124; Nouveau &#124; Projet à partir de Code existant** et suivez les instructions pour ajouter des fichiers de code source existants. Cette option est la plus appropriée pour les projets relativement petits et simples, 25 fichiers de code source tout au plus, avec peu ou pas de dépendances complexes.  
  
-   Démarrez avec un makefile, puis choisissez le modèle de projet Makefile sous l'onglet Général.  
  
-   Créez un projet vide (sous la **général** onglet), en ajoutant manuellement les fichiers de code source en cliquant sur le nœud de projet dans l’Explorateur de solutions et en choisissant **ajouter &#124; Un élément existant**.  
  
-   using the [Win32 Application Wizard](../windows/win32-application-wizard.md).  
  
## <a name="in-this-section"></a>Dans cette section  
 [Types de projets Visual C++](../ide/visual-cpp-project-types.md)  
 Décrit les types de projet MSBuild qui sont disponibles dans Visual C++.  
  
 [Types de fichiers créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)  
 Décrit les types de fichiers qui sont utilisés avec divers types de projet MSBuild.  
  
 [Création de projets de bureau à l’aide des Assistants Application](../ide/creating-desktop-projects-by-using-application-wizards.md)  
 Explique comment utiliser les Assistants pour créer des projets en Visual C++.  
  
 [Utilisation des propriétés de projet](../ide/working-with-project-properties.md)  
 Explique comment utiliser les pages de propriétés et les feuilles de propriétés pour spécifier les paramètres de votre projet.  
  
 [Ajout de fonctionnalités à l’aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)  
 Explique comment ajouter des classes, des méthodes, des variables et d'autres éléments à votre projet pour ajouter des fonctionnalités.  
  
 [Guide pratique pour organiser des fichiers de sortie de projet pour les générations](../ide/how-to-organize-project-output-files-for-builds.md)  
 Explique comment organiser les fichiers de sortie de projet.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Génération de programmes C/C++](../build/building-c-cpp-programs.md)  
 Fournit des liens vers des rubriques qui décrivent comment générer votre programme à partir de la ligne de commande ou de l'environnement de développement intégré de Visual Studio.  
  
 [Références Visual C++](http://msdn.microsoft.com/en-us/1ba03b5c-8229-4f63-b08c-6c12141d6ab1)  
 Fournit des liens vers les rubriques décrivant les références des langages C et C++, les bibliothèques fournies avec Visual C++, le modèle objet d'extensibilité Visual C++ et l'assembleur de macros Microsoft (MASM, Microsoft Macro Assembler).  
  
## <a name="see-also"></a>Voir aussi  
 [Kit de développement logiciel Visual Studio](http://msdn.microsoft.com/vstudio/extend)
