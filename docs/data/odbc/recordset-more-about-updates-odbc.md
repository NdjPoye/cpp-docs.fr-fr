---
title: "Recordset&#160;: informations compl&#233;mentaires sur les mises &#224; jour (ODBC) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "environnements multi-utilisateurs, mises à jour des recordsets"
  - "ODBC (recordsets), mettre à jour"
  - "enregistrements, mettre à jour"
  - "recordsets, mettre à jour"
  - "défilement, mises à jour des recordsets"
  - "transactions, mettre à jour des recordsets"
  - "mettre à jour des recordsets"
ms.assetid: 0353a742-d226-4fe2-8881-a7daeffe86cd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Recordset&#160;: informations compl&#233;mentaires sur les mises &#224; jour (ODBC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette rubrique s'applique aux classes ODBC MFC.  
  
 Cette rubrique explique :  
  
-   [l'influence des autres opérations, comme les transactions, sur les mises à jour](#_core_how_transactions_affect_updates) ;  
  
-   [vos propres mises à jour et celles des autres utilisateurs](#_core_your_updates_and_the_updates_of_other_users) ;  
  
-   [des informations complémentaires sur les fonctions membres Update et Delete](#_core_more_about_update_and_delete).  
  
> [!NOTE]
>  Cette rubrique s'applique aux objets dérivés de `CRecordset` dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si vous avez implémenté l'extraction de lignes en bloc, certaines des informations ne s'appliquent pas.  Par exemple, vous ne pouvez pas appeler les fonctions membres `AddNew`, **Edit**, **Delete** et **Update** ; cependant, il est possible d'effectuer des transactions.  Pour plus d'informations sur l'extraction de lignes en bloc, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_how_other_operations_affect_updates"></a> Influence des autres opérations sur les mises à jour  
 Vos mises à jour sont affectées par les transactions au moment de la mise à jour, lorsque vous fermez le recordset ou vous déplacez par défilement avant de terminer une transaction.  
  
###  <a name="_core_how_transactions_affect_updates"></a> Influence des transactions sur les mises à jour  
 En plus de la compréhension du fonctionnement de `AddNew`, **Edit** et **Delete**, il importe de maîtriser comment les fonctions membres **BeginTrans**, **CommitTrans** et **Rollback** de [CDatabase](../../mfc/reference/cdatabase-class.md) coopèrent avec les fonctions de mise à jour de [CRecordset](../../mfc/reference/crecordset-class.md).  
  
 Par défaut, les appels de `AddNew` et **Edit** affectent immédiatement la source de données lorsque vous appelez **Update**.  Les appels de **Delete** prennent effet immédiatement.  Mais vous pouvez créer une transaction et exécuter ces appels sous forme de lot.  Les mises à jour ne sont pas définitives tant que vous ne les avez pas validées.  Si vous changez d'avis, vous pouvez annuler la transaction au lieu de la valider.  
  
 Pour plus d'informations sur les transactions, consultez [Transaction \(ODBC\)](../../data/odbc/transaction-odbc.md).  
  
###  <a name="_core_how_closing_the_recordset_affects_updates"></a> Influence de la fermeture du recordset sur les mises à jour  
 Si vous fermez un recordset ou son objet associé `CDatabase`, avec une transaction en cours \([CDatabase::CommitTrans](../Topic/CDatabase::CommitTrans.md) ou [CDatabase::Rollback](../Topic/CDatabase::Rollback.md) n'ont pas été appelées\), la transaction est annulée automatiquement \(à moins que la base de données principale ne soit le moteur de base de données Microsoft Jet\).  
  
> [!CAUTION]
>  Si vous utilisez le moteur de base de données Microsoft Jet, la fermeture d'un recordset à l'intérieur d'une transaction explicite n'entraîne pas la libération des lignes modifiées ou des verrous placés tant que la transaction explicite n'a pas été validée ou annulée.  Il est recommandé que vous ouvriez et fermiez les recordsets à l'intérieur ou à l'extérieur d'une transaction Jet explicite.  
  
###  <a name="_core_how_scrolling_affects_updates"></a> Influence du défilement sur les mises à jour  
 Lorsque vous [Recordset : défilement \(ODBC\)](../../data/odbc/recordset-scrolling-odbc.md) un recordset, le tampon d'édition est rempli à l'aide de chaque nouvel enregistrement courant \(l'enregistrement précédent n'est pas stocké d'abord\).  Le défilement ignore les enregistrements préalablement supprimés.  Si vous vous déplacez par défilement après avoir appelé `AddNew` ou **Edit** sans avoir appelé **Update**, **CommitTrans** ou **Rollback**, toutes les modifications sont perdues \(sans que vous en soyez averti\) lorsqu'un nouvel enregistrement est placé dans le tampon d'édition.  Le tampon d'édition est rempli par l'enregistrement auquel vous avez accédé par défilement, l'enregistrement stocké est libéré et aucune modification n'est effectuée sur la source de données.  Cela s'applique à la fois à `AddNew` et **Edit**.  
  
##  <a name="_core_your_updates_and_the_updates_of_other_users"></a> Vos propres mises à jour et celles des autres utilisateurs  
 Lorsque vous utilisez un recordset pour modifier les données, vos mises à jour affectent les autres utilisateurs.  De même, les mises à jour des autres utilisateurs pendant la durée de vie de votre recordset influent sur les vôtres.  
  
 Dans un environnement multi\-utilisateur, les autres utilisateurs peuvent ouvrir des recordsets qui contiennent certains enregistrements identiques à ceux qui sont sélectionnés dans votre recordset.  Les modifications apportées à un enregistrement avant que vous ne le récupériez sont répercutées dans le recordset.  Comme les feuilles de réponse dynamiques récupèrent un enregistrement chaque fois que vous y accédez par défilement, elles répercutent les modifications chaque fois que vous accédez par défilement à un enregistrement.  Comme les instantanés récupèrent un enregistrement lorsque vous y accédez par défilement la première fois, ils ne répercutent que les modifications intervenues avant que vous n'accédiez à l'enregistrement.  
  
 Les enregistrements ajoutés par d'autres utilisateurs après que vous avez ouvert le recordset n'apparaissent pas dans le recordset tant que vous ne lancez pas une nouvelle requête.  Si le recordset est une feuille de réponse dynamique, les modifications d'enregistrements existants apparaissent effectivement dans la feuille de réponse dynamique lorsque vous accédez par défilement à l'enregistrement concerné.  Si le recordset est un instantané, les modifications n'apparaissent pas tant que vous ne lancez pas une nouvelle requête sur l'instantané.  Si vous voulez voir les enregistrements ajoutés ou supprimés par d'autres utilisateurs dans l'instantané, ou les enregistrements ajoutés par d'autres utilisateurs dans la feuille de réponse dynamique, appelez [CRecordset::Requery](../Topic/CRecordset::Requery.md) pour reconstruire le recordset. \(Remarquez que les suppressions des autres utilisateurs apparaissent dans la feuille de réponse dynamique\). Vous pouvez aussi appeler **Requery** pour voir les enregistrements que vous ajoutez, mais non pour voir vos propres suppressions.  
  
> [!TIP]
>  Pour imposer la mise en cache immédiate de la totalité d'un instantané, appelez `MoveLast` dès que vous avez ouvert l'instantané,  Appelez ensuite **MoveFirst** pour commencer à utiliser les enregistrements.  `MoveLast` est équivalent au défilement sur tous les enregistrements, mais il les extrait tous à la fois.  Notez, cependant, que les performances peuvent s'en trouver dégradées et que cette action est déconseillée dans le cas de certains pilotes.  
  
 Vos mises à jour influent sur celles des autres utilisateurs de la même façon que les leurs influent sur les vôtres.  
  
##  <a name="_core_more_about_update_and_delete"></a> Informations complémentaires sur Update et Delete  
 La présente section propose des informations complémentaires sur l'utilisation de **Update** et de **Delete**.  
  
### Bon déroulement ou échec d'Update  
 Si **Update** se déroule avec succès, le mode `AddNew` ou **Edit** prend fin.  Pour revenir de nouveau au mode `AddNew` ou **Edit**, appelez `AddNew` ou **Edit**.  
  
 Si **Update** échoue \(la valeur **FALSE** est retournée ou une exception est levée\), vous demeurez en mode `AddNew` ou **Edit**, selon la fonction qui a été appelée en dernier.  Vous pouvez alors effectuer l'une des actions suivantes :  
  
-   Modifier un membre de données de type champ et essayer **Update** de nouveau.  
  
-   Appeler `AddNew` pour réinitialiser les membres de données de type champ avec la valeur Null, puis définir les valeurs des membres de données de type champ et appeler de nouveau **Update**.  
  
-   Appeler **Edit** pour recharger les valeurs qui se trouvaient dans le recordset avant le premier appel de `AddNew` ou **Edit**, puis définir les valeurs des membres de données de type champ et appeler de nouveau **Update**.  Lorsque l'appel de **Update** s'est déroulé avec succès \(sauf après un appel de `AddNew`\), les membres de données de type champ conservent leurs nouvelles valeurs.  
  
-   Appeler **Move** \(y compris l'appel de **Move** incluant un paramètre de **AFX\_MOVE\_REFRESH**, ou 0\), qui purge les modifications effectuées et met fin au mode `AddNew` ou **Edit** en vigueur.  
  
### Update et Delete  
 Cette section s'applique à **Update** et à **Delete**.  
  
 Lors d'une opération **Update** ou **Delete**, un enregistrement et un seul doit être mis à jour.  Cet enregistrement constitue l'enregistrement courant, qui correspond aux valeurs des données dans les champs du recordset.  Si pour une raison ou une autre, aucun enregistrement n'est concerné ou que deux ou plusieurs enregistrements le sont, une exception est levée et **RETCODE** contient l'une des valeurs suivantes :  
  
-   **AFX\_SQL\_ERROR\_NO\_ROWS\_AFFECTED**  
  
-   **AFX\_SQL\_ERROR\_MULTIPLE\_ROWS\_AFFECTED**  
  
 Lorsque ces exceptions sont levées, vous demeurez dans le mode `AddNew` ou **Edit** où vous vous trouviez lors de l'appel de **Update** ou **Delete**.  Vous trouverez ci\-après quelques\-uns des cas de figure où ces exceptions sont susceptibles de se produire.  Par exemple :  
  
-   **AFX\_SQL\_ERROR\_NO\_ROWS\_AFFECTED** apparaît quand vous utilisez le mode de verrouillage optimiste et qu'un autre utilisateur a modifié l'enregistrement de telle façon que l'infrastructure ne peut identifier correctement l'enregistrement à modifier ou à supprimer.  
  
-   **AFX\_SQL\_ERROR\_MULTIPLE\_ROWS\_AFFECTED** apparaît lorsque la table que vous mettez à jour ne possède pas de clé primaire ou d'index unique, et que vous n'avez pas un nombre suffisant de colonnes dans le recordset pour identifier de façon unique la ligne d'une table.  
  
## Voir aussi  
 [Recordset \(ODBC\)](../../data/odbc/recordset-odbc.md)   
 [Recordset : sélection d'enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md)   
 [Record Field Exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [SQL](../../data/odbc/sql.md)   
 [Exceptions : exceptions de base de données](../../mfc/exceptions-database-exceptions.md)