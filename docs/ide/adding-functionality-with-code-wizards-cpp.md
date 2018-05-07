---
title: Ajout de fonctionnalités à l’aide des Assistants de Code (C++) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- vc.codewiz.classes
dev_langs:
- C++
helpviewer_keywords:
- code wizards [C++]
- wizards [C++], code
- Visual C++ projects, adding functionality
- projects [C++], adding functionality
- class wizards [C++]
ms.assetid: 6afb7ef9-7056-423d-b244-91bb4236d1d7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 55a2bb282d19a48cfd510056e327e7abca4de4ad
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="adding-functionality-with-code-wizards-c"></a>Ajout de fonctionnalités avec les Assistants Code (C++)
Une fois que vous avez créé un projet, vous devez modifier ou ajouter des fonctionnalités. Ces tâches comprennent la création de nouvelles classes, ajouter de nouvelles fonctions membres et variables, ajout Automation et méthodes. Les Assistants code sont conçus pour vous permettre d’effectuer toutes ces tâches.  
  
> [!NOTE]
>  Vous pouvez maintenant ajouter des gestionnaires de messages et mapper les messages à ceux-ci et substituer les fonctions virtuelles MFC à l’aide de la [fenêtre Propriétés](/visualstudio/ide/reference/properties-window).  
  
## <a name="accessing-visual-c-code-wizards"></a>L’accès aux Assistants Code Visual C++  
 Il existe trois emplacements où vous pouvez accéder aux Assistants code Visual C++ :  
  
-   Sur le **projet** menu, le **ajouter un nouvel élément** commande vous permet d’élever le `Add New Item` boîte de dialogue qui vous permet d’ajouter de nouveaux fichiers à votre projet. Le **ajouter une classe** commande affiche le [ajouter une classe](../ide/add-class-dialog-box.md) boîte de dialogue Ouvrir à son tour les Assistants pour chacun de la classe de types que vous pouvez ajouter à votre projet. Le **ajouter une ressource** commande affiche le [ajouter une ressource](../windows/add-resource-dialog-box.md) boîte de dialogue, à partir de laquelle vous pouvez créer ou sélectionner une ressource à ajouter à votre projet.  
  
     Si vous mettez en surbrillance une classe ou une interface dans votre projet dans l’affichage de classes, les **projet** menu affiche également les commandes suivantes :  
  
    -   **Implémenter l’Interface** (à partir d’une classe de contrôle)  
  
    -   **Ajouter une fonction**  
  
    -   **Ajouter une Variable**  
  
    -   **Ajouter un Point de connexion** (classe ATL uniquement)  
  
    -   **Ajoutez la méthode** (à partir d’une interface uniquement)  
  
    -   **Ajoutez la propriété** (à partir d’une interface uniquement)  
  
    -   **Ajouter un événement** (à partir d’une classe de contrôle)  
  
-   Dans **l’Explorateur de solutions**, droit sur n’importe quel dossier, puis en cliquant sur **ajouter** à partir du raccourci menu vous permet d’ajouter les fichiers nouveaux ou existants, d’autres dossiers, éléments, classes, les ressources et les références Web pour le projet.  
  
