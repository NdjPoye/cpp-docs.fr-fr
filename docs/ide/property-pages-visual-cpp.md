---
title: "Pages de propri&#233;t&#233;s (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VC.Project.NotAProp.Edit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "macro de génération"
  - "macros, fichier projet"
  - "propriétés de projet (C++), valeurs par défaut"
  - "propriétés de projet (C++), définir"
  - "fichier projet macro"
  - "pages de propriétés, paramètres de projet"
  - "macros définies par l'utilisateur"
  - "valeurs définies par l'utilisateur"
  - "projets Visual C++, propriétés"
ms.assetid: 13ffe3ea-1bc3-4bee-be5e-053a8a99cce4
caps.latest.revision: 22
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Pages de propri&#233;t&#233;s (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les pages de propriétés vous permettent de spécifier les paramètres des projets Visual Studio.  Pour accéder à la boîte de dialogue **Pages de propriétés** d'un projet Visual Studio, dans le menu **Projet**, cliquez sur **Propriétés**.  
  
 Vous pouvez spécifier les paramètres du projet pour qu'ils s'appliquent à toutes les configurations de build. Vous pouvez aussi spécifier différentes propriétés de projet pour chaque configuration de build.  Par exemple, vous pouvez spécifier certains paramètres pour la configuration Release et d'autres paramètres pour la configuration Debug.  
  
 La boîte de dialogue **Pages de propriétés** n'affiche pas nécessairement toutes les pages disponibles.  Les pages affichées varient en fonction des types de fichiers contenus dans le projet.  
  
 Pour plus d'informations, consultez [Utilisation des propriétés de projet](../ide/working-with-project-properties.md).  
  
## Propriétés par défaut etpropriétés modifiées  
 Quand vous créez un projet à partir de la boîte de dialogue **Nouveau projet**, [!INCLUDE[vsprvs](../assembler/masm/includes/vsprvs_md.md)] utilise le modèle de projet spécifié pour initialiser les propriétés du projet.  Par conséquent, les valeurs des propriétés du modèle peuvent être considérées comme des valeurs par défaut pour ce type de projet.  Dans d'autres types de projets, les propriétés peuvent avoir des valeurs par défaut différentes.  
  
 Une valeur de propriété de projet apparaît en gras si elle est modifiée.  Une propriété de projet peut être modifiée pour les raisons suivantes :  
  
-   L'Assistant Application modifie la propriété, car il exige une valeur de propriété différente de celle spécifiée dans le modèle de projet.  
  
-   Vous pouvez spécifier une valeur de propriété différente dans la boîte de dialogue **Nouveau projet**.  
  
-   Vous pouvez spécifier une valeur de propriété différente dans une page de propriétés du projet.  
  
> [!TIP]
>  Pour afficher le jeu de valeurs de propriétés final que MSBuild utilisera pour générer votre projet, examinez le fichier de sortie du préprocesseur, que vous pouvez créer en utilisant cette ligne de commande : **MSBuild \/preprocess:***nomfichier\_sortie\_préprocesseur*opt *nomfichier\_projet*opt  
  
## Réinitialisation des propriétés  
 Quand vous affichez la boîte de dialogue **Pages de propriétés** pour un projet et que le nœud du projet est sélectionné dans l'**Explorateur de solutions**, pour bon nombre de propriétés, vous pouvez sélectionner **Hériter des paramètres par défaut du parent ou du projet** ou modifier la valeur d'une autre façon.  
  
 Quand vous affichez la boîte de dialogue **Pages de propriétés** pour un projet et qu'un fichier est sélectionné dans l'**Explorateur de solutions**, pour bon nombre de propriétés, vous pouvez sélectionner **Hériter des paramètres par défaut du parent ou du projet** ou modifier la valeur d'une autre façon.  Cependant, si le projet contient de nombreux fichiers dont certaines propriétés ont des valeurs différentes des valeurs par défaut du projet, la génération de ce dernier prend plus de temps.  
  
> [!TIP]
>  Pour actualiser la boîte de dialogue **Pages de propriétés** de sorte qu'elle présente les sélections les plus récentes, cliquez sur **Appliquer**.  
  
 La plupart des valeurs par défaut du projet sont les valeurs par défaut du système \(plateforme\).  Certains paramètres par défaut du projet dérivent des feuilles de style qui sont appliquées au moment où vous mettez à jour des propriétés dans la section **Paramètres par défaut du projet** de la page de propriétés de configuration **Général** du projet.  Pour plus d'informations, consultez [Général, page de propriétés \(Projet\)](../ide/general-property-page-project.md).  
  
## Spécification de valeurs définies par l'utilisateur  
 Vous devez définir la valeur de certaines propriétés.  Une valeur définie par l'utilisateur peut contenir un ou plusieurs caractères alphanumériques ou des noms de macros de fichiers projet.  Si certaines de ces propriétés ne peuvent prendre qu'une seule valeur définie par l'utilisateur, d'autres peuvent en accepter plusieurs prenant la forme d'une liste délimitée par des points\-virgules.  
  
 Pour définir une propriété avec une valeur définie par l'utilisateur ou une liste si la propriété peut accepter plusieurs valeurs définies par l'utilisateur, dans la colonne située à droite du nom de la propriété, procédez de l'une des façons suivantes :  
  
-   Tapez la valeur ou la liste de valeurs.  
  
-   Cliquez sur la flèche déroulante.  Si **Modifier** est disponible, cliquez dessus puis, dans la zone de texte, tapez la valeur ou la liste de valeurs.  Une autre façon de spécifier une liste est de taper chaque valeur sur une ligne distincte dans la zone de texte.  Dans la page de propriétés, les valeurs s'affichent sous forme de liste délimitée par des points\-virgules.  
  
     Pour insérer une macro de fichier projet en tant que valeur, cliquez sur **Macros**, puis double\-cliquez sur le nom de la macro.  
  
