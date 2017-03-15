---
title: "Fonctionnalit&#233;s des classes d&#39;affichage des enregistrements (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "enregistrements (classes d'affichage)"
  - "vues des enregistrements, classes"
ms.assetid: e7b2820f-09c4-483f-83c0-317e8be42bdf
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Fonctionnalit&#233;s des classes d&#39;affichage des enregistrements (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez effectuer une programmation d'accès aux données à base de formulaires avec la classe [CFormView](../mfc/reference/cformview-class.md), mais [CRecordView](../mfc/reference/crecordview-class.md) et [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) sont généralement mieux comme classes de dérivation.  Outre leurs fonctionnalités `CFormView` , `CRecordView` et `CDaoRecordView` :  
  
-   permettent l'échange DDX \(Dialog Data Exchange\) entre les contrôles du formulaire et l'objet recordset associé ;  
  
-   gèrent les commandes Move First, Move Next, Move Previous et Move Last pour la navigation parmi les enregistrements dans l'objet recordset associé ;  
  
-   mettent à jour les modifications apportées à l'enregistrement actif quand l'utilisateur passe à un autre enregistrement.  
  
 Pour plus d'informations sur la navigation, consultez [Vues d'enregistrements : prise en charge de la navigation dans une vue d'enregistrement](../data/supporting-navigation-in-a-record-view-mfc-data-access.md).  
  
## Voir aussi  
 [Vues d'enregistrements \(Accès aux données MFC\)](../data/record-views-mfc-data-access.md)   
 [Liste de pilotes ODBC](../data/odbc/odbc-driver-list.md)