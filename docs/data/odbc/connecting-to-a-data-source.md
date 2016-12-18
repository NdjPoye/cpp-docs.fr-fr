---
title: "Connexion &#224; une source de donn&#233;es | Microsoft Docs"
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
  - "connexions (C++), source de données"
  - "sources de données (C++), connecter à"
  - "connexions de base de données (C++), classes ODBC MFC"
  - "connexions de base de données (C++), ODBC"
  - "bases de données (C++), connecter à"
  - "ODBC (connexions) (C++), utilisation"
  - "ODBC (sources de données) (C++), connexions"
ms.assetid: ef6c8c98-5979-43a8-9fb5-5bb06fc59f36
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Connexion &#224; une source de donn&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une source de données ODBC représente un ensemble spécifique de données, les informations nécessaires pour y accéder et l'emplacement de la source de données, pouvant être décrite par un nom de source de données.  D'un point de vue de votre programme, la source de données comprend les données, le système de gestion de base de données, le réseau \(le cas échéant\) et ODBC.  
  
 Pour accéder aux données fournies par une source de données, votre programme doit d'abord établir une connexion à la source de données.  Tous les accès aux données sont gérés par le biais de cette connexion.  
  
 Les connexions de source de données sont encapsulées par la classe [CDatabase](../../mfc/reference/cdatabase-class.md).  Dès qu'un objet `CDatabase` est connecté à une source de données, vous pouvez :  
  
-   construire des [recordsets](../../mfc/reference/crecordset-class.md), qui sélectionnent des enregistrements à partir de tables ou de requêtes ;  
  
-   gérer des [transactions](../../data/odbc/transaction-odbc.md), qui regroupent les mises à jour pour qu'elles soient toutes validées en une seule fois auprès de la source de données \(ou la transaction complète est restaurée pour que la source de données demeure inchangée\) si la source de données prend en charge le niveau requis de transactions ;  
  
-   Exécutez directement les instructions d'[SQL](../../data/odbc/sql.md).  
  
 Lorsque vous avez terminé d'utiliser une connexion à une source de données, fermez l'objet `CDatabase` et détruisez\-le ou réutilisez\-le pour une nouvelle connexion.  Pour plus d'informations sur les connexions aux sources de données, consultez [Source de données \(ODBC\)](../../data/odbc/data-source-odbc.md).  
  
## Voir aussi  
 [ODBC et MFC](../../data/odbc/odbc-and-mfc.md)