-   Cliquez sur la flèche déroulante.  Si **Parcourir** est disponible, cliquez dessus, puis sélectionnez une ou plusieurs valeurs.  
  
 Pour une propriété à valeurs multiples, l'option **Hériter des paramètres par défaut du parent ou du projet** est disponible quand vous cliquez sur la flèche déroulante de la colonne située à droite du nom de la propriété, puis sur **Modifier**.  Cette option est activée par défaut.  
  
 Notez qu'une page de propriétés présente uniquement les paramètres correspondant au niveau actuel d'une propriété à valeurs multiples qui hérite d'un autre niveau.  Par exemple, si un fichier est sélectionné dans l'**Explorateur de solutions** et que vous sélectionnez la propriété **Définitions de préprocesseur** C\/C\+\+, les définitions au niveau du fichier sont affichées, mais pas celles, héritées, au niveau du projet.  Pour afficher à la fois les valeurs du niveau actuel et les valeurs héritées, cliquez sur la flèche déroulante dans la colonne située à droite du nom de la propriété, puis sur **Modifier**.  Si vous utilisez le [modèle de projet Visual C\+\+](http://msdn.microsoft.com/fr-fr/06c1bbd9-4c79-4f97-ad6d-2b1dea8ecd1f), ce comportement s'applique aussi aux objets des fichiers et projets.  Ainsi, quand vous formulez une requête pour récupérer les valeurs d'une propriété au niveau du fichier, vous n'obtenez pas les valeurs de cette même propriété au niveau du projet.  Vous devez obtenir explicitement les valeurs de la propriété au niveau du projet.  De même, certaines valeurs héritées d'une propriété peuvent provenir d'une feuille de style qui n'est pas accessible par programmation.  
  
## Dans cette section  
  
1.  [Ajouter un chemin de recherche des références, boîte de dialogue](http://msdn.microsoft.com/fr-fr/4520d80d-aa9f-4d11-b92b-2f64a1fd5cb2)  
  
2.  [Avancé, Outil Manifeste, Propriétés de configuration, boîte de dialogue Pages de propriétés de \<NomProjet\>](../ide/advanced-manifest-tool.md)  
  
3.  [Pages de propriétés Ligne de commande](../ide/command-line-property-pages.md)  
  
4.  [Étape de génération personnalisée, page de propriétés : général](../ide/custom-build-step-property-page-general.md)  
  
5.  [Ajout de références](../ide/adding-references-in-visual-cpp-projects.md)  
  
6.  [Général, page de propriétés \(Fichier\)](../ide/general-property-page-file.md)  
  
7.  [Général, page de propriétés \(Projet\)](../ide/general-property-page-project.md)  
  
8.  [Général, Outil Manifeste, Propriétés de configuration, boîte de dialogue Pages de propriétés de \<NomProjet\>](../ide/general-manifest-tool-configuration-properties.md)  
  
9. [Pages de propriétés HLSL](../ide/hlsl-property-pages.md)  
  
10. [Pages de propriétés HLSL : Avancé](../ide/hlsl-property-pages-advanced.md)  
  
11. [Pages de propriétés HLSL : Général](../ide/hlsl-property-pages-general.md)  
  
12. [Pages de propriétés HLSL : fichiers de sortie](../ide/hlsl-property-pages-output-files.md)  
  
13. [Entrée et sortie, Outil Manifeste, Propriétés de configuration, boîte de dialogue Pages de propriétés de \<NomProjet\>](../ide/input-and-output-manifest-tool.md)  
  
14. [COM isolé, Outil Manifeste, Propriétés de configuration, boîte de dialogue Pages de propriétés de \<NomProjet\>](../ide/isolated-com-manifest-tool.md)  
  
15. [Pages de propriétés de l'Éditeur de liens](../ide/linker-property-pages.md)  
  
16. [Ressources managées, page de propriétés](../ide/managed-resources-property-page.md)  
  
17. [Pages de propriétés de l'outil Manifeste](../ide/manifest-tool-property-pages.md)  
  
18. [Pages de propriétés MIDL](../ide/midl-property-pages.md)  
  
19. [Pages de propriétés MIDL : Avancé](../ide/midl-property-pages-advanced.md)  
  
20. [Pages de propriétés MIDL : Général](../ide/midl-property-pages-general.md)  
  
21. [Pages de propriétés MIDL : Sortie](../ide/midl-property-pages-output.md)  
  
22. [Nmake, page de propriétés](../ide/nmake-property-page.md)  
  
23. [Pages de propriétés Ressources](../ide/resources-property-pages.md)  
  
24. [Page de propriétés Répertoires VC\+\+](../ide/vcpp-directories-property-page.md)  
  
25. [Références web, page de propriétés](../ide/web-references-property-page.md)  
  
26. [XML Data Generator Tool, page de propriétés](../ide/xml-data-generator-tool-property-page.md)  
  
27. [Outil Générateur de documents XML, page de propriétés](../ide/xml-document-generator-tool-property-pages.md)  
  
## Voir aussi  
 [Comment : créer et supprimer les dépendances d'un projet](../Topic/How%20to:%20Create%20and%20Remove%20Project%20Dependencies.md)   
 [Comment : créer et modifier des configurations](../Topic/How%20to:%20Create%20and%20Edit%20Configurations.md)   
 [Déploiement d'applications](http://msdn.microsoft.com/fr-fr/4ff8881d-0daf-47e7-bfe7-774c625031b4)