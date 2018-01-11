---
title: "Ajout d’un gestionnaire d’événements (Visual C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.eventhandler.overview
dev_langs: C++
helpviewer_keywords:
- event handlers, adding
- properties [Visual Studio], MSBuild
- MSBuild, properties
ms.assetid: 050bebf0-a9e0-474b-905c-796fe5ac8fc3
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f9a5380bf335a13bbf7b2f54840c9d1160187167
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-event-handler-visual-c"></a>Ajout d'un gestionnaire d'événements (Visual C++)
À partir de l’éditeur de ressources, vous pouvez ajouter un gestionnaire d’événements, ou modifier un gestionnaire d’événements existant, un contrôle de boîte de dialogue à l’aide du [Assistant Gestionnaire d’événements](../ide/event-handler-wizard.md).  
  
 Vous pouvez ajouter un événement à la classe implémentant la boîte de dialogue à l’aide de la [fenêtre Propriétés](/visualstudio/ide/reference/properties-window). Si vous souhaitez ajouter l’événement à une classe autre que la classe de boîte de dialogue, utilisez l’Assistant Gestionnaire d’événements.  
  
### <a name="to-add-an-event-handler-to-a-dialog-box-control"></a>Pour ajouter un gestionnaire d’événements à un contrôle de boîte de dialogue  
  
1.  Double-cliquez sur la ressource de boîte de dialogue dans [affichage des ressources](../windows/resource-view-window.md) pour ouvrir la ressource de boîte de dialogue qui contient le contrôle dans le [éditeur de boîte de dialogue](../windows/dialog-editor.md).  
  
2.  Cliquez sur le contrôle pour lequel vous souhaitez gérer l’événement de notification.  
  
3.  Dans le menu contextuel, cliquez sur **ajouter un gestionnaire d’événements** pour afficher l’Assistant Gestionnaire d’événements.  
  
4.  Sélectionnez l’événement dans le **type de Message** case pour ajouter à la classe sélectionnée dans la **liste de classes** boîte.  
  
5.  Acceptez le nom par défaut dans le **nom du Gestionnaire de** zone, ou fournir le nom de votre choix.  
  
6.  Cliquez sur **ajouter et modifier** pour ajouter le Gestionnaire d’événements au projet et ouvrez l’éditeur de texte à la nouvelle fonction pour ajouter le code de gestionnaire d’événements approprié.  
  
     Si le type de message sélectionné possède déjà un gestionnaire d’événements pour la classe sélectionnée, **ajouter et modifier** n’est pas disponible, et **modifier le code** n’est disponible. Cliquez sur **modifier le code** pour ouvrir l’éditeur de texte à la fonction existante.  
  
 Sinon, vous pouvez ajouter des gestionnaires d’événements à partir de la [fenêtre Propriétés](/visualstudio/ide/reference/properties-window). Consultez [Ajout de gestionnaires d’événements pour les contrôles de boîte de dialogue](../windows/adding-event-handlers-for-dialog-box-controls.md) pour plus d’informations.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout de fonctionnalités à l’aide des Assistants Code](../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d’une classe](../ide/adding-a-class-visual-cpp.md)   
 [Ajout d’une Variable membre](../ide/adding-a-member-variable-visual-cpp.md)   
 [Ajout d’une fonction membre](../ide/adding-a-member-function-visual-cpp.md)   
 [Gestionnaire de messages MFC](../mfc/reference/adding-an-mfc-message-handler.md)   
 [Navigation dans la Structure de classe](../ide/navigating-the-class-structure-visual-cpp.md)