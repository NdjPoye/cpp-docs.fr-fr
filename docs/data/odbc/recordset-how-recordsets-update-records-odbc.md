---
title: "Recordset&#160;: modification des enregistrements par les recordsets (ODBC) | Microsoft Docs"
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
  - "ODBC (recordsets), mettre à jour"
  - "enregistrements, mettre à jour"
  - "recordsets, modifier les enregistrements"
  - "recordsets, mettre à jour"
  - "mettre à jour des recordsets"
ms.assetid: 5ceecc06-7a86-43b1-93db-a54fb1e717c7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Recordset&#160;: modification des enregistrements par les recordsets (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 En dehors de leur capacité à sélectionner les enregistrements d'une source de données, les recordsets peuvent \(à titre facultatif\) mettre à jour ou supprimer les enregistrements sélectionnés ou ajouter de nouveaux enregistrements.  Trois facteurs déterminent le caractère modifiable d'un recordset : la possibilité de mettre à jour la source de données connectée, les options définies lors de la création de l'objet recordset et l'instruction SQL créée.  
  
> [!NOTE]
>  L'instruction SQL sur laquelle est fondé l'objet `CRecordset` peut influer sur le caractère modifiable du recordset.  Par exemple, si l'instruction SQL contient une jointure ou une clause **GROUP BY**, MFC définit le caractère modifiable avec la valeur **FALSE**.  
  
> [!NOTE]
>  Cette rubrique s'applique aux objets dérivés de `CRecordset` dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si vous utilisez l'extraction de lignes en bloc, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Cette rubrique explique :  
  
-   [votre propre rôle dans la mise à jour du recordset](#_core_your_role_in_recordset_updating) et ce que l'infrastructure effectue automatiquement ;  
  
-   [le recordset comme tampon d'édition](#_core_the_edit_buffer) et les [différences entre les feuilles de réponse dynamiques et les instantanés](#_core_dynasets_and_snapshots).  
  
 [Recordset : fonctionnement d'AddNew, Edit et Delete \(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md) décrit les actions de ces fonctions du point de vue du recordset.  
  
 [Recordset : informations complémentaires sur les mises à jour \(ODBC\)](../../data/odbc/recordset-more-about-updates-odbc.md) conclut la description de la mise à jour des recordsets en expliquant comment les transactions affectent les mises à jour, comment la fermeture d'un recordset influe sur les mises à jour en cours et comment vos propres mises à jour et celles des autres utilisateurs interagissent.  
  
##  <a name="_core_your_role_in_recordset_updating"></a> Votre rôle dans la mise à jour du recordset  
 Le tableau suivant illustre votre rôle dans l'utilisation des recordsets pour ajouter, modifier ou supprimer des enregistrements, ainsi que les tâches accomplies automatiquement par l'infrastructure.  
  
### Mise à jour du recordset : responsabilités respectives  
  
|Vous|L'infrastructure|  
|----------|----------------------|  
|Déterminez si la source de données peut être modifiée \(ou faire l'objet d'ajouts\).|Fournit les fonctions membres [CDatabase](../../mfc/reference/cdatabase-class.md) pour tester le caractère modifiable ou extensible de la source de données.|  
|Ouvrez un recordset modifiable \(type indifférent\).||  
|Déterminez si le recordset est modifiable en appelant les fonctions de mise à jour de `CRecordset` comme `CanUpdate` ou `CanAppend`.||  
|Appelez les fonctions membres du recordset pour ajouter, modifier ou supprimer des enregistrements.|Gère les mécanismes d'échanges de données entre l'objet recordset et la source de données.|  
|Le cas échéant, utilisez des transactions pour contrôler le processus de mise à jour.|Fournit les fonctions membres de `CDatabase` pour prendre en charge les transactions.|  
  
 Pour plus d'informations sur les transactions, consultez [Transaction \(ODBC\)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="_core_the_edit_buffer"></a> Tampon d'édition  
 Pris collectivement, les membres de données de type champ d'un recordset font office de tampon d'édition, ne contenant qu'un seul enregistrement : l'enregistrement courant.  Les opérations de mise à jour utilisent ce tampon pour travailler sur l'enregistrement courant.  
  
-   Lorsque vous ajoutez un enregistrement, le tampon d'édition est utilisé pour construire un nouvel enregistrement.  Lorsque vous avez fini d'ajouter l'enregistrement, l'enregistrement courant précédent redevient l'enregistrement courant.  
  
-   Lorsque vous mettez à jour \(modifiez\) un enregistrement, le tampon d'édition est utilisé pour affecter les nouvelles valeurs aux membres de données de type champ de recordset.  Lorsque la mise à jour est terminée, l'enregistrement modifié demeure l'enregistrement courant.  
  
 Lorsque vous appelez [AddNew](../Topic/CRecordset::AddNew.md) ou [Edit](../Topic/CRecordset::Edit.md), l'enregistrement courant est stocké de façon à pouvoir être restauré comme nécessaire.  Lorsque vous appelez [Delete](../Topic/CRecordset::Delete.md), l'enregistrement courant n'est pas stocké mais marqué comme étant supprimé, et vous devez accéder à un autre enregistrement.  
  
> [!NOTE]
>  Le tampon d'édition ne joue aucun rôle dans la suppression d'enregistrements.  Lorsque vous supprimez l'enregistrement courant, l'enregistrement est marqué comme supprimé, et le recordset ne se trouve sur aucun enregistrement tant que vous n'avez pas accédé à un nouvel enregistrement.  
  
##  <a name="_core_dynasets_and_snapshots"></a> Feuilles de réponses dynamiques et instantanés  
 Les [feuilles de réponse dynamiques](../../data/odbc/dynaset.md) actualisent le contenu d'un enregistrement tandis que vous accédez à l'enregistrement.  Les [instantanés](../../data/odbc/snapshot.md) sont des représentations statiques des enregistrements, si bien que le contenu d'un enregistrement n'est pas actualisé tant que vous n'appelez pas [Requery](../Topic/CRecordset::Requery.md).  Pour utiliser toute la fonctionnalité des feuilles de réponse dynamiques, vous devez disposer d'un pilote ODBC qui soit conforme au niveau correct de prise en charge API ODBC.  Pour plus d'informations, consultez [ODBC](../../data/odbc/odbc-basics.md) et [Feuille de réponse dynamique](../../data/odbc/dynaset.md).  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : fonctionnement d'AddNew, Edit et Delete \(ODBC\)](../../data/odbc/recordset-how-addnew-edit-and-delete-work-odbc.md)