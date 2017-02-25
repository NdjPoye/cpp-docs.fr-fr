---
title: "&#201;change de donn&#233;es pour les affichages des enregistrements (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "DDX (échange de données de boîtes de dialogue), vues des enregistrements"
  - "processus DFX (DAO record field exchange)"
  - "processus DFX (DAO record field exchange), mécanisme d'échange de données"
  - "processus DFX (DAO record field exchange), vues des enregistrements"
  - "vues des enregistrements, échange de données"
  - "RFX (Record Field Exchange)"
  - "RFX (Record Field Exchange), mécanisme d'échange de données"
  - "RFX (Record Field Exchange), vues des enregistrements"
ms.assetid: abc52ca7-6997-47a7-98f3-f347f52b1f72
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# &#201;change de donn&#233;es pour les affichages des enregistrements (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Quand vous utilisez [Ajouter une classe](../mfc/reference/adding-an-mfc-odbc-consumer.md) pour mapper les contrôles d'une ressource de modèle de boîte de dialogue d'une vue d'enregistrement aux champs d'un recordset, l'infrastructure gère l'échange de données dans les deux sens : du recordset vers les contrôles et des contrôles vers le recordset.  L'utilisation du mécanisme DDX signifie que vous n'êtes pas obligé d'écrire le code pour transférer les données d'une extrémité à une autre.  
  
 Le mécanisme DDX des vues d'enregistrements fonctionne en combinaison avec :  
  
-   [RFX](../data/odbc/record-field-exchange-rfx.md) pour les recordsets de la classe `CRecordset` \(ODBC\).  
  
-   DFX pour les recordsets de la classe `CDaoRecordset` \(DAO\).  
  
 Bien que leur implémentation diffère, au niveau de l'interface RFX et DFX sont des mécanismes d'échange de données très similaires.  La version DAO, DFX, s'inspire très largement de l'ancienne version ODBC, RFX.  Si vous savez comment utiliser RFX, vous savez comment utiliser DFX.  
  
 RFX et DFX déplacent les données entre l'enregistrement actif de la source de données et les données membres de champ d'un objet recordset.  DDX déplace les données à partir des données membres de champ vers les contrôles dans le formulaire.  Cette combinaison remplit les contrôles du formulaire initialement et à mesure que l'utilisateur passe d'un enregistrement à un autre.  Elle peut également retransférer les données mises à jour vers le recordset, puis vers la source de données.  
  
 La figure suivante montre la relation entre DDX et RFX \(ou DFX\) pour les vues d'enregistrements.  
  
 ![Mécanismes DDX et RFX](../data/media/vc37xt1.png "vc37XT1")  
Échange de données de boîtes de dialogue et de champs d'enregistrements  
  
 Pour plus d'informations sur DDX, consultez [Échange et validation de données de boîtes de dialogue](../mfc/dialog-data-exchange-and-validation.md).  Pour plus d'informations sur RFX, consultez [Record Field Exchange \(RFX\)](../data/odbc/record-field-exchange-rfx.md).  
  
## Voir aussi  
 [Vues d'enregistrements \(Accès aux données MFC\)](../data/record-views-mfc-data-access.md)   
 [Liste de pilotes ODBC](../data/odbc/odbc-driver-list.md)