-   À partir de la [fenêtre Affichage de classes](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925), droit sur le nœud approprié et en cliquant sur **ajouter** à partir du raccourci menu vous permet d’ajouter des fonctions, variables, classes, propriétés, méthodes, événements, interfaces, points de connexion ou un autre code à votre projet.  
  
    > [!NOTE]
    >  Visual Studio ne fournit pas un Assistant permettant d’ajouter une interface à un projet. Vous pouvez ajouter une interface à un projet ATL ou à un [ajoutant la prise en charge ATL à votre projet MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) en ajoutant un objet simple à l’aide de la [Assistant objet Simple ATL](../atl/reference/atl-simple-object-wizard.md). Vous pouvez également ouvrir le fichier du projet .idl et créer l’interface en tapant :  
  
    ```  
    interface IMyInterface {  
    };  
  
    ```  
  
     Consultez [implémentant une Interface](../ide/implementing-an-interface-visual-cpp.md) et [Ajout d’objets et des contrôles à un projet ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md) pour plus d’informations.  
  
    |Assistant de code d’accès à partir de|Description|  
    |-----------------------------|-----------------|  
    |Ajouter un nouvel élément|Les Assistants de code ajouter un nouvel élément ajoutent des fichiers sources à votre projet. Si nécessaire, des répertoires supplémentaires sont créés pour contenir les fichiers où, le moteur de génération de projet s’attend à trouver. Assistants code disponibles à partir de l’icône Ajouter un élément sont les suivantes :<br /><br /> -Ajouter des fichiers de code source C++ (.cpp, .h, .idl, .rc, .srf, .def, .rgs).<br />-Ajouter des fichiers de développement Web (.html, .asp, .css, .xml).<br />-Ajouter des fichiers d’utilitaire et de ressources (.bmp, .cur, .ico, .rct, .sql, .txt).<br /><br /> En règle générale, ces Assistants code ne pas demanderont les informations mais ajouter un fichier à votre arborescence de développement. Vous pouvez renommer le fichier dans la fenêtre Propriétés.|  
    |Explorateur de solutions|Les Assistants code disponibles à partir de l’Explorateur de solutions dépendent d’où votre sélection du curseur est lorsque vous cliquez sur un élément. Si le **ajouter** option n’apparaît pas lorsque vous cliquez sur un élément, puis déplacez le curseur d’un niveau dans l’arborescence de développement et recommencez l’opération. Les Assistants code toujours placera le code supplémentaire dans l’emplacement approprié dans l’arborescence de développement, sans que lorsque le curseur est. Assistants code disponibles à partir de l’Explorateur de solutions sont les suivantes :<br /><br /> -Ajouter une classe (ouvre le **ajouter une classe** boîte de dialogue contient les nouveaux Assistants code).<br />-Ajouter une ressource (nouveau, importer ou personnaliser).<br />-Ajouter une référence Web.|  
    |Affichage de classes|Les Assistants code disponibles à partir de l’affichage de classes dépendent où votre sélection du curseur est lorsque vous avec le bouton droit sur un élément. Si le **ajouter** option n’apparaît pas lorsque vous avec le bouton droit sur un élément, puis déplacez le curseur d’un niveau dans l’arborescence de la classe et recommencez l’opération. Les Assistants code toujours placera le code supplémentaire dans l’emplacement approprié dans l’arborescence de développement, sans que lorsque le curseur est. Assistants code disponibles à partir de l’affichage de classes sont les suivantes :<br /><br /> -   [Ajouter une fonction membre](../ide/adding-a-member-function-visual-cpp.md).<br />-   [Ajouter une Variable membre](../ide/adding-a-member-variable-visual-cpp.md).<br />-   [Ajouter une classe](../ide/adding-a-class-visual-cpp.md).<br />-   [Implémenter l’Interface](../ide/implement-interface-wizard.md) (à partir d’une classe de contrôle)<br />-   [Ajouter un Point de connexion](../ide/implement-connection-point-wizard.md) (classe ATL uniquement)<br />-   [Ajoutez la méthode](../ide/add-method-wizard.md) (à partir d’une interface uniquement)<br />-   [Ajoutez la propriété](../ide/names-add-property-wizard.md) (à partir d’une interface uniquement)<br />-   [Ajouter un événement](../ide/add-event-wizard.md) (à partir d’une classe de contrôle)<br /><br /> La sélection d’ajout de classes s’ouvre le **ajouter une classe** boîte de dialogue qui vous permet d’accéder à tous les nouveaux Assistants code d’ajouter une classe.|  
  
## <a name="see-also"></a>Voir aussi  
 [Une fonction virtuelle de substitution](../ide/overriding-a-virtual-function-visual-cpp.md)   
 [Navigation dans la Structure de classe](../ide/navigating-the-class-structure-visual-cpp.md)   
 [Création de projets du Bureau à l’aide des Assistants Application](../ide/creating-desktop-projects-by-using-application-wizards.md)   
 [Types de projet Visual C++](../ide/visual-cpp-project-types.md)   
 [Types de fichiers créés pour les projets Visual C++](../ide/file-types-created-for-visual-cpp-projects.md)