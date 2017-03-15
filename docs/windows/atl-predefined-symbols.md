---
title: "ATL Predefined Symbols | Microsoft Docs"
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
  - "symbols, ATL predefined"
  - "ATL symbols"
ms.assetid: 60d8f4e6-6ed9-47f3-9051-e4bf34384456
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL Predefined Symbols
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces symboles sont définis dans les fichiers d'en\-tête ATL, mais ils prennent en charge les fonctions et les actions standard des applications Windows.  Ces symboles sont utilisés principalement avec les boîtes de dialogue.  Lorsque vous utilisez des boîtes de dialogue et des contrôles dans l'[Éditeur de boîtes de dialogue](../mfc/dialog-editor.md), ces symboles s'affichent dans la fenêtre Propriétés associée aux contrôles courants.  Par exemple, si votre boîte de dialogue contient un bouton Annuler, cette commande est associée au symbole IDCANCEL dans la [fenêtre Propriétés](../Topic/Properties%20Window.md).  
  
|||  
|-|-|  
|IDABORT|Contrôle : bouton Abandonner d'une boîte de dialogue|  
|IDC\_STATIC|Contrôle : contrôle Static|  
|IDCANCEL|Contrôle : bouton Annuler d'une boîte de dialogue|  
|IDIGNORE|Contrôle : bouton Ignorer d'une boîte de dialogue|  
|IDNO|Contrôle : bouton Non d'une boîte de dialogue|  
|IDOK|Contrôle : bouton OK d'une boîte de dialogue|  
|IDR\_ACCELERATOR1|Ressource : table d'accélérateurs|  
|IDRETRY|Contrôle : bouton Réessayer d'une boîte de dialogue|  
|IDS\_PROJNAME|Chaîne : nom actuel de l'application|  
|IDYES|Contrôle : bouton Oui d'une boîte de dialogue|  
  
## Configuration requise  
 ATL  
  
## Voir aussi  
 [Predefined Symbol IDs](../windows/predefined-symbol-ids.md)   
 [Symbols: Resource Identifiers](../mfc/symbols-resource-identifiers.md)