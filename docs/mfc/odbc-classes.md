---
title: "Classes ODBC | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.data"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de base de données (C++), ODBC"
  - "ODBC (classes) (C++)"
ms.assetid: 6c40fca8-3033-4873-9abe-7f51725de0e0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Classes ODBC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces classes fonctionnent avec les autres classes d'infrastructure d'application pour permettre à un accès aisé à une grande variété de bases de données dont les pilotes ODBC \(Open Database Connectivity\) sont disponibles.  
  
 Les programmes qui utilisent les bases de données ODBC ont au moins un objet `CDatabase` et un objet `CRecordset`.  
  
 [CDatabase](../mfc/reference/cdatabase-class.md)  
 Encapsule une connexion à une source de données, par l'intermédiaire de laquelle vous pouvez utiliser la source de données.  
  
 [CRecordset](../mfc/reference/crecordset-class.md)  
 Encapsule un ensemble d'enregistrements sélectionnés à partir d'une source de données.  Les jeux permettent le défilement d'enregistrements sur l'enregistrement, la mise à jour des enregistrements \(ajouter, modifier, et supprimer des enregistrements\), qualifiant la sélection d'un filtre, de tri la sélection, puis paramétrant la sélection avec les informations obtenues via ou calculées au moment de l'exécution.  
  
 [CRecordView](../mfc/reference/crecordview-class.md)  
 Fournit un mode formulaire directement connectée à un objet recordset.  L'échange de données de dialogue \(DDX\) de l'infrastructure échange les données entre le recordset et les commandes de la vue de l'enregistrement.  Comme tous les modes formulaire, une vue de l'enregistrement est basée sur une ressource modèle de la boîte de dialogue.  Les vues des enregistrements prennent en charge également déplacer des enregistrements sur l'enregistrement dans l'ensemble d'enregistrements, mettre à jour des enregistrements, et fermer le jeu d'associé à la vue de l'enregistrement se ferme.  
  
 [CDBException](../mfc/reference/cdbexception-class.md)  
 Une exception résultant des échecs de traitement d'accès aux données.  Cette classe sert le même objectif d'autres classes d'exception dans le mécanisme de gestion des exceptions de la bibliothèque de classes.  
  
 [CFieldExchange](../mfc/reference/cfieldexchange-class.md)  
 Les informations de contexte de la prise en compte pour prendre en charge l'échange des champs de journalisation \(RFX\), qui données d'échanges entre les données de membre de champ et les membres de données de type paramètre d'un objet recordset et les colonnes de table correspondantes dans la source de données.  Analogue pour classer [CDataExchange](../mfc/reference/cdataexchange-class.md), utilisé même pour l'échange de données de boîtes de dialogue \(DDX\).  
  
## Classes liées  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 Encapsule un descripteur de stockage pour un objet BLOB, tel qu'une bitmap.  Les objets `CLongBinary` sont utilisés pour gérer les données LOB de données stockés dans les tables de base de données.  
  
 [CDBVariant](../mfc/reference/cdbvariant-class.md)  
 Permet d'enregistrer une valeur sans vous préoccuper du type de données de la valeur.  `CDBVariant` suit le type de données de la valeur actuelle, qui est stockée dans une union.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)