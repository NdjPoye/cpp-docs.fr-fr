---
title: "Ajout d&#39;une propri&#233;t&#233; locale (Visual C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces, ajouter des propriétés"
  - "propriétés (C++), ajouter aux interfaces"
ms.assetid: 37bd4db7-efd3-4faa-87ad-64902ed16a36
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;une propri&#233;t&#233; locale (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser l'[Assistant Ajout de propriété](../ide/names-add-property-wizard.md) pour ajouter une méthode à une interface dans votre projet.  
  
### Pour ajouter une propriété à votre objet  
  
1.  Dans l'[Affichage de classes](http://msdn.microsoft.com/fr-fr/8d7430a9-3e33-454c-a9e1-a85e3d2db925), cliquez avec le bouton droit sur le nom de l'interface à laquelle vous souhaitez ajouter la propriété.  
  
    > [!NOTE]
    >  Vous pouvez également ajouter des propriétés aux dispinterfaces qui, sauf si le projet est avec attributs, sont imbriquées dans le nœud de bibliothèque.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une propriété**.  
  
3.  Dans l'[Assistant Ajout de propriété](../ide/names-add-property-wizard.md), indiquez les informations pour créer la propriété.  
  
4.  Spécifiez tous les paramètres IDL \(Interface Definition Language\) de la propriété sur la page [Attributs IDL](../ide/idl-attributes-add-property-wizard.md) de l'Assistant.  
  
5.  Cliquez sur **Terminer** pour ajouter la propriété.  
  
 Les méthodes **Get** et `Put` de la propriété sont affichées sous la forme de deux icônes dans l'Affichage de classes, sous l'interface où elle est définie.  Vous pouvez double\-cliquer sur l'une ou l'autre des icônes pour afficher la déclaration de propriété dans le fichier .idl.  
  
-   Pour les interfaces ATL, les fonctions **Get** et **Put** sont ajoutées au fichier .cpp tandis que les références à ces fonctions sont ajoutées au fichier .h.  
  
-   Pour les dispinterfaces MFC, si vous sélectionnez **Variable membre** comme type d'implémentation, une méthode et une variable sont ajoutées à la classe qui l'a implémentée.  Si vous sélectionnez **Méthodes Get\/Set** comme type d'implémentation, deux méthodes sont ajoutées à la classe qui l'a implémentée.  
  
## Voir aussi  
 [Création d'une interface COM](../ide/creating-a-com-interface-visual-cpp.md)   
 [Modification d'une interface COM](../ide/editing-a-com-interface.md)   
 [Le composant COM \(Component Object Model\)](http://msdn.microsoft.com/library/windows/desktop/ms694363)   
 [Pointeurs d'interface et interfaces](http://msdn.microsoft.com/library/windows/desktop/ms688484)