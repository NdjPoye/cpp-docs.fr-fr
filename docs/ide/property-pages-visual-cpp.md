---
title: "Pages de propriétés (Visual C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VC.Project.NotAProp.Edit
dev_langs: C++
helpviewer_keywords:
- project-file macro
- project properties [C++], default values
- user-defined values
- project properties [C++], setting
- macros, project-file
- property pages, project settings
- Visual C++ projects, properties
- build macro
- user-defined macros
ms.assetid: 13ffe3ea-1bc3-4bee-be5e-053a8a99cce4
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0d276a9ada16c4959be0b5ee20d43bf78e65217b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="property-pages-visual-c"></a>Pages de propriétés (Visual C++)
Les pages de propriétés vous permettent de spécifier les paramètres des projets Visual Studio. Pour ouvrir la **Pages de propriétés** projet de la boîte de dialogue de Visual Studio, dans le **projet** menu, cliquez sur **propriétés**.  
  
 Vous pouvez spécifier les paramètres du projet pour qu'ils s'appliquent à toutes les configurations de build. Vous pouvez aussi spécifier différentes propriétés de projet pour chaque configuration de build. Par exemple, vous pouvez spécifier certains paramètres pour la configuration Release et d’autres paramètres pour la configuration Debug.  
  
 Pas toutes les pages disponibles sont toujours affichées dans le **Pages de propriétés** boîte de dialogue. Les pages affichées varient en fonction des types de fichiers contenus dans le projet.  
  
 Pour plus d’informations, consultez [utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
## <a name="default-properties-vs-modified-properties"></a>Propriétés par défaut et propriétés modifiées  
 Lorsque vous utilisez la **nouveau projet** boîte de dialogue pour créer un projet, Visual Studio utilise le modèle de projet spécifié pour initialiser les propriétés du projet. Par conséquent, les valeurs des propriétés du modèle peuvent être considérées comme des valeurs par défaut pour ce type de projet. Dans d'autres types de projets, les propriétés peuvent avoir des valeurs par défaut différentes.  
  
 Une valeur de propriété de projet apparaît en gras si elle est modifiée. Une propriété de projet peut être modifiée pour les raisons suivantes :  
  
-   L'Assistant Application modifie la propriété, car il exige une valeur de propriété différente de celle spécifiée dans le modèle de projet.  
  
-   Vous spécifiez une valeur de propriété différente dans la **nouveau projet** boîte de dialogue.  
  
-   Vous pouvez spécifier une valeur de propriété différente dans une page de propriétés du projet.  
  
> [!TIP]
>  Pour afficher le jeu final de valeurs de propriété MSBuild utilise pour générer votre projet, examinez le fichier de sortie du préprocesseur, que vous pouvez créer à l’aide de cette ligne de commande : **MSBuild / de prétraitement :***preprocessor_output_ nom de fichier*opt*NomFichier_Projet*opt  
  
## <a name="resetting-properties"></a>Réinitialisation des propriétés  
 Lorsque vous affichez la **Pages de propriétés** boîte de dialogue pour un projet et le nœud de projet est sélectionné dans **l’Explorateur de solutions**, pour de nombreuses propriétés, vous pouvez sélectionner **hériter du parent ou du projet valeurs par défaut** ou modifier la valeur une autre façon.  
  
 Lorsque vous affichez la **Pages de propriétés** boîte de dialogue pour un projet et un fichier est sélectionné dans **l’Explorateur de solutions**, pour de nombreuses propriétés, vous pouvez sélectionner **héritent par défaut du parent ou du projet** ou modifier la valeur une autre façon. Cependant, si le projet contient de nombreux fichiers dont certaines propriétés ont des valeurs différentes des valeurs par défaut du projet, la génération de ce dernier prend plus de temps.  
  
> [!TIP]
>  Pour actualiser le **Pages de propriétés** boîte de dialogue afin qu’elle affiche les sélections les plus récentes, cliquez sur **appliquer**.  
  
 La plupart des valeurs par défaut du projet sont les valeurs par défaut du système (plateforme). Certains paramètres par défaut du projet dérivent des feuilles de style qui sont appliqués lorsque vous mettez à jour les propriétés dans le **valeurs par défaut du projet** section de la **général** page de propriétés de configuration pour le projet. Pour plus d’informations, consultez [général, Page de propriétés (projet)](../ide/general-property-page-project.md).  
  
## <a name="specifying-user-defined-values"></a>Spécification de valeurs définies par l'utilisateur  
 Vous devez définir la valeur de certaines propriétés. Une valeur définie par l'utilisateur peut contenir un ou plusieurs caractères alphanumériques ou des noms de macros de fichiers projet. Si certaines de ces propriétés ne peuvent prendre qu'une seule valeur définie par l'utilisateur, d'autres peuvent en accepter plusieurs prenant la forme d'une liste délimitée par des points-virgules.  
  
 Pour définir une propriété avec une valeur définie par l'utilisateur ou une liste si la propriété peut accepter plusieurs valeurs définies par l'utilisateur, dans la colonne située à droite du nom de la propriété, procédez de l'une des façons suivantes :  
  
-   Tapez la valeur ou la liste de valeurs.  
  
-   Cliquez sur la flèche déroulante. Si **modifier** n’est disponible, cliquez dessus, puis, dans la zone de texte, tapez la valeur ou une liste de valeurs. Une autre façon de spécifier une liste est de taper chaque valeur sur une ligne distincte dans la zone de texte. Dans la page de propriétés, les valeurs s'affichent sous forme de liste délimitée par des points-virgules.  
  
     Pour insérer une macro de fichier projet en tant que valeur, cliquez sur **Macros** puis double-cliquez sur le nom de macro.  
  
-   Cliquez sur la flèche déroulante. Si **Parcourir** n’est disponible, cliquez dessus, puis sélectionnez une ou plusieurs valeurs.  
  
 Pour une propriété à valeurs multiples, le **hériter des paramètres par défaut parent ou du projet** option est disponible lorsque vous cliquez sur la flèche déroulante dans la colonne à droite du nom de la propriété, puis sur **modifier**. Cette option est activée par défaut.  
  
 Notez qu'une page de propriétés présente uniquement les paramètres correspondant au niveau actuel d'une propriété à valeurs multiples qui hérite d'un autre niveau. Par exemple, si un fichier est sélectionné dans **l’Explorateur de solutions** et que vous sélectionnez le C/C++ **définitions de préprocesseur** propriété, les définitions au niveau des fichiers sont affichées, mais héritée les définitions au niveau du projet ne sont pas affichés. Pour afficher à la fois au niveau actuel et les valeurs héritées, cliquez sur la flèche déroulante dans la colonne à droite du nom de la propriété, puis sur **modifier**. Si vous utilisez la [modèle de projet Visual C++](http://msdn.microsoft.com/en-us/06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f), ce comportement est également valable pour les objets de fichiers et de projets. Ainsi, quand vous formulez une requête pour récupérer les valeurs d'une propriété au niveau du fichier, vous n'obtenez pas les valeurs de cette même propriété au niveau du projet. Vous devez obtenir explicitement les valeurs de la propriété au niveau du projet. De même, certaines valeurs héritées d'une propriété peuvent provenir d'une feuille de style qui n'est pas accessible par programmation.  
  
## <a name="in-this-section"></a>Dans cette section  
  
 
  [Avancé, outil manifeste, propriétés de Configuration, \<Projectname > boîte de dialogue Pages de propriétés](../ide/advanced-manifest-tool.md)   
  
  [Ligne de commande, pages de propriétés](../ide/command-line-property-pages.md)  
  
  [Étape de génération personnalisée, page de propriétés : général](../ide/custom-build-step-property-page-general.md)  
  
  [Ajout de références](../ide/adding-references-in-visual-cpp-projects.md)  
  
  [Général, page de propriétés (Fichier)](../ide/general-property-page-file.md)  
  
  [Général, page de propriétés (Projet)](../ide/general-property-page-project.md)  
   
  [Général, outil manifeste, propriétés de Configuration, \<Projectname > boîte de dialogue Pages de propriétés](../ide/general-manifest-tool-configuration-properties.md)  
  
  [HLSL, page de propriétés](../ide/hlsl-property-pages.md)  
  
  [HLSL, page de propriétés : Avancé](../ide/hlsl-property-pages-advanced.md)  
  
  [HLSL, page de propriétés : Général](../ide/hlsl-property-pages-general.md)  
  
  [HLSL, page de propriétés : fichiers de sortie](../ide/hlsl-property-pages-output-files.md)  
  
  [Entrée et sortie, outil, les propriétés de Configuration, manifeste \<Projectname > boîte de dialogue Pages de propriétés](../ide/input-and-output-manifest-tool.md)  
  
  [Isolé COM, outil manifeste, propriétés de Configuration, \<Projectname > boîte de dialogue Pages de propriétés](../ide/isolated-com-manifest-tool.md)  
  
  [Éditeur de liens, page de propriétés](../ide/linker-property-pages.md)  
  
  [Ressources managées, page de propriétés](../ide/managed-resources-property-page.md)  
  
  [Outil Manifeste, page de propriétés](../ide/manifest-tool-property-pages.md)  
  
  [MIDL, page de propriétés](../ide/midl-property-pages.md)  
  
  [MIDL, page de propriétés : Avancé](../ide/midl-property-pages-advanced.md)  
  
  [MIDL, page de propriétés : Général](../ide/midl-property-pages-general.md)  
  
  [MIDL, page de propriétés : Sortie](../ide/midl-property-pages-output.md)  
  
  [NMake, page de propriétés](../ide/nmake-property-page.md)  
  
  [Ressources, page de propriétés](../ide/resources-property-pages.md)  
  
  [Répertoires VC++, page de propriétés](../ide/vcpp-directories-property-page.md)  
  
  [Références web, page de propriétés](../ide/web-references-property-page.md)  
  
  [XML Data Generator Tool, page de propriétés](../ide/xml-data-generator-tool-property-page.md)  
  
  [Outil Générateur de documents XML, page de propriétés](../ide/xml-document-generator-tool-property-pages.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Comment : créer et supprimer des dépendances du projet](/visualstudio/ide/how-to-create-and-remove-project-dependencies)   
 [Guide pratique pour créer et modifier des configurations](/visualstudio/ide/how-to-create-and-edit-configurations)   
