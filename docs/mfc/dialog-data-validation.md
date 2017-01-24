---
title: "Validation de donn&#233;es de bo&#238;tes de dialogue | Microsoft Docs"
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
  - "données (validation) (C++), boîtes de dialogue"
  - "données (validation) (C++), boîtes de message"
  - "DDV (validation de données de boîtes de dialogue) (C++)"
  - "boîtes de dialogue (C++), valider des données"
  - "valider des données (C++), entrée de données de boîte de dialogue"
  - "valider des données (C++), boîtes de message"
ms.assetid: f070c309-2044-4ff2-8c92-1ec1ea84af58
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Validation de donn&#233;es de bo&#238;tes de dialogue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez spécifier la validation en plus d ' échange de données en appelant les fonctions de DDV, comme illustré dans l'exemple de [Échange de données de boîtes de dialogue](../mfc/dialog-data-exchange.md).  L'appel de `DDV_MaxChars` dans l'exemple vérifie que la chaîne entrée dans le contrôle de la zone de texte n'est pas plus de 20 caractères.  La fonction de DDV alerte généralement l'utilisateur avec un message si la validation échoue et met l'accent sur le contrôle offensant l'utilisateur peut réentrer les données.  Une fonction de DDV pour un contrôle donné doit être appelée immédiatement après la fonction de DDX pour le même contrôle.  
  
 Vous pouvez aussi définir des classes Principal personnalisées.  Pour plus d'informations sur ce point et sur d'autres aspects de DDX et de DDV, consultez l'[Note technique 26 en MFC](../mfc/tn026-ddx-and-ddv-routines.md).  
  
 [Assistant Ajout de variable membre](../ide/add-member-variable-wizard.md) écrit tous les appels de DDX et de DDV dans la configuration de données pour vous.  
  
## Voir aussi  
 [Échange et validation de données de boîtes de dialogue](../mfc/dialog-data-exchange-and-validation.md)   
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)   
 [Échange de données de boîtes de dialogue](../mfc/dialog-data-exchange.md)