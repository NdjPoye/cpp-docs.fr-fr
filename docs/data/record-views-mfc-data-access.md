---
title: "Vues d&#39;enregistrements (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "DAO (C++), vues des enregistrements"
  - "bases de données (C++), vues des enregistrements"
  - "formulaires (C++), tâches d'accès aux données"
  - "MFC (C++), vues des enregistrements"
  - "ODBC (recordsets C++), vues des enregistrements"
  - "vues des enregistrements (C++)"
ms.assetid: 562122d9-01d8-4284-acf6-ea109ab0408d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Vues d&#39;enregistrements (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette section s'applique uniquement aux classes DAO et ODBC MFC.  Pour plus d'informations sur les vues d'enregistrements OLE DB, consultez [COleDBRecordView](../mfc/reference/coledbrecordview-class.md) et [Utilisation des vues de l'enregistrement OLE DB](../data/oledb/using-ole-db-record-views.md).  
  
 Pour prendre en charge les applications d'accès aux données basées sur formulaire, la bibliothèque de classes fournit les classes [CRecordView](../mfc/reference/crecordview-class.md) et [CDaoRecordView](../mfc/reference/cdaorecordview-class.md).  Une vue d'enregistrement est un objet de vue de formulaire dont les contrôles sont mappés directement aux données membres de champ d'un objet [recordset](../data/odbc/recordset-odbc.md) \(et indirectement aux colonnes correspondantes dans un résultat de requête ou une table sur la source de données\).  Comme leur classe de base [CFormView](../mfc/reference/cformview-class.md), `CRecordView` et `CDaoRecordView` sont basées sur une ressource de modèle de boîte de dialogue.  
  
## Utilisations des formulaires  
 Les formulaires sont utiles pour diverses tâches d'accès aux données :  
  
-   Saisie de données  
  
-   Exécution de l'analyse des données en lecture seule  
  
-   Mise à jour des données  
  
## Informations complémentaires sur les vues d'enregistrements  
 Le contenu de ces rubriques s'applique aux classes ODBC et DAO.  Utilisez `CRecordView` pour ODBC et `CDaoRecordView` pour DAO.  
  
 Les rubriques traitées ici sont les suivantes :  
  
-   [Fonctionnalités des classes d'affichage des enregistrements](../data/features-of-record-view-classes-mfc-data-access.md)  
  
-   [Échange de données pour les vues des enregistrements](../data/data-exchange-for-record-views-mfc-data-access.md)  
  
-   [Votre rôle dans l'utilisation d'une vue de l'enregistrement](../data/your-role-in-working-with-a-record-view-mfc-data-access.md)  
  
-   [Conception et création d'une vue de l'enregistrement](../data/designing-and-creating-a-record-view-mfc-data-access.md)  
  
-   [Utilisation d'une vue de l'enregistrement](../data/using-a-record-view-mfc-data-access.md)  
  
## Voir aussi  
 [Programmation de l'accès aux données \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)   
 [Liste de pilotes ODBC](../data/odbc/odbc-driver-list.md)