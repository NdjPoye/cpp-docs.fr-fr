---
title: "Page de propriétés répertoires VC ++ | Documents Microsoft"
ms.custom: 
ms.date: 11/28/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VC.Project.VCDirectories.IncludePath
- VC.Project.VCDirectories.ReferencePath
- VC.Project.VCDirectories.SourcePath
- VC.Project.VCDirectories.LibraryWPath
- VC.Project.VCDirectories.ExecutablePath
- VC.Project.VCDirectories.LibraryPath
- VS.ToolsOptionsPages.Projects.VCDirectories
- VC.Project.VCDirectories.ExcludePath
dev_langs: C++
helpviewer_keywords: VC++ Directories Property Page
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
caps.latest.revision: "25"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 2c92a97ccd28a1bc7d1fae518cf499b45d339dae
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="vc-directories-property-page-windows"></a>VC ++ Page de propriétés répertoires (Windows)

Utilisez cette page de propriétés pour indiquer à Visual Studio les répertoires à utiliser lors de la génération du projet sélectionné. Pour définir des répertoires pour plusieurs projets dans une solution, utilisez une feuille de propriétés personnalisées, comme décrit dans [création de configurations de propriétés réutilisables](working-with-project-properties.md#bkmkPropertySheets).

Pour la version Linux de cette page, consultez [répertoires VC ++ (C++ Linux)](../linux/prop-pages/directories-linux.md).   

Pour accéder à la **répertoires VC ++** page de propriétés :

1. dans le menu principal, choisissez **affichage | Explorateur de solutions**
1. avec le bouton droit sur le nœud de projet (pas la solution de niveau supérieur) et choisissez **propriétés**
1. dans le volet gauche de la **Pages de propriétés** boîte de dialogue, développez **propriétés de Configuration** et sélectionnez **répertoires VC ++**.  

Les propriétés répertoires VC ++ s’appliquent à un projet, et non le nœud de solution de niveau supérieur :

![Sélectionnez le nœud de projet](media/vcppdir.png "sélectionnez le nœud de projet pour voir les propriétés répertoires VC ++")

Si vous ne voyez pas la page de propriétés, assurez-vous que vous avez sélectionné dans le nœud du projet **l’Explorateur de solutions**. Notez qu’un **répertoires VC ++** page de propriétés pour les projets interplateforme, différent. Pour les projets non Windows, consultez [répertoires VC ++ (C++ Linux)](../linux/prop-pages/directories-linux.md) ou. 
 
Si vous n’êtes pas familiarisé avec *propriétés de projet* dans Visual Studio, il peut s’avérer utile de la première lecture [utilisation des propriétés de projet](working-with-project-properties.md). 
 
Les paramètres par défaut pour les répertoires VC ++ dépendent du type de projet. Pour les projets de bureau, ils comprennent les emplacements d’outils VC ++ pour un ensemble d’outils de plateforme spécifique et l’emplacement du Kit de développement logiciel Windows. Vous pouvez modifier le **ensemble d’outils de plateforme** et **version du Kit de développement logiciel Windows** sur la **propriétés de Configuration – général** page. Pour afficher les valeurs pour tous les répertoires de :

1. dans le volet droit de la **répertoires VC ++** , sélectionnez une ligne. Par exemple, **répertoires de bibliothèques**
1. Cliquez sur le bouton de flèche vers le bas à droite
1. Choisissez **modifier**.

![Modifier les répertoires de bibliothèques](media/vcppdir_libdir_edit.png "boîte de dialogue pour modifier des chemins d’accès de la bibliothèque")

Vous maintenant voir une boîte de dialogue comme suit : 

![Afficher les répertoires de bibliothèques](media/vcppdir_libdir.png "boîte de dialogue pour ajouter ou supprimer des chemins d’accès de la bibliothèque")

Utilisez cette boîte de dialogue pour afficher les répertoires en cours. Toutefois, si vous souhaitez modifier ou ajouter un répertoire, il est préférable d’utiliser **Gestionnaire de propriétés** pour créer une feuille de propriétés ou de modifier la feuille de propriétés utilisateur par défaut. Pour plus d’informations, consultez [création de configurations de propriétés réutilisables](working-with-project-properties.md#bkmkPropertySheets).

Comme indiqué ci-dessus, la plupart des chemins d’accès héritées sont fournis comme macros.  Pour examiner la valeur actuelle d’une macro, choisissez le **Macros** bouton dans le coin inférieur droit de la boîte de dialogue. Notez que des macros varient selon le type de configuration. Une macro dans une version debug peut correspondre à un autre chemin d’accès à la même macro dans une version Release. 

Vous pouvez rechercher des correspondances partielles ou complètes dans la zone d’édition. L’illustration suivante montre toutes les macros qui contiennent la chaîne « WindowsSDK » et il montre également le chemin d’accès actuel qui prend la valeur de la macro :

![Consultez les valeurs des macros](media/vcppdir_libdir_macros.png "boîte de dialogue pour modifier les macros")

Remarque : La liste remplira en cours de frappe. N’appuyez pas sur **entrée**.

Pour plus d’informations sur les macros et pourquoi vous devez les utiliser au lieu des chemins codés en dur chaque fois que possible, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md#bkmkPropertiesVersusMacros). 

Pour obtenir la liste des macros couramment utilisées, consultez [Macros commun pour les propriétés et les commandes de génération](https://docs.microsoft.com/en-us/cpp/ide/common-macros-for-build-commands-and-properties).

Vous pouvez définir vos propres macros de deux manières :
-   Définir des variables d’environnement dans une invite de commandes développeur. Toutes les variables d’environnement sont traités en tant que propriétés/macros MSBuild.
-   Définir des macros utilisateur dans un fichier .props. Pour plus d’informations, consultez [macros de page de propriété](working-with-project-properties.md#bkmkPropertiesVersusMacros). 

Pour plus d’informations, consultez ces billets de blog : [répertoires VC ++](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [héritée de propriétés et les feuilles de propriétés](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx), et [Visual Studio 2010 C++ Project Upgrade Guide](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx).  
  
## <a name="directory-types"></a>Types de répertoires

Vous pouvez également spécifier d'autres répertoires, comme suit.  
  
**Répertoires d’exécutables**  
Répertoires dans lesquels rechercher des fichiers exécutables. Correspond à la **chemin d’accès** variable d’environnement.

**Répertoires Include**  
Répertoires dans lesquels rechercher des fichiers Include référencés dans le code source. Correspond à la **INCLUDE** variable d’environnement.

**Répertoires de référence**  
 Répertoires dans lesquels rechercher l’assembly et les fichiers de module (métadonnées) référencés dans le code source par le [#using](../preprocessor/hash-using-directive-cpp.md) directive. Correspond à la **LIBPATH** variable d’environnement.

**Répertoires de bibliothèques**  
Répertoires dans lesquels se trouvent des fichiers bibliothèques (.lib) ; cela inclut des bibliothèques Runtime. Correspond à la **LIB** variable d’environnement. Ce paramètre ne s’applique pas aux fichiers .obj ; Pour lier à un fichier .obj, sur le [l’éditeur de liens](../ide/linker-property-pages.md)**général** page de propriétés, sélectionnez **Additional Library Dependencies** , puis spécifiez le chemin d’accès relatif du fichier.

**Répertoires sources**  
Répertoires dans lesquels rechercher des fichiers source à utiliser pour IntelliSense.

**Exclure des répertoires**  
Répertoires à ne pas rechercher lors de la recherche de dépendances de génération.

## <a name="sharing-the-settings"></a>Partage des paramètres

Vous pouvez partager des paramètres de projet avec d'autres utilisateurs ou sur plusieurs ordinateurs. Pour plus d’informations, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).
