---
title: "Ajout de fonctionnalit&#233;s &#224; l&#39;aide des Assistants Code | Microsoft Docs"
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
  - "vc.codewiz.classes"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classe (Assistants C++)"
  - "code (Assistants C++)"
  - "projets (C++), ajouter une fonctionnalité"
  - "projets Visual C++, ajouter une fonctionnalité"
  - "Assistants (C++), code"
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout de fonctionnalit&#233;s &#224; l&#39;aide des Assistants Code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque vous avez créé un projet, il se peut que vous souhaitiez le modifier ou lui ajouter des fonctionnalités.  Vous pouvez notamment créer de nouvelles classes, ajouter de nouvelles fonctions membres et variables membres, ainsi qu'ajouter des méthodes et des propriétés d'automation.  Les Assistants Code sont destinés à vous aider à exécuter toutes ces opérations.  
  
> [!NOTE]
>  Vous pouvez à présent ajouter des gestionnaires de messages et mapper les messages à ceux\-ci, ainsi que substituer les fonctions virtuelles MFC à l'aide de la [fenêtre Propriétés](../Topic/Properties%20Window.md).  
  
## Accès aux Assistants Code Visual C\+\+  
 Il existe trois emplacements à partir desquels vous pouvez accéder aux Assistants Code Visual C\+\+ :  
  
