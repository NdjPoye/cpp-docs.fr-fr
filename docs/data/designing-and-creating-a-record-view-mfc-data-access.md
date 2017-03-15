---
title: "Conception et cr&#233;ation d&#39;une vue de l&#39;enregistrement (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "Assistants Application (C++), créer des classes d'affichage des enregistrements"
  - "créer des formulaires"
  - "créer des vues d'enregistrements"
  - "formulaires (C++), concevoir"
  - "vues des enregistrements, créer"
  - "vues des enregistrements, concevoir"
ms.assetid: 1d6f5439-754f-4b8b-a19d-841a4657827b
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Conception et cr&#233;ation d&#39;une vue de l&#39;enregistrement (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez créer votre classe de vue d'enregistrement avec l'[Assistant Application MFC](../mfc/reference/database-support-mfc-application-wizard.md).  Si vous utilisez un Assistant Application, il crée la classe de vue d'enregistrement et une ressource de modèle de boîte de dialogue pour elle \(sans contrôles\).  Vous devez utiliser l'éditeur de boîtes de dialogue Visual C\+\+ pour ajouter des contrôles à la ressource de modèle de boîte de dialogue.  En revanche, si vous utilisez **Ajouter une classe**, vous devez d'abord créer la ressource de modèle de boîte de dialogue dans la boîte de dialogue Éditeur, puis créer la classe de vue d'enregistrement.  
  
 Ces informations s'appliquent à `CRecordView` et à `CDaoRecordView`.  
  
#### Pour créer votre vue d'enregistrement avec l'Assistant Application MFC  
  
1.  Voir [Prise en charge des bases de données, Assistant Application MFC](../mfc/reference/database-support-mfc-application-wizard.md).  
  
#### Pour concevoir votre formulaire  
  
1.  Voir [Éditeur de boîte de dialogue](../mfc/dialog-editor.md).  
  
#### Pour créer votre classe de vue d'enregistrement  
  
1.  Voir [Ajout d'un consommateur ODBC MFC](../mfc/reference/adding-an-mfc-odbc-consumer.md).  
  
 Les rubriques suivantes décrivent d'autres aspects de l'utilisation des vues d'enregistrements :  
  
-   [Vues d'enregistrements : prise en charge de la navigation dans une vue d'enregistrement](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)  
  
-   [Vues d'enregistrements : utilisation d'une vue d'enregistrement](../data/using-a-record-view-mfc-data-access.md)  
  
-   [Vues d'enregistrements : remplissage d'une zone de liste à partir d'un second recordset](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md)  
  
## Voir aussi  
 [Vues d'enregistrements \(Accès aux données MFC\)](../data/record-views-mfc-data-access.md)   
 [Recordset \(ODBC\)](../data/odbc/recordset-odbc.md)   
 [Liste de pilotes ODBC](../data/odbc/odbc-driver-list.md)