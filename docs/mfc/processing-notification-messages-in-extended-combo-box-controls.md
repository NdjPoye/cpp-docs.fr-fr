---
title: "Traitement des Messages de Notification dans étendus des contrôles de zone de liste déroulante | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- extended combo boxes [MFC], notifications
- notifications [MFC], extended combo box controls
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a78e7b9fd8f9c67f14a4bb51088866785d372cca
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-extended-combo-box-controls"></a>Traitement des messages de notification dans les contrôles de zone de liste déroulante étendue
Quand les utilisateurs interagissent avec la zone de liste déroulante étendue, le contrôle (`CComboBoxEx`) envoie des messages de notification à sa fenêtre parente, généralement un objet d’affichage ou de boîte de dialogue. Vous devez gérer ces messages si vous voulez faire quelque chose en réponse. Par exemple, quand l’utilisateur active la liste déroulante ou clique dans la zone d’édition du contrôle, la notification **CBEN_BEGINEDIT** est envoyée.  
  
 Utilisez la fenêtre Propriétés pour ajouter des gestionnaires de notification à la classe parente pour les messages que vous voulez implémenter.  
  
 La liste suivante décrit les différentes notifications envoyées par le contrôle de zone de liste déroulante étendue.  
  
-   **CBEN_BEGINEDIT** Envoyée quand l’utilisateur active la liste déroulante ou clique dans la zone d’édition du contrôle.  
  
-   **CBEN_DELETEITEM** Envoyée quand un élément a été supprimé.  
  
-   **CBEN_DRAGBEGIN** Envoyée quand l’utilisateur commence à faire glisser l’image de l’élément affichée dans la zone d’édition du contrôle.  
  
-   **CBEN_ENDEDIT** Envoyée quand l’utilisateur a terminé une opération dans la zone d’édition ou qu’il a sélectionné un élément de la liste déroulante du contrôle.  
  
-   **CBEN_GETDISPINFO** Envoyée pour récupérer les informations d’affichage sur un élément de rappel.  
  
-   **CBEN_INSERTITEM** Envoyée quand un nouvel élément a été inséré dans le contrôle.  
  
## <a name="see-also"></a>Voir aussi  
 [Utilisation de CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Contrôles](../mfc/controls-mfc.md)

