---
title: "Gestionnaires de commandes pour le d&#233;filement des enregistrements (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "faire défiler des enregistrements (C++)"
  - "vues des enregistrements (C++), défilement"
  - "faire défiler des enregistrements"
ms.assetid: f8b13477-2a37-459e-a30c-806fb78165ac
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestionnaires de commandes pour le d&#233;filement des enregistrements (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes [CRecordView](../mfc/reference/crecordview-class.md) et [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) fournissent une gestion des commandes par défaut pour les commandes standard suivantes :  
  
-   **ID\_RECORD\_MOVE\_FIRST**  
  
-   **ID\_RECORD\_MOVE\_LAST**  
  
-   **ID\_RECORD\_MOVE\_NEXT**  
  
-   **ID\_RECORD\_MOVE\_PREV**  
  
 La fonction de membre `OnMove` des classes `CRecordView` et `CDaoRecordView` fournit une gestion des commandes par défaut pour les quatre commandes, qui permettent de passer d'un enregistrement à l'autre.  À mesure que ces commandes sont exécutées, RFX \(ou DFX\) charge le nouvel enregistrement dans les champs du recordset et DDX déplace les valeurs dans les contrôles du formulaire d'enregistrement.  Pour plus d'informations sur RFX, consultez [Record Field Exchange \(RFX\)](../data/odbc/record-field-exchange-rfx.md).  
  
> [!NOTE]
>  Veillez à utiliser ces ID de commandes standard pour tous les objets d'interface utilisateur associés aux commandes de navigation d'enregistrements standard.  
  
## Voir aussi  
 [Prise en charge de la navigation dans une vue de l'enregistrement](../data/supporting-navigation-in-a-record-view-mfc-data-access.md)