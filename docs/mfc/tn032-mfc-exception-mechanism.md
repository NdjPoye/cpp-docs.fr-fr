---
title: "TN032&#160;: m&#233;canisme d&#39;exception MFC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.mfc.exceptions"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CException (classe), utilisation"
  - "MFC, exceptions"
  - "TN032"
ms.assetid: 0271f0aa-82cb-47a2-b7ea-e88126fc7e43
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# TN032&#160;: m&#233;canisme d&#39;exception MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les versions antérieures de Visual C\+\+ ne prenaient pas en charge le mécanisme standard d'exception de C\+\+, et MFC fournissait les macros **TRY\/CATCH\/THROW** utilisées à la place.  Cette version de Visual C\+\+ prend entièrement en charge des exceptions C\+\+.  Cette remarque couvre certains détails d'implémentation avancés des macros précédentes et comment inclure automatiquement les objets basés sur la pile de nettoyage.  Puisque les exceptions C\+\+ prennent en charge la progression de la pile par défaut, cette note technique n'est plus nécessaire.  
  
 Reportez\-vous à [Exceptions : Utiliser la macro MFC et les exceptions C\+\+](../mfc/exceptions-using-mfc-macros-and-cpp-exceptions.md) pour plus d'informations sur les différences entre les macros MFC les nouveaux mots clés C\+\+.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)