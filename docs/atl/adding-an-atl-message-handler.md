---
title: "Ajout d&#39;un gestionnaire de messages ATL | Microsoft Docs"
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
  - "ATL, gestionnaires de messages"
  - "ATL, fenêtres"
  - "message handlers [C++]"
  - "message handling [C++], ATL message handler"
  - "windows [C++], ATL"
ms.assetid: cdea38a1-0d9b-4f8d-bbd5-b4f063fb3eeb
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Ajout d&#39;un gestionnaire de messages ATL
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour ajouter un gestionnaire de messages \(une fonction membre qui gère les messages windows\) à un contrôle, commencez par le contrôle dans l'Affichage de classes.  Puis ouvrez la fenêtre **Propriétés** , sélectionnez l'icône de **Messages** , puis cliquez sur le contrôle de liste déroulante dans la zone contraire du message requis.  Cela ajoutera une déclaration du gestionnaire de messages dans le fichier d'en\-tête et une implémentation squelette du contrôle du gestionnaire dans le fichier .cpp du contrôle.  Il ajoute également la table des messages et ajoute une entrée pour le gestionnaire.  
  
 Ajouter un gestionnaire de messages dans ATL est semblable à ajouter un gestionnaire de messages à une classe MFC.  Consultez l' [Ajouter un gestionnaire de messages MFC](../mfc/reference/adding-an-mfc-message-handler.md) pour plus d'informations.  
  
 Les conditions suivantes s'appliquent uniquement à ajouter un gestionnaire de messages ATL :  
  
-   Les gestionnaires de messages suivent la même convention d'affectation de noms que MFC.  
  
-   Les nouvelles entrées de la table des messages sont ajoutées dans la table des messages principale.  L'assistant ne reconnaît pas les tables des messages secondaires et le chaînage.  
  
## Voir aussi  
 [Implementing a Window](../atl/implementing-a-window.md)