---
title: "Transactions (Acc&#232;s aux donn&#233;es MFC) | Microsoft Docs"
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
  - "bases de données (C++), transactions"
  - "transactions (C++)"
  - "transactions (C++), prise en charge de"
ms.assetid: f80afbfe-1517-4fec-8870-9ffc70a58b05
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Transactions (Acc&#232;s aux donn&#233;es MFC)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le concept de transaction a été développé pour gérer les cas dans lesquels l'état résultant de la base de données dépend du succès total d'une série d'opérations.  Cette situation peut survenir car des opérations successives peuvent modifier les résultats des opérations précédentes.  Dans ce cas, si l'une des opérations échoue, l'état résultant pourrait être indéterminé.  
  
 Pour résoudre ce problème, les transactions regroupent une série d'opérations pour que l'intégrité du résultat final puisse être assurée.  Soit toutes les opérations doivent réussir puis être validées \(écrites dans la base de données\), soit la transaction entière échoue.  L'annulation de la transaction est appelée « restauration ».  La restauration permet d'annuler les modifications et de rétablir la base de données à l'état précédant la transaction.  
  
 Par exemple, dans une transaction bancaire automatisée, si vous transférez une somme d'argent du compte A au compte B, la retrait de A et le crédit de B doivent tous deux réussir pour que les fonds soient traités correctement ou la transaction complète doit échouer.  
  
 Une transaction doit avoir des propriétés ACID, à savoir :  
  
-   **Atomicité** Une transaction est une unité de travail atomique qui s'exécute une seule fois ; le travail est effectué entièrement ou pas du tout.  
  
-   **Cohérence** Une transaction préserve la cohérence des données. Elle transforme un état cohérent des données en un autre état cohérent des données.  Les données liées par une transaction doivent être préservées sémantiquement.  
  
-   **Isolement** Une transaction est une unité d'isolement et chacune se produit séparément et indépendamment des transactions simultanées.  Une transaction ne doit jamais voir les phases intermédiaires d'une autre transaction.  
  
-   **Durabilité** Une transaction est une unité de récupération.  Si une transaction réussit, ses mises à jour persistent, même si le système tombe en panne ou est arrêté.  Si une transaction échoue, le système reste à l'état qui était le sien avant la validation de la transaction.  
  
 Vous pouvez prendre en charge les transactions dans OLE DB \(voir [Prise en charge des transactions dans OLE DB](../data/oledb/supporting-transactions-in-ole-db.md)\) ou ODBC \(voir [Transaction \(ODBC\)](../data/odbc/transaction-odbc.md)\).  
  
 Une transaction distribuée est une transaction qui met à jour des données distribuées, c'est\-à\-dire des données qui se trouvent sur plusieurs systèmes informatiques en réseau.  Si vous souhaitez prendre en charge les transactions sur un système distribué, vous devez utiliser Microsoft.NET Framework plutôt que la prise en charge des transactions OLE DB.  
  
## Voir aussi  
 [Programmation de l'accès aux données \(MFC\/ATL\)](../data/data-access-programming-mfc-atl.md)