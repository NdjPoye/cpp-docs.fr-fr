---
title: "Classes DAO | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
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
  - "DAO (C++), classes"
  - "classes de base de données (C++), DAO"
ms.assetid: b15d0cd6-328b-4288-9c19-d037a795db57
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Classes DAO
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces classes fonctionnent avec les autres classes d'infrastructure d'application pour permettre un accès aisé aux bases de données d'accès aux données \(DAO\), qui utilisent le même moteur de base de données que Microsoft Visual Basic.NET et Microsoft Access.  Les classes de DAO peuvent également accéder à une grande variété de bases de données pour lesquelles les pilotes ODBC \(Open Database Connectivity\) sont disponibles.  
  
 Les programmes qui utilisent les bases de données DAO ont au moins un objet `CDaoDatabase` et un objet `CDaoRecordset`.  
  
> [!NOTE]
>  Dans Visual C\+\+ .NET, les Assistants et l'environnement Visual C\+\+ ne prennent plus en charge DAO \(même si les classes DAO sont incluses et que vous pouvez toujours les utiliser\).  Microsoft recommande l'utilisation d'ODBC pour des nouveaux projets de MFC.  Vous ne devez utiliser DAO que dans les applications existantes.  
  
 [CDaoWorkspace](../mfc/reference/cdaoworkspace-class.md)  
 Gère une session de base de données nommée et protégée par mot de passe, de la connexion à la déconnexion.  La plupart des programmes utilisent l'espace de travail par défaut.  
  
 [CDaoDatabase](../mfc/reference/cdaodatabase-class.md)  
 Une connexion à une base de données, par l'intermédiaire de laquelle vous pouvez utiliser les données.  
  
 [CDaoRecordset](../mfc/reference/cdaorecordset-class.md)  
 Représente un ensemble d'enregistrements sélectionnés à partir d'une source de données.  
  
 [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)  
 Vue qui affiche des enregistrements de base de données dans des contrôles.  
  
 [CDaoQueryDef](../mfc/reference/cdaoquerydef-class.md)  
 Représente une définition de requête, généralement stockée dans une base de données.  
  
 [CDaoTableDef](../mfc/reference/cdaotabledef-class.md)  
 Représente la définition stockée d'une table de base ou d'une table attachée.  
  
 [CDaoException](../mfc/reference/cdaoexception-class.md)  
 Représente une condition d'exception résultant des classes de DAO.  
  
 [CDaoFieldExchange](../mfc/reference/cdaofieldexchange-class.md)  
 Prend en charge les routines d'échange de champs d'enregistrements DAO \(DFX\) utilisées par les classes de base de données DAO.  Vous n'utiliserez généralement pas directement cette classe.  
  
## Classes liées  
 [CLongBinary](../mfc/reference/clongbinary-class.md)  
 Encapsule un descripteur de stockage pour un objet BLOB, tel qu'une bitmap.  Les objets `CLongBinary` sont utilisés pour gérer les données LOB de données stockés dans les tables de base de données.  
  
 [COleCurrency](../mfc/reference/colecurrency-class.md)  
 Wrapper pour le type OLE **DEVISE**, un type OLE automation d'arithmétique à virgule fixe, avec 15 chiffres placés avant la virgule et 4 chiffres après.  
  
 [COleDateTime](../atl-mfc-shared/reference/coledatetime-class.md)  
 Wrapper pour le type **DATE**OLE automation.  Représente les valeurs de date et d'heure.  
  
 [COleVariant](../mfc/reference/colevariant-class.md)  
 Wrapper pour le type **VARIANT**OLE automation.  Les données dans **VARIANT**s peuvent être stockées dans plusieurs formats.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)