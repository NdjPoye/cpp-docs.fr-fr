---
title: "Mappage des messages Windows &#224; votre classe | Microsoft Docs"
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
  - "mappages, messages à la classe de boîte de dialogue"
  - "tables des messages (C++), dans la classe de boîte de dialogue"
  - "tables des messages (C++), mapper les messages Windows aux classes"
  - "messages à la classe de boîte de dialogue"
  - "messages à la classe de boîte de dialogue, mapper"
  - "boîtes de dialogue MFC, messages Windows"
  - "messages Windows (C++), mapper dans les classes de boîte de dialogue"
ms.assetid: a4c6fd1f-1d33-47c9-baa0-001755746d6d
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mappage des messages Windows &#224; votre classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous avez besoin de la boîte de dialogue pour traiter les messages Windows, remplacez les fonctions de gestions appropriées.  Pour cela, utilisez la fenêtre Propriétés à [mappez les messages](../mfc/reference/mapping-messages-to-functions.md) dans la classe de la boîte de dialogue.  Cela écrit un message\-mappage d'entrée pour chaque message et ajoute les fonctions membres responsables de messages à la classe.  Utilisez l'éditeur de code source Visual C\+\+ pour écrire du code dans des gestionnaires de messages.  
  
 Vous pouvez également remplacer les fonctions membres de [CDialog](../mfc/reference/cdialog-class.md) et ses classes de base, notamment [CWnd](../mfc/reference/cwnd-class.md).  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Gestion et mappage des messages](../mfc/message-handling-and-mapping.md)  
  
-   [Fonctions membres couramment substituées](../mfc/commonly-overridden-member-functions.md)  
  
-   [Fonctions membres couramment ajoutées](../mfc/commonly-added-member-functions.md)  
  
## Voir aussi  
 [Boîtes de dialogue](../mfc/dialog-boxes.md)   
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)