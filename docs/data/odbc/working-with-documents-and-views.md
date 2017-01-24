---
title: "Utilisation des documents et vues | Microsoft Docs"
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
  - "documents (C++), MFC"
  - "MFC (C++), documents"
  - "MFC (C++), vues"
  - "vues (C++), MFC"
ms.assetid: 349b142d-1c5a-4b99-9de4-241e41d3d2f1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des documents et vues
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

De nombreuses fonctionnalités de la bibliothèque MFC \(Microsoft Foundation Classes\) reposent sur l'architecture document\/vue.  Généralement, un document enregistre vos données, et une vue affiche ces données dans une zone cliente d'une fenêtre frame et gère l'interaction de l'utilisateur avec ces données.  La vue communique avec le document pour obtenir et mettre à jour les données.  Vous pouvez utiliser les classes de base de données avec ou sans la structure.  
  
 Pour plus d'informations sur l'utilisation des classes de base de données dans la structure, consultez [MFC : utilisation de classes de bases de données avec des documents et des vues](../../data/mfc-using-database-classes-with-documents-and-views.md).  
  
 Par défaut, l'Assistant Création d'applications MFC crée une application squelette sans prendre en charge la base de données.  Vous pouvez toutefois sélectionner des options pour inclure une prise en charge minimale de la base de données ou une prise en charge plus complète basée sur un formulaire.  Pour plus d'informations sur les options des Assistants d'applications, consultez [Prise en charge des bases de données, Assistant Application MFC](../../mfc/reference/database-support-mfc-application-wizard.md).  
  
 Vous pouvez également utiliser les classes de base de données sans utiliser l'architecture complète document\/vue.  Pour plus d'informations, consultez [MFC : utilisation de classes de bases de données sans document ni vue](../../data/mfc-using-database-classes-without-documents-and-views.md).  
  
## Voir aussi  
 [ODBC et MFC](../../data/odbc/odbc-and-mfc.md)