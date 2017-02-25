---
title: "Cr&#233;ation de votre classe de bo&#238;te de dialogue | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "boîtes de dialogue (C++), créer"
  - "classes de boîte de dialogue, Assistant Ajouter une classe"
  - "classes de boîte de dialogue, créer"
  - "fichiers (C++), créer"
  - "boîtes de dialogue MFC, créer"
ms.assetid: d5321741-da41-47a8-bb1c-6a0e8b28c4c1
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Cr&#233;ation de votre classe de bo&#238;te de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour chaque boîte de dialogue dans votre programme, créez une nouvelle classe de dialogue pour travailler avec la ressource de dialogue.  
  
 [Ajouter une classe](../ide/adding-a-class-visual-cpp.md) explique comment créer une nouvelle classe de dialogue.  Lorsque vous créez une classe de dialogue à l'aide de la classe d'ajouter, elle écrit les éléments suivants dans les fichiers .H et .CPP que vous spécifiez :  
  
 Dans le fichier .H :  
  
-   Une déclaration de classe pour la classe de dialogue.  La classe dérive de [CDialog](../mfc/reference/cdialog-class.md).  
  
 Dans le fichier .CPP :  
  
-   Une table des messages pour la classe.  
  
-   Un constructeur standard pour la boîte de dialogue.  
  
-   Une substitution de la fonction membre de [DoDataExchange](../Topic/CWnd::DoDataExchange.md).  Modifiez cette fonction.  Elle est utilisée pour l'échange de données de boîtes de dialogue et les fonctions de validation comme décrit plus loin dans [Échange de données de boîtes de dialogue et validation](../mfc/dialog-data-exchange-and-validation.md).  
  
## Voir aussi  
 [Création d'une classe de boîte de dialogue à l'aide des Assistants Code](../mfc/creating-a-dialog-class-with-code-wizards.md)   
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)