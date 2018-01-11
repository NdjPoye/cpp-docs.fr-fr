---
title: "Génération de projets C++ dans Visual Studio | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Visual C++ projects, building
- projects [C++], building
- builds [C++], about building in Visual Studio
ms.assetid: 9e8bc1a2-bb17-4951-937a-c757ed88d2d1
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: cd4934f3075f963efe59e8d73d8c72347fd53912
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="building-c-projects-in-visual-studio"></a>Génération de projets C++ dans Visual Studio
Dans l'environnement de développement intégré (IDE) de Visual Studio, il existe plusieurs façons de générer une solution complète ou un seul projet dans cette solution. Vous pouvez également modifier les paramètres de build et spécifier des étapes de génération personnalisées pour rendre plus efficace votre processus de développement.  
  
 Pour créer une solution est ouverte dans Visual Studio et sélectionné dans **l’Explorateur de solutions**, vous pouvez :  
  
-   Dans la barre de menus, choisissez **Générer**, puis **Générer la solution**.  
  
-   Ou, **l’Explorateur de solutions**, ouvrez le menu contextuel de la solution, puis sélectionnez **générer la Solution**.  
  
-   Appuyez sur F7. (Raccourci clavier par défaut vers les paramètres de développement C/C++)  
  
-   Ou, dans le [fenêtre commande](/visualstudio/ide/reference/command-window) (dans la barre de menus, choisissez **vue**, **autres fenêtres**, **fenêtre commande**), entrez `Build.BuildSolution`.  
  
-   Ou, dans le [lancement rapide](/visualstudio/ide/reference/quick-launch-environment-options-dialog-box) , entrez `build build solution`.  
  
 Pour générer un projet est sélectionné dans **l’Explorateur de solutions**, vous pouvez :  
  
-   Dans la barre de menus, choisissez **générer**, **générer \<nom du projet >**.  
  
-   Ou, **l’Explorateur de solutions**, ouvrez le menu contextuel du projet, puis sélectionnez **Build**.  
  
-   Ou, dans la fenêtre de commande (dans la barre de menus, choisissez **vue**, **autres fenêtres**, **fenêtre commande**), entrez `Build.BuildOnlyProject`.  
  
-   Ou, dans la zone de lancement rapide, entrez `build project only build only <project name>`.  
  
 Quand vous générez une application Visual C++ dans Visual Studio, vous pouvez modifier un grand nombre de paramètres de la build dans la boîte de dialogue Pages de propriétés du projet. Pour plus d’informations sur la définition des propriétés du projet, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
 Pour obtenir un exemple sur la façon d’utiliser l’IDE pour créer, générer et déboguer un projet C++, consultez [procédure pas à pas : Explorer l’IDE de Visual Studio avec C++](/visualstudio/ide/getting-started-with-cpp-in-visual-studio). Pour obtenir un exemple sur l’utilisation de l’IDE pour générer un C + c++ / projet CLR, consultez [procédure pas à pas : compilation d’un programme C++ qui cible le CLR dans Visual Studio](../ide/walkthrough-compiling-a-cpp-program-that-targets-the-clr-in-visual-studio.md). Pour obtenir un exemple sur l’utilisation de l’IDE pour créer une application Windows Runtime, consultez [créer votre première application Windows Runtime en C++](http://msdn.microsoft.com/library/windows/apps/hh974580.aspx).  
  
 Pour en savoir plus sur la manière de générer, modifier les paramètres de build et spécifier des étapes de génération personnalisées, reportez-vous aux articles suivants.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Présentation des étapes de génération personnalisée et des événements de build](../ide/understanding-custom-build-steps-and-build-events.md)  
 Décrit comment personnaliser le processus de génération dans l'environnement de développement intégré.  
  
 [Macros courantes pour les propriétés et les commandes de génération](../ide/common-macros-for-build-commands-and-properties.md)  
 Répertorie les macros que vous pouvez utiliser quand les chaînes sont acceptées.  
  
 [Génération de projets externes](../ide/building-external-projects.md)  
 Présente la génération de projets qui utilisent des fonctionnalités à l'extérieur de l'environnement de développement intégré.  
  
 [Fichiers projet](../ide/project-files.md)  
 Présente la structure XML d'un fichier .vcxproj.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [Boîte de dialogue Options projets, répertoires VC ++](vcpp-directories-property-page.md)  
 (Uniquement pour les projets de MSBuild) Explique comment modifier le chemin de recherche des fichiers exécutables, notamment des fichiers, les fichiers de bibliothèque et les fichiers de code source pendant une génération.  
  
 [Compilation et génération](/visualstudio/ide/compiling-and-building-in-visual-studio)  
 Fournit des informations sur la génération d'applications dans Visual Studio.  
  
 [Génération de programmes C/C++](../build/building-c-cpp-programs.md)  
 Fournit des liens vers des rubriques qui décrivent comment générer votre programme à partir de la ligne de commande ou de l'environnement de développement intégré de Visual Studio.  
  
 [Référence de la génération C/C++](../build/reference/c-cpp-building-reference.md)  
 Fournit des liens vers des présentations de la génération de programmes à l'aide des options C++, du compilateur et de l'éditeur de liens, ainsi qu'avec des outils de génération supplémentaires.  
  
 [Mise à niveau de projets à partir de versions antérieures de Visual C++](../porting/upgrading-projects-from-earlier-versions-of-visual-cpp.md)  
 Fournit des liens vers les rubriques traitant les problèmes de mise à niveau de votre projet C++ vers des versions plus récentes de l’ensemble d’outils du compilateur.  
  
[Guide du portage et de la mise à niveau de Visual C++](../porting/visual-cpp-porting-and-upgrading-guide.md)  
  Obtenir des informations détaillées sur la mise à niveau des applications C++ qui ont été créées dans les versions antérieures de Visual Studio et également comment migrer les applications qui ont été créées à l’aide des outils autres que Visual Studio.  
  
## <a name="see-also"></a>Voir aussi  
 [Feuille de route pour les applications du Windows Store en C++](http://msdn.microsoft.com/en-us/0b71e4a4-5d8a-4a20-b2ec-e40062675ec1)