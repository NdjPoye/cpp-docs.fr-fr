---
title: "Impl&#233;mentation d&#39;une interface (Visual C++) | Microsoft Docs"
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
  - "interfaces, implémenter"
ms.assetid: 72f8731b-7e36-45db-8b10-7ef211a773cd
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Impl&#233;mentation d&#39;une interface (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour implémenter une interface, vous devez avoir créé un projet en tant qu'application COM ATL ou MFC intégrant la prise en charge ATL.  Vous pouvez utiliser l'[Assistant Projet ATL](../atl/reference/atl-project-wizard.md) pour créer une application ATL, ou vous pouvez également [ajouter un objet ATL à votre application MFC](../mfc/reference/adding-atl-support-to-your-mfc-project.md) pour implémenter la prise en charge ATL pour une application MFC.  
  
 Lorsque vous créez un projet, pour implémenter une interface, vous devez d'abord ajouter un objet ATL.  Pour obtenir la liste des Assistants permettant d'ajouter des objets à votre projet ATL, consultez [Ajout d'objets et de contrôles à un projet ATL](../atl/reference/adding-objects-and-controls-to-an-atl-project.md).  
  
> [!NOTE]
>  L'Assistant ne prend pas en charge les dialogues ATL, les services Web XML utilisant ATL, les objets de performance ou les compteurs de performance.  
  
 Si vous [ajoutez un contrôle ATL](../atl/reference/adding-an-atl-control.md), vous pouvez spécifier l'implémentation éventuelle des interfaces par défaut énumérées à la page [Interfaces](../atl/reference/interfaces-atl-control-wizard.md) de cet Assistant et définies dans le fichier atlcom.h.  
  
 Lorsque vous avez ajouté l'objet ou le contrôle, vous pouvez implémenter d'autres interfaces, situées dans n'importe quelle bibliothèque de types disponible, à l'aide de l'Assistant Implémentation d'interface.  
  
 Si vous ajoutez une nouvelle interface, vous devez l'ajouter manuellement au fichier .idl du projet.  Pour plus d'informations, consultez [Ajout d'une nouvelle interface à un projet ATL](../atl/reference/adding-a-new-interface-in-an-atl-project.md).  
  
### Pour implémenter une interface  
  
1.  Dans l'Affichage de classes, cliquez avec le bouton droit sur le nom de classe de votre objet ATL.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Implémenter l'interface** pour afficher l'[Assistant Implémentation d'interface](../ide/implement-interface-wizard.md).  
  
3.  Sélectionnez les interfaces à implémenter dans les bibliothèques de types appropriées, puis cliquez sur **Terminer**.  
  
4.  Dans l'Affichage de classes, développez le nœud Bases et Interfaces de l'objet pour afficher l'interface que vous avez implémentée, puis développez le nœud de l'interface pour afficher ses propriétés, méthodes et événements disponibles.  
  
    > [!NOTE]
    >  Vous pouvez également utiliser l'[Explorateur d'objets](http://msdn.microsoft.com/fr-fr/f89acfc5-1152-413d-9f56-3dc16e3f0470) pour examiner les membres de l'interface.  
  
## Voir aussi  
 [Création d'une interface COM](../ide/creating-a-com-interface-visual-cpp.md)   
 [Modification d'une interface COM](../ide/editing-a-com-interface.md)