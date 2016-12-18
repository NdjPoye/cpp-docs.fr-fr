---
title: "Fournisseurs et consommateurs OLE&#160;DB | Microsoft Docs"
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
  - "consommateurs OLE DB"
  - "consommateurs OLE DB, architecture de données OLE DB"
  - "fournisseurs OLE DB"
  - "fournisseurs OLE DB, architecture de données OLE DB"
  - "OLE DB, modèle de données"
ms.assetid: 886cb39d-652b-4557-93f0-4b1b0754d8bc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Fournisseurs et consommateurs OLE&#160;DB
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'architecture OLE DB utilise le modèle du consommateur et du fournisseur.  Un consommateur formule des demandes de données.  Le fournisseur répond à ces demandes en donnant une forme tabulaire aux données avant de les retourner au consommateur.  Tout appel pouvant émaner du consommateur doit être implémenté dans le fournisseur.  
  
 Sur un plan technique, un consommateur représente tout système ou code d'application code \(pas nécessairement un composant OLE DB\) qui accède aux données par l'intermédiaire d'interfaces OLE DB.  Les interfaces sont implémentées dans un fournisseur.  Ainsi, un fournisseur correspond à tout composant logiciel implémentant des interfaces OLE DB pour encapsuler l'accès aux données et exposer celles\-ci à d'autres objets \(c'est\-à\-dire les consommateurs\).  
  
 En termes de rôles, donc, un consommateur appelle les méthodes sur des interfaces OLE DB ; un fournisseur OLE DB implémente les interfaces OLE DB requises.  
  
 OLE DB évite les termes « client » et « serveur » car ces rôles ne sont pas toujours significatifs, notamment dans une situation multicouche.  Un consommateur peut être un composant sur une couche qui prend en charge un autre composant ; parler alors de composant client risque de prêter à confusion.  Un fournisseur se comporte également davantage en tant que pilote de base de données que comme un serveur.  
  
## Voir aussi  
 [Programmation OLE DB](../../data/oledb/ole-db-programming.md)   
 [Vue d'ensemble de la programmation OLE DB](../../data/oledb/ole-db-programming-overview.md)