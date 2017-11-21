---
title: "Page de propriétés répertoires VC ++ | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
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
ms.openlocfilehash: 30a54b1d90585e6433f059acf30991ca53948d60
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="vc-directories-property-page"></a>Page de propriétés Répertoires VC++
Spécifie les répertoires à utiliser par Visual Studio pour générer un projet. Pour accéder à cette page de propriétés, dans **l’Explorateur de solutions**, ouvrez le menu contextuel du projet et choisissez **propriétés**, puis dans le volet gauche de la **Pages de propriétés** boîte de dialogue, développez **propriétés de Configuration** et sélectionnez **répertoires VC ++**.  
  
 Lorsque vous utilisez Visual Studio pour créer un projet, il hérite de certains répertoires. Beaucoup de ces derniers sont fournis comme macros. Pour examiner la valeur actuelle d’une macro, dans le volet droit de la **répertoires VC ++** , sélectionnez une ligne, par exemple, **répertoires Include**: cliquez sur le bouton de flèche vers le bas à droite, choisissez  **Modifier**, puis, dans la boîte de dialogue qui s’affiche, choisissez le **Macros** bouton. Pour plus d’informations, consultez ces billets de blog : [répertoires VC ++](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx), [héritée de propriétés et les feuilles de propriétés](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx), et [Visual Studio 2010 C++ Project Upgrade Guide](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx).  
  
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
  
#### <a name="to-specify-or-modify-directory-settings"></a>Pour spécifier ou modifier des paramètres de répertoire  
  
1.  Dans **l’Explorateur de solutions**, ouvrez le menu contextuel pour le projet que vous souhaitez modifier, puis choisissez **propriétés**.  
  
2.  Dans le volet gauche de la **Pages de propriétés** boîte de dialogue, développez **propriétés de Configuration** , puis sélectionnez **répertoires VC ++**.  
  
3.  Pour modifier l’une des listes de répertoire, sélectionnez-la, cliquez sur le bouton de flèche vers le bas à droite, puis choisissez **modifier**.  
  
     Dans la zone de la boîte de dialogue qui apparaît, vous pouvez ajouter ou supprimer des valeurs, et vous pouvez réorganiser l'ordre dans lequel les valeurs s'affichent. Vous pouvez également choisir le projet hérite des paramètres en activant ou désactivant **hériter des paramètres par défaut parent ou du projet**.  
  
## <a name="sharing-the-settings"></a>Partage des paramètres  
 Vous pouvez partager des paramètres de projet avec d'autres utilisateurs ou sur plusieurs ordinateurs. Pour plus d’informations, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
