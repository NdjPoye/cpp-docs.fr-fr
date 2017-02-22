---
title: "Assistant Gestionnaire d&#39;&#233;v&#233;nements | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.eventhandler.overview"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Gestionnaire d'événements (Assistant C++)"
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Assistant Gestionnaire d&#39;&#233;v&#233;nements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet Assistant ajoute à la classe de votre choix un gestionnaire d'événements relatif à un contrôle de boîte de dialogue.  Si vous ajoutez un gestionnaire d'événements à partir de la [fenêtre Propriétés](../Topic/Properties%20Window.md), vous pouvez l'ajouter uniquement à la classe qui implémente la boîte de dialogue.  Pour plus d'informations, consultez [Ajout de gestionnaires d'événements pour les contrôles de boîte de dialogue](../mfc/adding-event-handlers-for-dialog-box-controls.md).  
  
 **Nom de la commande**  
 Identifie le contrôle sélectionné pour lequel le gestionnaire d'événements est ajouté.  Cette zone n'est pas disponible.  
  
 **Type de message**  
 Affiche la liste des gestionnaires de messages possibles en cours pour le contrôle sélectionné.  
  
 **Nom du gestionnaire de fonctions**  
 Affiche le nom de la fonction qui est ajoutée pour gérer l'événement.  Par défaut, le nom est basé sur le type de message et la commande, précédé de « On ».  Par exemple, pour le bouton appelé `IDC_BUTTON1`, le type de message `BN_CLICKED` affiche le nom du gestionnaire de fonctions `OnBnClickedButton1`.  
  
 **Liste de classes**  
 Affiche les classes disponibles auxquelles vous pouvez ajouter un gestionnaire d'événements.  La classe de la boîte de dialogue sélectionnée apparaît en rouge.  
  
 **Description du gestionnaire**  
 Fournit une description de l'élément sélectionné dans la zone **Type de message**.  Cette zone n'est pas disponible.  
  
 **Ajouter**  
 Ajoute le gestionnaire d'événements à la classe ou à l'objet sélectionné, puis ouvre l'éditeur de texte à l'emplacement de la nouvelle fonction pour vous permettre d'ajouter le code du gestionnaire de notification de contrôle.  
  
 **Modifier**  
 Ouvre l'éditeur de texte à l'emplacement de la fonction existante sélectionnée pour vous permettre d'ajouter ou de modifier le code du gestionnaire de notification de contrôle.  
  
## Voir aussi  
 [Ajout d'un gestionnaire d'événements](../ide/adding-an-event-handler-visual-cpp.md)