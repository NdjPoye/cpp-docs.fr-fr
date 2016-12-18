---
title: "Traitement des messages de notification dans les contr&#244;les de zone de liste d&#233;roulante &#233;tendue | Microsoft Docs"
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
  - "zones de liste déroulante étendues, notifications"
  - "notifications, contrôles de zone de liste déroulante étendue"
ms.assetid: 4e442758-d054-4746-bb1a-6ff84accb127
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Traitement des messages de notification dans les contr&#244;les de zone de liste d&#233;roulante &#233;tendue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand les utilisateurs interagissent avec la zone de liste déroulante étendue, le contrôle \(`CComboBoxEx`\) envoie des messages de notification à sa fenêtre parente, généralement un objet d’affichage ou de boîte de dialogue. Vous devez gérer ces messages si vous voulez faire quelque chose en réponse. Par exemple, quand l’utilisateur active la liste déroulante ou clique dans la zone d’édition du contrôle, la notification **CBEN\_BEGINEDIT** est envoyée.  
  
 Utilisez la fenêtre Propriétés pour ajouter des gestionnaires de notification à la classe parente pour les messages que vous voulez implémenter.  
  
 La liste suivante décrit les différentes notifications envoyées par le contrôle de zone de liste déroulante étendue.  
  
-   **CBEN\_BEGINEDIT** Envoyée quand l’utilisateur active la liste déroulante ou clique dans la zone d’édition du contrôle.  
  
-   **CBEN\_DELETEITEM** Envoyée quand un élément a été supprimé.  
  
-   **CBEN\_DRAGBEGIN** Envoyée quand l’utilisateur commence à faire glisser l’image de l’élément affichée dans la zone d’édition du contrôle.  
  
-   **CBEN\_ENDEDIT** Envoyée quand l’utilisateur a terminé une opération dans la zone d’édition ou qu’il a sélectionné un élément de la liste déroulante du contrôle.  
  
-   **CBEN\_GETDISPINFO** Envoyée pour récupérer les informations d’affichage sur un élément de rappel.  
  
-   **CBEN\_INSERTITEM** Envoyée quand un nouvel élément a été inséré dans le contrôle.  
  
## Voir aussi  
 [Utilisation de CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Contrôles](../mfc/controls-mfc.md)