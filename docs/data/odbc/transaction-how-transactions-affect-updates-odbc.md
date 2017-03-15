---
title: "Transaction&#160;: r&#233;percussions des transactions sur les mises &#224; jour (ODBC) | Microsoft Docs"
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
  - "CommitTrans (méthode)"
  - "ODBC (recordsets), transactions"
  - "Rollback (méthode), transactions ODBC"
  - "transactions, restaurer"
  - "transactions, mettre à jour des recordsets"
ms.assetid: 9e00bbf4-e9fb-4332-87fc-ec8ac61b3f68
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Transaction&#160;: r&#233;percussions des transactions sur les mises &#224; jour (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Les mises à jour de la [source de données](../../data/odbc/data-source-odbc.md) sont managées pendant les transactions grâce à l'utilisation d'une mémoire tampon de modification ; la même méthode est d'ailleurs utilisée en dehors des transactions.  Les données membres de champs d'un recordset jouent collectivement le rôle d'une mémoire tampon de modification qui contient l'enregistrement en cours, ce dernier étant sauvegardé temporairement par le recordset pendant un `AddNew` ou **Edit**.  Pendant une opération **Delete**, l'enregistrement en cours n'est pas sauvegardé dans une transaction.  Pour plus d'informations sur la mémoire tampon de modification et la façon dont les mises à jour sauvegardent l'enregistrement en cours, consultez [Recordset : modification des enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
> [!NOTE]
>  Si vous avez implémenté l'extraction de lignes en bloc, vous ne pouvez pas appeler `AddNew`, **Edit** ou **Delete**.  Vous devez donc écrire vos propres fonctions pour effectuer des mises à jour de la source de données.  Pour plus d'informations sur l'extraction de lignes en bloc, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Pendant les transactions, les opérations `AddNew`, **Edit** et **Delete** peuvent être validées ou annulées.  **CommitTrans** et **Rollback** peuvent entraîner l'échec de la restauration de l'enregistrement en cours dans la mémoire tampon de modification.  Pour assurer la restauration correcte de l'enregistrement en cours, il est important de bien comprendre comment les fonctions membres **CommitTrans** et **Rollback** de `CDatabase` fonctionnent avec les fonctions de mise à jour de `CRecordset`.  
  
##  <a name="_core_how_committrans_affects_updates"></a> Répercussions de CommitTrans sur les mises à jour  
 Le tableau ci\-dessous explique les effets de **CommitTrans** sur les transactions.  
  
### Répercussions de CommitTrans sur les mises à jour  
  
|Opération|État de la source de données|  
|---------------|----------------------------------|  
|`AddNew` et **Update**, puis **CommitTrans**|Ajout d'un nouvel enregistrement à la source de données.|  
|`AddNew` \(sans **Update**\), puis **CommitTrans**|Perte du nouvel enregistrement.  L'enregistrement n'est pas ajouté à la source de données.|  
|**Edit** et **Update**, puis **CommitTrans**|Validation des modifications dans la source de données.|  
|**Edit** \(sans **Update**\), puis **CommitTrans**|Perte des modifications de l'enregistrement.  L'enregistrement reste identique dans la source de données.|  
|**Delete**, puis **CommitTrans**|Suppression des enregistrements de la source de données.|  
  
##  <a name="_core_how_rollback_affects_updates"></a> Répercussions de Rollback sur les transactions  
 Le tableau ci\-dessous explique les effets de **Rollback** sur les transactions.  
  
### Répercussions de Rollback sur les transactions  
  
|Opération|État de l'enregistrement en cours|Vous devez également|État de la source de données|  
|---------------|---------------------------------------|--------------------------|----------------------------------|  
|`AddNew` et **Update**, puis **Rollback**|Le contenu de l'enregistrement en cours est temporairement stocké pour libérer de l'espace pour les nouveaux enregistrements.  Le nouvel enregistrement est entré dans la mémoire tampon de modification.  Après appel de **Update**, l'enregistrement en cours est rétabli dans la mémoire tampon de modification.||L'ajout à la source de données effectué par **Update** est annulé.|  
|`AddNew` \(sans **Update**\), puis **Rollback**|Le contenu de l'enregistrement en cours est temporairement stocké pour libérer de l'espace pour les nouveaux enregistrements.  La mémoire tampon de modification contient le nouvel enregistrement.|Appeler une nouvelle fois `AddNew` pour rétablir la mémoire tampon de modification pour un nouvel enregistrement vide.  Autre solution : appeler **Move**\(0\) pour rétablir les anciennes valeurs dans la mémoire tampon de modification.|Comme **Update** n'a pas été appelé, aucune modification n'a été apportée à la source de données.|  
|**Edit** et **Update**, puis **Rollback**|Une version non modifiée de l'enregistrement en cours est temporairement stockée.  Des modifications sont apportées au contenu de la mémoire tampon de modification.  Après l'appel de **Update**, la version non modifiée de l'enregistrement est toujours temporairement stockée.|*Dynaset* : Vous éloigner de l'enregistrement en cours, puis y revenir pour rétablir la version non modifiée de l'enregistrement dans la mémoire tampon de modification.<br /><br /> *Snapshot* : Appeler **Requery** pour actualiser le recordset à partir de la source de données.|Les modifications apportées par **Update** à la source de données sont annulées.|  
|**Edit** \(sans **Update**\), puis **Rollback**|Une version non modifiée de l'enregistrement en cours est temporairement stockée.  Des modifications sont apportées au contenu de la mémoire tampon de modification.|Appeler une nouvelle fois **Edit** pour rétablir la version non modifiée de l'enregistrement dans la mémoire tampon de modification.|Comme **Update** n'a pas été appelé, aucune modification n'a été apportée à la source de données.|  
|**Delete**, puis **Rollback**|Le contenu de l'enregistrement en cours est supprimé.|Appeler **Requery** pour rétablir le contenu de l'enregistrement en cours à partir de la source de données.|La suppression des données de la source de données est annulée.|  
  
## Voir aussi  
 [Transaction \(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [Transaction \(ODBC\)](../../data/odbc/transaction-odbc.md)   
 [Transaction : exécution d'une transaction dans un recordset \(ODBC\)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordset Class](../../mfc/reference/crecordset-class.md)