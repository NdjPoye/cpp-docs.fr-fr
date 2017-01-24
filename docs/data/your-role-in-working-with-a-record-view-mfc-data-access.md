---
title: "Votre r&#244;le dans l&#39;utilisation d&#39;une vue de l&#39;enregistrement (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "MFC, vues des enregistrements"
  - "vues des enregistrements, personnaliser le code par défaut"
ms.assetid: 691e89a5-ff21-4ca3-9278-69d4678288bb
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Votre r&#244;le dans l&#39;utilisation d&#39;une vue de l&#39;enregistrement (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant montre ce que vous devez généralement faire pour travailler avec une vue d'enregistrement et ce que l'infrastructure effectue pour vous.  
  
### Utilisation d'une vue d'enregistrement : l'infrastructure et vous  
  
|Vous|L'infrastructure|  
|----------|----------------------|  
|Utiliser l'éditeur de boîte de dialogue Visual C\+\+ pour concevoir le formulaire.|Crée une ressource de modèle de boîte de dialogue avec des contrôles.|  
|Utiliser l'[Assistant Application MFC](../mfc/reference/database-support-mfc-application-wizard.md) pour créer des classes dérivées de [CRecordView](../mfc/reference/crecordview-class.md) et [CRecordset](../mfc/reference/crecordset-class.md) ou de [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) et [CDaoRecordset](../mfc/reference/cdaorecordset-class.md).|Écrit les classes pour vous.|  
|Mapper les contrôles de vue d'enregistrement à des données membres de champ de recordset.|Fournit DDX entre les contrôles et les champs du recordset.|  
||Fournit des gestionnaires de commandes par défaut pour les commandes **Move First**, **Move Last**, **Move Next** et **Move Previous** à partir de menus ou de boutons de barre d'outils.|  
||Met à jour les modifications apportées à la source de données.|  
|\[Facultatif\] Écrire du code pour remplir les zones de liste ou zones de liste déroulante ou d'autres contrôles avec des données à partir d'un second recordset.||  
|\[Facultatif\] Écrire du code pour les validations spéciales.||  
|\[Facultatif\] Écrire du code pour ajouter ou supprimer des enregistrements.||  
  
 La programmation basée sur formulaire n'est qu'une approche parmi d'autres de l'utilisation d'une base de données.  Pour plus d'informations sur les applications utilisant une autre interface utilisateur, ou aucune interface utilisateur, consultez [MFC : utilisation de classes de bases de données avec des documents et des vues](../data/mfc-using-database-classes-with-documents-and-views.md) et [MFC : utilisation de classes de bases de données avec des documents et des vues](../data/mfc-using-database-classes-without-documents-and-views.md).  Pour découvrir d'autres approches de l'affichage des enregistrements de base de données, consultez les classes [CListView](../mfc/reference/clistview-class.md) et [CTreeView](../mfc/reference/ctreeview-class.md).  
  
## Voir aussi  
 [Vues d'enregistrements \(Accès aux données MFC\)](../data/record-views-mfc-data-access.md)   
 [Liste de pilotes ODBC](../data/odbc/odbc-driver-list.md)