-   Dans le menu **Projet**, la commande **Ajouter un nouvel élément** vous permet d'afficher la boîte de dialogue `Add New Item`, qui permet d'ajouter de nouveaux fichiers à votre projet.  La commande **Ajouter une classe** affiche la boîte de dialogue [Ajouter une classe](../ide/add-class-dialog-box.md) permettant d'ouvrir les Assistants pour chaque type classe que vous pouvez ajouter à votre projet.  La commande **Ajouter une ressource** affiche la boîte de dialogue [Ajouter une ressource](../windows/add-resource-dialog-box.md) à partir de laquelle vous pouvez créer ou sélectionner une ressource à ajouter à votre projet.  
  
     Si vous sélectionnez une classe ou une interface dans votre projet en affichage de classes, le menu **Projet** affiche également les commandes suivantes :  
  
    -   **Implémenter l'interface** \(à partir d'une classe de contrôle uniquement\)  
  
    -   **Ajouter une fonction**  
  
    -   **Ajouter une variable**  
  
    -   **Ajouter un point de connexion** \(classe ATL uniquement\)  
  
    -   **Ajouter une méthode** \(à partir d'une interface uniquement\)  
  
    -   **Ajout de propriété** \(à partir d'une interface uniquement\)  
  
    -   **Ajouter un événement** \(à partir d'une classe de contrôle uniquement\)  
  
-   Dans l'**Explorateur de solutions**, cliquez avec le bouton droit sur n'importe quel dossier et sélectionnez **Ajouter** dans le menu contextuel pour ajouter de nouveaux fichiers ou des fichiers existants, des dossiers, des éléments, des classes, des ressources et des références Web au projet.  
  
-   À partir de la [fenêtre Affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez avec le bouton droit sur le nœud approprié et sélectionnez **Ajouter** dans le menu contextuel pour ajouter des fonctions, des variables, des classes, des propriétés, des méthodes, des événements, des interfaces, des points de connexion ou un autre code à votre projet.  
  
    > [!NOTE]
    >  Visual Studio ne propose pas d'Assistant pour l'ajout d'une interface à un projet.  Vous pouvez ajouter une interface à un projet ATL ou [ajouter la prise en charge ATL à votre projet MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) en ajoutant un objet simple à l'aide de l'[Assistant Objet simple ATL](../atl/reference/atl-simple-object-wizard.md).  Vous pouvez également ouvrir le fichier .idl du projet et créer l'interface en tapant :  
  
    ```  
    interface IMyInterface {  
    };  
  
    ```  
  
     Pour plus d'informations, consultez [Implémentation d'une interface](../ide/implementing-an-interface-visual-cpp.md) et [Ajout d'objets et de contrôles à un projet ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).  
  
    |Accès à l'Assistant Code à partir de|Description|  
    |------------------------------------------|-----------------|  
    |Ajouter un nouvel élément|Les Assistants Code de la fenêtre Ajouter un nouvel élément ajoutent des fichiers sources à votre projet.  Le cas échéant, des répertoires supplémentaires sont créés pour contenir les fichiers que le moteur de génération du projet peut être amené à rechercher.  Les Assistants Code disponibles à partir de l'icône Ajouter un élément sont les suivants :<br /><br /> -   Ajout de fichiers sources C\+\+ \(.cpp, .h, .idl, .rc, .srf, .def, .rgs\).<br />-   Ajout de fichiers de développement Web \(.html, .asp, .css, .xml\).<br />-   Ajout de fichiers d'utilitaire et de ressources \(.bmp, .cur, .ico, .rct, .sql, .txt\).<br /><br /> Ces Assistants Code ne vous demandent généralement aucune information, mais ajoutent un fichier à votre arborescence de développement.  Vous pouvez renommer le fichier dans la fenêtre des propriétés.|  
    |Explorateur de solutions|Les Assistants Code disponibles à partir de l'Explorateur de solutions dépendent de l'emplacement de votre curseur au moment où vous cliquez avec le bouton droit sur un élément.  Si l'option **Ajouter** ne s'affiche pas lorsque vous cliquez avec le bouton droit sur un élément, déplacez le curseur d'un niveau vers le haut dans l'arborescence de développement et recommencez.  Les Assistants Code placent toujours le code supplémentaire à l'endroit approprié de l'arborescence de développement, peu importe où se trouve votre curseur.  L'Explorateur de solutions propose les Assistants Code suivants :<br /><br /> -   Ajout de classe \(ouvre la boîte de dialogue **Ajouter une classe** qui contient les nouveaux Assistants Code\).<br />-   Ajout de ressource \(Nouveau, Importer ou Personnaliser\).<br />-   Ajout de référence Web.|  
    |Affichage de classes|Les Assistants Code disponibles à partir de l'affichage de classes dépendent de l'emplacement de votre curseur au moment où vous cliquez avec le bouton droit sur un élément.  Si l'option **Ajouter** ne s'affiche pas lorsque vous cliquez avec le bouton droit sur un élément, déplacez le curseur d'un niveau vers le haut dans l'arborescence de la classe et recommencez.  Les Assistants Code placent toujours le code supplémentaire à l'endroit approprié de l'arborescence de développement, peu importe où se trouve votre curseur.  L'affichage de classes propose les Assistants Code suivants :<br /><br /> -   [Ajout de fonction membre](../ide/adding-a-member-function-visual-cpp.md).<br />-   [Ajout de variable membre](../ide/adding-a-member-variable-visual-cpp.md).<br />-   [Ajouter une classe](../ide/adding-a-class-visual-cpp.md).<br />-   [Implémentation de l'interface](../ide/implement-interface-wizard.md) \(à partir d'une classe de contrôle uniquement\)<br />-   [Ajouter un point de connexion](../ide/implement-connection-point-wizard.md) \(classe ATL uniquement\)<br />-   [Ajouter une méthode](../ide/add-method-wizard.md) \(à partir d'une interface uniquement\)<br />-   [Ajout de propriété](../ide/names-add-property-wizard.md) \(à partir d'une interface uniquement\)<br />-   [Ajouter un événement](../ide/add-event-wizard.md) \(à partir d'une classe de contrôle uniquement\)<br /><br /> Si vous cliquez sur Ajouter une classe, la boîte de dialogue **Ajouter une classe** s'ouvre, vous permettant d'accéder à tous les nouveaux Assistants Code d'ajout d'une classe.|  
  
## Voir aussi  
 [Substitution d'une fonction virtuelle](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Parcours de la structure de classe](../ide/navigating-the-class-structure-visual-cpp.md)   
 [Création de projets de bureau à l'aide des Assistants Application](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Types de projets Visual C\+\+](../ide/visual-cpp-project-types.md)   
 [Types de fichiers créés pour les projets Visual C\+\+](../ide/file-types-created-for-visual-cpp-projects.md)