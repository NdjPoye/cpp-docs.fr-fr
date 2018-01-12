---
title: "Assistant Gestionnaire d’événements | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-ide
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.codewiz.eventhandler.overview
dev_langs: C++
helpviewer_keywords: Event Handler Wizard [C++]
ms.assetid: af8e1835-94b1-4d9a-b353-c519e011d3a1
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ccb80add8a98b9251a7ccbb5c85bf98b610a22e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="event-handler-wizard"></a>Assistant Gestionnaire d'événements
Cet Assistant ajoute un gestionnaire d’événements pour un contrôle de boîte de dialogue à la classe de votre choix. Si vous ajoutez un gestionnaire d’événements à partir de la [fenêtre Propriétés](/visualstudio/ide/reference/properties-window), vous pouvez l’ajouter uniquement à la classe qui implémente la boîte de dialogue. Consultez [Ajout de gestionnaires d’événements pour les contrôles de boîte de dialogue](../windows/adding-event-handlers-for-dialog-box-controls.md) pour plus d’informations.  
  
 **Nom de la commande**  
 Identifie le contrôle sélectionné, pour lequel le Gestionnaire d’événements est ajouté. Cette case n’est pas disponible.  
  
 **Type de message**  
 Affiche la liste des gestionnaires de messages possibles en cours pour le contrôle sélectionné.  
  
 **Nom du Gestionnaire**  
 Affiche le nom de la fonction qui est ajoutée pour gérer l’événement. Par défaut, le nom est basé sur le type de message et de la commande, précédé de « On ». Par exemple, pour le bouton appelé `IDC_BUTTON1`, le type de message `BN_CLICKED` affiche le nom du gestionnaire `OnBnClickedButton1`.  
  
 **Liste de classes**  
 Affiche les classes disponibles auxquels vous pouvez ajouter un gestionnaire d’événements. La classe de la boîte de dialogue sélectionnée s’affiche en rouge.  
  
 **Description du Gestionnaire**  
 Fournit une description de l’élément sélectionné dans le **type de Message** boîte. Cette case n’est pas disponible.  
  
 **Ajouter et modifier**  
 Ajoute le Gestionnaire de messages à l’objet ou la classe sélectionnée et ouvre l’éditeur de texte à la nouvelle fonction qui vous pouvez d’ajouter le code de gestionnaire de notification de contrôle.  
  
 **Modifier le code**  
 Ouvre l’éditeur de texte à la fonction existante sélectionnée afin d’en ajouter ou modifier le code de gestionnaire de notification de contrôle.  
  
## <a name="see-also"></a>Voir aussi  
 [Ajout d’un gestionnaire d’événements](../ide/adding-an-event-handler-visual-cpp.md)