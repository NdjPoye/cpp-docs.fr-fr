---
title: "Recordset&#160;: verrouillage d&#39;enregistrements (ODBC) | Microsoft Docs"
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
  - "données (C++), verrouiller"
  - "verrous (C++), recordsets"
  - "ODBC (recordsets C++), verrouiller des enregistrements"
  - "verrouillage optimiste"
  - "verrouillage optimiste, ODBC"
  - "verrouillage pessimiste dans ODBC"
  - "recordsets (C++), verrouiller des enregistrements"
ms.assetid: 8fe8fcfe-b55a-41a8-9136-94a7cd1e4806
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset&#160;: verrouillage d&#39;enregistrements (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Cette rubrique explique :  
  
-   [les différents modes de verrouillage disponibles](#_core_record.2d.locking_modes) ;  
  
-   [comment verrouiller les enregistrements du recordset lors de mises à jour](#_core_locking_records_in_your_recordset).  
  
 Lorsque vous utilisez un recordset pour modifier un enregistrement de la source de données, l'application peut verrouiller l'enregistrement afin qu'aucun autre utilisateur ne puisse le modifier en même temps.  Comme l'état d'un enregistrement modifié simultanément par deux utilisateurs est imprévisible, il importe que le système puisse garantir que deux utilisateurs ne peuvent pas modifier simultanément un même enregistrement.  
  
> [!NOTE]
>  Cette rubrique s'applique aux objets dérivés de `CRecordset` dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si vous avez implémenté l'extraction de lignes en bloc, certaines des informations ne s'appliquent pas.  Par exemple, vous ne pouvez pas appeler les fonctions membres **Edit** et **Update**.  Pour plus d'informations sur l'extraction de lignes en bloc, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_record.2d.locking_modes"></a> Types de verrouillage d'enregistrements  
 Les classes de base de données fournissent deux [types de verrouillages d'enregistrements](../Topic/CRecordset::SetLockingMode.md) :  
  
-   le verrouillage optimiste \(mode par défaut\) ;  
  
-   le verrouillage pessimiste.  
  
 La mise à jour d'un enregistrement se décompose en trois étapes :  
  
1.  Commencez par appeler la fonction membre [Edit](../Topic/CRecordset::Edit.md).  
  
2.  Modifiez les champs appropriés de l'enregistrement courant.  
  
3.  Terminez l'opération — et en principe validez la mise à jour — en appelant la fonction membre [Update](../Topic/CRecordset::Update.md).  
  
 Le verrouillage optimiste verrouille l'enregistrement de la source de données uniquement pendant l'appel de la fonction **Update**.  Si vous utilisez le verrouillage optimiste dans un environnement multi\-utilisateur, l'application doit gérer une condition d'échec de la fonction **Update**.  Le verrouillage pessimiste verrouille l'enregistrement dès que vous appelez **Edit** et ne le libère pas tant que vous n'avez pas appelé **Update** \(les échecs sont signalés via `CDBException`, et non par la valeur **FALSE** retournée par **Update**\).  Le verrouillage pessimiste pénalise potentiellement les performances des autres utilisateurs, car les accès simultanés au même enregistrement doivent attendre la fin complète du processus **Update** de votre application.  
  
##  <a name="_core_locking_records_in_your_recordset"></a> Verrouillage d'enregistrements du recordset  
 Si vous voulez modifier le [mode de verrouillage](#_core_record.2d.locking_modes) par défaut d'un objet recordset, vous devez le modifier avant d'appeler **Edit**.  
  
#### Pour modifier le mode de verrouillage actif d'un recordset  
  
1.  Appelez la fonction membre [SetLockingMode](../Topic/CRecordset::SetLockingMode.md), en spécifiant **CRecordset::pessimistic** ou **CRecordset::optimistic**.  
  
 Le nouveau mode de verrouillage demeure effectif tant que vous ne le modifiez pas à nouveau ou que le recordset n'est pas fermé.  
  
> [!NOTE]
>  Très peu de pilotes ODBC prennent actuellement en charge le verrouillage pessimiste.  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : création d'une jointure \(ODBC\)](../../data/odbc/recordset-performing-a-join-odbc.md)   
 [Recordset : ajout, modification et suppression d'enregistrements \(ODBC\)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md)