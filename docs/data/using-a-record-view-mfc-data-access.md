---
title: "Utilisation d&#39;une vue de l&#39;enregistrement (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "vues des enregistrements, personnaliser le code par défaut"
ms.assetid: 91f2828f-0666-4273-ae28-e4703fd98521
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation d&#39;une vue de l&#39;enregistrement (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette rubrique explique comment personnaliser le code par défaut pour les vues d'enregistrements que l'Assistant écrit pour vous.  En général, vous souhaitez contraindre la sélection d'enregistrement avec un [filtre](../data/odbc/recordset-filtering-records-odbc.md) ou des [paramètres](../data/odbc/recordset-parameterizing-a-recordset-odbc.md), par exemple [trier](../data/odbc/recordset-sorting-records-odbc.md) les enregistrements, personnaliser l'instruction SQL.  
  
 Ces informations s'appliquent à [CRecordView](../mfc/reference/crecordview-class.md) \(ODBC\) et à [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) \(DAO\).  
  
 L'utilisation de `CRecordView` ou de `CDaoRecordView` est très similaire à l'utilisation de [CFormView](../mfc/reference/cformview-class.md).  L'approche de base consiste à utiliser la vue d'enregistrement pour afficher et éventuellement mettre à jour les enregistrements d'un seul recordset.  Vous souhaiterez peut\-être aussi utiliser d'autres recordsets, comme expliqué dans [Vues d'enregistrements : remplissage d'une zone de liste à partir d'un second recordset](../data/filling-a-list-box-from-a-second-recordset-mfc-data-access.md).  
  
## Voir aussi  
 [Vues d'enregistrements \(Accès aux données MFC\)](../data/record-views-mfc-data-access.md)   
 [Liste de pilotes ODBC](../data/odbc/odbc-driver-list.md)