---
title: "Acc&#232;s aux donn&#233;es&#160;: ADO et RDO | Microsoft Docs"
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
  - "contrôles dépendants (C++), ADO"
  - "contrôles dépendants (C++), RDO"
  - "contrôles (C++), liaison de données"
  - "accès aux données (C++), contrôles de données RDO"
  - "liaison de données (C++), ADO"
  - "liaison de données (C++), RDO"
  - "contrôles de données (C++)"
  - "contrôles liés aux données (C++), ADO"
  - "contrôles liés aux données (C++), RDO"
ms.assetid: 92da8f1e-144b-4605-ac0a-43c25bdc14a7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Acc&#232;s aux donn&#233;es&#160;: ADO et RDO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant montre deux technologies sous\-jacentes qui prennent en charge les contrôles de sources de données ou les contrôles liés aux données.  
  
 **ADO**  
 ADO est un wrapper COM d'OLE DB qui facilite l'écriture d'applications d'accès aux données \(consommateurs\).  OLE DB est une technologie d'accès aux données universelles de type COM ; elle permet d'utiliser n'importe quelle source de données et pas seulement les méthodes d'accès séquentiel indexé \(ISAM\) et les bases de données SQL.  
  
 Les fournisseurs OLE DB peuvent accéder aux données à partir d'une riche panoplie de sources de données et ne sont pas limités aux requêtes SQL pour récupérer des données mais peuvent aussi utiliser les requêtes définies dans le fournisseur.  
  
 **RDO**  
 RDO est le wrapper COM d'ODBC.  ODBC, une API basée sur le langage C, permet un accès aux données universel \(hétérogène\).  Cependant, RDO fait appel à SQL en tant que langage de commandes pour l'accès aux données.  
  
 Il convient donc d'opter pour les contrôles d'accès aux données de type ADO de préférence aux contrôles d'accès aux données RDO.  
  
 Le tableau suivant montre les principales différences entre les contrôles de données ADO et RDO.  
  
 **Contrôles liés aux données**  
 Les contrôles RDO liés aux données utilisent les interfaces **ICursor** ; les contrôles ADO utilisent l'interface `IRowset` OLE DB.  Dans les deux cas, les interfaces utilisées par les contrôles retournent un jeu de lignes.  
  
 Les contrôles liés aux données RDO ont été conçus pour fonctionner de façon optimale avec Visual Basic.  Certaines fonctionnalités des contrôles liés aux données RDO, notamment dans le domaine de la mise en forme, ne sont pas disponibles dans les applications Visual C\+\+.  Ce problème ne se retrouve pas dans les contrôles de liaison de données ADO.  
  
 **Contrôles de données**  
 Les contrôles de données ADO implémentent l'interface **IDataSource** alors que les contrôles de données RDO implémentent l'interface **IVBDSC**.  Vous pouvez donc appeler une méthode **IDataSource** pour recevoir un pointeur d'interface `IRowset`.  Vous pouvez également appeler une méthode IVBDSC pour recevoir un pointeur d'interface **ICursor**.  
  
## Voir aussi  
 [Liaison de données avec des contrôles ActiveX dans Visual C\+\+](../../data/ado-rdo/databinding-with-activex-controls-in-visual-cpp.md)