---
title: "Page de propri&#233;t&#233;s R&#233;pertoires VC++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.VCDirectories.IncludePath"
  - "VC.Project.VCDirectories.ReferencePath"
  - "VC.Project.VCDirectories.SourcePath"
  - "VC.Project.VCDirectories.LibraryWPath"
  - "VC.Project.VCDirectories.ExecutablePath"
  - "VC.Project.VCDirectories.LibraryPath"
  - "VS.ToolsOptionsPages.Projects.VCDirectories"
  - "VC.Project.VCDirectories.ExcludePath"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Page de propriétés Répertoires VC++"
ms.assetid: 428eeef6-f127-4271-b3ea-0ae6f2c3d624
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Page de propri&#233;t&#233;s R&#233;pertoires VC++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie les répertoires à utiliser par Visual Studio pour générer un projet.  Pour accéder à cette page de propriétés, dans l'**Explorateur de solutions**, ouvrez le menu contextuel du projet et choisissez **Propriétés**, puis dans le volet gauche de la boîte de dialogue **Pages de propriétés**, ouvrez **Propriétés de configuration** , puis sélectionnez **Répertoires VC\+\+**.  
  
 Lorsque vous utilisez Visual Studio pour créer un projet, il hérite de certains répertoires.  Beaucoup de ces derniers sont fournis comme macros.  Pour tester la valeur actuelle d'une macro, dans le volet droit de la page **Répertoires VC\+\+**, sélectionnez une ligne, par exemple **Répertoires Include**, puis choisissez la flèche vers le bas située sur la droite, sélectionnez ensuite **Modifier**, puis dans la boîte de dialogue qui apparaît, choisissez le bouton **Macros**.  Pour plus d'informations, consultez ces publications de blog : [Répertoires VC\+\+](http://blogs.msdn.com/b/vsproject/archive/2009/07/07/vc-directories.aspx) [Propriétés et feuilles de propriétés héritées](http://blogs.msdn.com/b/vsproject/archive/2009/06/23/inherited-properties-and-property-sheets.aspx) et [Guide 2010 de mise à niveau du projet C\+\+ Visual Studio](http://blogs.msdn.com/b/vcblog/archive/2010/03/02/visual-studio-2010-c-project-upgrade-guide.aspx).  
  
## Types de répertoires  
 Vous pouvez également spécifier d'autres répertoires, comme suit.  
  
 **Répertoires d'exécutables**  
 Répertoires dans lesquels rechercher des fichiers exécutables.  Correspond à la variable d'environnement,**PATH**.  
  
 **Répertoires Include**  
 Répertoires dans lesquels rechercher des fichiers Include référencés dans le code source.  Correspond à la variable d'environnement**INCLUDE**.  
  
 **Répertoires de référence**  
 Répertoires dans lesquels rechercher des fichiers d'assembly et de modules \(métadonnées\) référencés dans le code source par la directive [\#using](../preprocessor/hash-using-directive-cpp.md).  Correspond à la variable d'environnement **LIBPATH**.  
  
 **Répertoires de bibliothèques**  
 Répertoires dans lesquels se trouvent des fichiers bibliothèques \(.lib\) ; cela inclut des bibliothèques Runtime.  Correspond à la variable d'environnement **LIB**.  Ce paramètre ne s'applique pas aux fichiers .obj ; pour lier à un fichier .obj, sur la page de propriétés **Général** de [Linker](../ide/linker-property-pages.md), sélectionnez **Additional Library Dependencies** puis spécifiez le chemin d'accès relatif du fichier.  
  
 **Répertoires sources**  
 Répertoires dans lesquels rechercher des fichiers source à utiliser pour IntelliSense.  
  
 **Exclure des répertoires**  
 Répertoires à ne pas rechercher lors de la recherche de dépendances de génération.  
  
#### Pour spécifier ou modifier des paramètres de répertoire  
  
1.  Dans l'**Explorateur de solutions**, ouvrez le menu contextuel du projet que vous souhaitez modifier, puis choisissez **Propriétés**.  
  
2.  Dans le volet gauche de la boîte de dialogue **Pages de propriétés** , développez **Propriétés de configuration** et sélectionnez **Répertoires VC\+\+**.  
  
3.  Pour modifier une des listes de répertoire, sélectionnez\-la, choisissez la flèche vers le bas située à droite, puis choisissez **Modifier**.  
  
     Dans la zone de la boîte de dialogue qui apparaît, vous pouvez ajouter ou supprimer des valeurs, et vous pouvez réorganiser l'ordre dans lequel les valeurs s'affichent.  Vous pouvez également choisir si le projet hérite de paramètres en activant ou désactivant **Hériter des paramètres par défaut du parent ou du projet**.  
  
## Partage des paramètres  
 Vous pouvez partager des paramètres de projet avec d'autres utilisateurs ou sur plusieurs ordinateurs.  Pour plus d'informations, consultez [Utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
## Voir aussi  
 [Utilisation des propriétés de projet](../ide/working-with-project-properties.md)