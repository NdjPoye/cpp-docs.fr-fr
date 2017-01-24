---
title: "ODBC et les classes de base de donn&#233;es | Microsoft Docs"
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
  - "classes de base de données (C++), ODBC"
  - "MFC (C++), ODBC et"
  - "ODBC (fonctions API) (C++)"
  - "ODBC (classes) (C++), classes de base de données MFC"
ms.assetid: b166f82d-6f85-4556-aac8-fb851235d22c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ODBC et les classes de base de donn&#233;es
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les classes de base de données ODBC MFC encapsulent les appels de fonction API ODBC que vous effectueriez normalement vous\-même dans les fonctions membres des classes [CDatabase](../../mfc/reference/cdatabase-class.md) et [CRecordset](../../mfc/reference/crecordset-class.md).  Par exemple, les classes de base de données gèrent à votre place les séquences d'appel ODBC complexes, la liaison d'enregistrements retournés à des emplacements de stockage, le traitement des conditions d'erreur et d'autres opérations.  Par conséquent, vous utilisez une interface de classe beaucoup plus simple pour manipuler des enregistrements par le biais d'un objet Recordset.  
  
> [!NOTE]
>  Les sources de données ODBC sont accessibles via les classes ODBC MFC, comme le décrit cette RUBRIQUE, ou via les classes DAO \(Data Access Object\) MFC.  
  
 Bien que les classes de base de données encapsulent la fonctionnalité ODBC, elles ne fournissent pas un mappage un à un des fonctions API ODBC.  Les classes de base de données fournissent un plus haut niveau d'abstraction, basé sur les objets d'accès aux données de Microsoft Access et Microsoft Visual Basic.  Pour plus d'informations, consultez [Qu'est\-ce que le modèle de programmation de bases de données MFC ?](../../data/what-is-the-mfc-database-programming-model-q.md).  
  
## Voir aussi  
 [Éléments fondamentaux relatifs à ODBC](../../data/odbc/odbc-basics.md)