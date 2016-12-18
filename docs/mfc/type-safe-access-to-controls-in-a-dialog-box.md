---
title: "Acc&#232;s de type s&#233;curis&#233; aux contr&#244;les d&#39;une bo&#238;te de dialogue | Microsoft Docs"
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
  - "contrôles communs (C++), dans des boîtes de dialogue"
  - "contrôles (MFC), accéder dans les boîtes de dialogue"
  - "boîtes de dialogue (C++), accès de type sécurisé aux contrôles"
  - "boîtes de dialogue MFC, accès de type sécurisé aux contrôles"
  - "accès sécurisé aux contrôles de boîte de dialogue"
  - "accès de type sécurisé aux contrôles de boîte de dialogue"
  - "contrôles Windows communs (C++), dans des boîtes de dialogue"
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Acc&#232;s de type s&#233;curis&#233; aux contr&#244;les d&#39;une bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les contrôles d'une boîte de dialogue peuvent utiliser les interfaces des classes de contrôles MFC telles que `CListBox` et `CEdit`.  Vous pouvez créer un objet contrôle et l'attacher à un contrôle de boîte de dialogue.  Vous pouvez ensuite accéder au contrôle via son interface de classe, en appelant des fonctions membres pour agir sur le contrôle.  Les méthodes décrites ici sont conçues pour vous donner un accès de type sécurisé à un contrôle.  Ceci est particulièrement utile pour les contrôles tels que les zones d'édition et les zones de liste.  
  
 Vous disposez de deux méthodes pour établir une connexion entre un contrôle d'une boîte de dialogue et une variable membre de contrôle C\+\+ dans une classe dérivée de `CDialog` :  
  
-   [Sans Assistants Code](../mfc/type-safe-access-to-controls-without-code-wizards.md)  
  
-   [Avec des Assistants Code](../mfc/type-safe-access-to-controls-with-code-wizards.md)  
  
## Voir aussi  
 [Boîtes de dialogue](../mfc/dialog-boxes.md)