---
title: "Affichage et manipulation de donn&#233;es dans un formulaire | Microsoft Docs"
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
  - "données (MFC)"
  - "données (MFC), affichage dans un formulaire"
  - "afficher les données (C++), formulaires"
  - "formulaires (C++), afficher les données"
  - "ODBC (C++), formulaires"
  - "vues des enregistrements (C++), afficher les données"
ms.assetid: c56185c4-12cb-40b1-b499-02b29ea83e3a
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Affichage et manipulation de donn&#233;es dans un formulaire
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

De nombreuses applications d'accès aux données sélectionnent des données et les affichent dans des champs dans un formulaire.  La classe de base de données [CRecordView](../../mfc/reference/crecordview-class.md) vous offre un objet [CFormView](../../mfc/reference/cformview-class.md) directement connecté à un objet Recordset.  La vue de l'enregistrement utilise [DDX \(Dialog Data Exchange\)](../../mfc/dialog-data-exchange-and-validation.md) pour déplacer les valeurs des champs de l'enregistrement en cours du recordset vers les contrôles du formulaire et pour replacer les informations mises à jour dans le recordset.  À son tour, le recordset utilise RFX \(Record Field Exchange\) pour déplacer des données entre ses membres de données de champ et les colonnes correspondantes dans une table de la source de données.  
  
 Vous pouvez utiliser l'Assistant Création d'applications MFC ou **Ajout de classes** \(décrit dans [Ajout d'un consommateur ODBC MFC](../../mfc/reference/adding-an-mfc-odbc-consumer.md)\) pour créer conjointement la classe de vue et ses classes de recordset associées.  
  
 La vue de l'enregistrement et son recordset sont détruits lorsque vous fermez le document.  Pour plus d'informations sur les vues de l'enregistrement, consultez [Vues des enregistrements](../../data/record-views-mfc-data-access.md).  Pour plus d'informations sur RFX, consultez [Record Field Exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md).  
  
## Voir aussi  
 [ODBC et MFC](../../data/odbc/odbc-and-mfc.md)