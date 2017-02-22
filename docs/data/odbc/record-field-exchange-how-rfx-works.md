---
title: "Record Field Exchange&#160;: fonctionnement de RFX | Microsoft Docs"
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
  - "liaison de données (C++), DFX"
  - "ODBC (C++), RFX"
  - "modification d'enregistrements (C++), utiliser RFX"
  - "RFX (ODBC) (C++), lier des champs et des paramètres"
  - "RFX (ODBC) (C++), mettre à jour les données dans les recordsets"
  - "défilement (C++)"
  - "défilement (C++), RFX"
ms.assetid: e647cacd-62b0-4b80-9e20-b392deca5a88
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Record Field Exchange&#160;: fonctionnement de RFX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La présente rubrique explique le processus RFX.  Cette rubrique avancée couvre :  
  
-   [RFX et le recordset](#_core_rfx_and_the_recordset)  
  
-   [Le processus RFX](#_core_the_record_field_exchange_process)  
  
> [!NOTE]
>  Cette rubrique s'applique aux classes dérivées de `CRecordset` dans lesquels l'extraction de lignes en bloc n'a pas été implémentée.  Si vous utilisez l'extraction de lignes en bloc, le mécanisme RFX en bloc \(Bulk RFX\) est implémenté.  RFX en bloc est similaire à RFX.  Pour plus d'informations sur les différences, consultez [Recordset : extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="_core_rfx_and_the_recordset"></a> RFX et l'objet du recordset  
 Les données membre de champ de l'objet recordset constituent à eux tous un tampon d'édition qui contient les colonnes sélectionnées d'un enregistrement unique.  Lorsque le recordset est ouvert pour la première fois et qu'il s'apprête à lire le premier enregistrement, RFX lie \(associe\) chaque colonne sélectionnée à l'adresse du membre de données de type champ approprié.  Quand le recordset met à jour un enregistrement, RFX appelle les fonctions API ODBC pour envoyer une instruction SQL **UPDATE** ou **INSERT** au pilote.  RFX utilise sa connaissance des membres de données de type champ pour indiquer les colonnes à écrire.  
  
 Comme l'infrastructure sauvegarde le tampon d'édition à certaines étapes, il peut restaurer son contenu si nécessaire.  RFX sauvegarde le tampon d'édition avant d'ajouter un nouvel enregistrement ou de modifier un enregistrement existant.  RFX restaure le tampon d'édition dans certains cas : par exemple, après un appel **Update** suivant `AddNew`.  Le tampon d'édition n'est pas restauré si vous quittez un tampon d'édition nouvellement modifié \(en vous déplaçant, par exemple, sur un nouvel enregistrement avant d'appeler **Update\)**.  
  
 En dehors de l'échange de données entre la source de données et les membres de données de type champ de recordset, RFX gère la liaison des paramètres.  Quand le recordset est ouvert, tous les membres de données de type paramètre sont liés dans l'ordre des emplacements réservés « ? » de l'instruction SQL construite par `CRecordset::Open`.  Pour plus d'informations, consultez [Recordset : paramétrage d'un recordset \(ODBC\)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
 La substitution de `DoFieldExchange` de votre classe du recordset effectue tout le travail, transférant les données dans les deux directions.  De même que DDX \(Dialog Data eXchange\), RFX a besoin d'informations concernant les membres de données de votre classe.  L'Assistant fournit les informations nécessaires en écrivant automatiquement une implémentation de `DoFieldExchange` propre au recordset, à partir des noms de membres de données de type champ et des types de données que vous avez indiqués dans l'Assistant.  
  
##  <a name="_core_the_record_field_exchange_process"></a> Processus d'échange des champs d'enregistrements  
 La présente section décrit l'ordre des événements RFX lorsqu'un objet recordset est ouvert et que vous ajoutez, modifiez ou supprimez des enregistrements.  Les tableaux [Ordre des opérations RFX lors de l'ouverture d'un recordset](#_core_sequence_of_rfx_operations_during_recordset_open) et [Ordre des opérations RFX lors d'un défilement](#_core_sequence_of_rfx_operations_during_scrolling) de la présente rubrique illustrent les processus activés quand RFX traite une commande **Move** dans le recordset et gère une mise à jour.  Au cours de ces processus, [DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md) est plusieurs fois appelé pour effectuer différentes opérations.  Le membre de données **m\_nOperation** de l'objet [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) détermine l'opération qui est demandée.  Avant de poursuivre, il peut être utile de consulter [Recordset : sélection d'enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md) et [Recordset : modification des enregistrements par les recordsets \(ODBC\)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
###  <a name="_mfc_rfx.3a_.initial_binding_of_columns_and_parameters"></a> RFX : liaison initiale des colonnes et des paramètres  
 Les activités RFX détaillées ci\-après surviennent, dans l'ordre indiqué, quand vous appelez la fonction membre [Open](../Topic/CRecordset::Open.md) d'un objet recordset :  
  
-   Si le recordset possède des membres de données de type paramètre, l'infrastructure appelle `DoFieldExchange` pour lier les paramètres aux emplacements de paramètres réservés dans la chaîne de l'instruction SQL du recordset.  Une représentation \(dépendant du type de données\) de la valeur du paramètre est utilisée pour chaque emplacement réservé de l'instruction **SELECT**.  L'action précédente a lieu après la préparation de l'instruction SQL, mais avant son exécution.  Pour plus d'informations sur la préparation de l'instruction, consultez la fonction **::SQLPrepare** dans le *Guide de référence du programmeur* ODBC.  
  
-   L'infrastructure appelle `DoFieldExchange` une seconde fois pour lier les valeurs des colonnes sélectionnées aux membres de données de type champ correspondants dans le recordset.  L'objet recordset devient ainsi un tampon d'édition contenant les colonnes du premier enregistrement.  
  
-   Le recordset exécute l'instruction SQL et la source de données sélectionne le premier enregistrement.  Les colonnes de l'enregistrement sont chargées dans les membres de données de champ de recordset.  
  
 Le tableau ci\-après répertorie l'ordre des opérations RFX lorsque vous ouvrez un recordset.  
  
### Ordre des opérations RFX lors de l'ouverture d'un recordset  
  
|Votre opération|DoFieldExchange|Opération de base de données\/SQL|  
|---------------------|---------------------|---------------------------------------|  
|1.  Ouvrir le recordset.|||  
||2.  Générer une instruction SQL.||  
|||3.  Envoyer l'instruction SQL.|  
||4.  Lier les membres de données de type champ.||  
||5.  Lier les membres de données de type champ aux colonnes.||  
|||6.  ODBC effectue le transfert et insère les données.|  
||7.  Corriger les données pour C\+\+.||  
  
 Les recordsets utilisent l'exécution préparée d'ODBC pour permettre le lancement rapide d'une nouvelle requête avec la même instruction SQL.  Pour plus d'informations sur l'exécution préparée, consultez le guide ODBC SDK *Programmer's Reference* dans MSDN Library.  
  
###  <a name="_mfc_rfx.3a_.scrolling"></a> RFX : défilement  
 Lorsque vous passez d'un enregistrement à un autre, l'infrastructure appelle `DoFieldExchange` pour remplacer les valeurs précédemment stockées dans les membres de données de type champ par les valeurs du nouvel enregistrement.  
  
 Le tableau ci\-après répertorie l'ordre des opérations RFX lorsque l'utilisateur se déplace d'enregistrement en enregistrement.  
  
### Ordre des opérations RFX lors du défilement  
  
|Votre opération|DoFieldExchange|Opération de base de données\/SQL|  
|---------------------|---------------------|---------------------------------------|  
|1.  Appeler `MoveNext` ou une autre fonction Move.|||  
|||2.  ODBC effectue le transfert et insère les données.|  
||3.  Corriger les données pour C\+\+.||  
  
###  <a name="_mfc_rfx.3a_.adding_new_records_and_editing_existing_records"></a> RFX : ajout de nouveaux enregistrements et modification des enregistrements existants  
 Si vous ajoutez un enregistrement, le recordset fonctionne comme un tampon d'édition en vue de constituer le contenu du nouvel enregistrement.  Comme l'ajout d'enregistrements, la modification d'enregistrements existants entraîne une modification des valeurs des membres de données de champ dans le recordset.  Sous l'angle RFX, l'ordre des événements est le suivant :  
  
1.  Votre appel de la fonction membre [AddNew](../Topic/CRecordset::AddNew.md) ou [Edit](../Topic/CRecordset::Edit.md) du recordset entraîne le stockage par RFX du tampon d'édition en cours, afin de pouvoir le restaurer par la suite.  
  
2.  `AddNew` ou **Edit** prépare les champs du tampon d'édition afin que RFX puisse identifier les membres de données de type champ ayant été modifiés.  
  
     Comme un nouvel enregistrement n'a pas de valeurs initiales auxquelles les nouvelles valeurs puissent être comparées, `AddNew` définit la valeur de chaque membre de données de type champ avec la valeur **PSEUDO\_NULL**.  Par la suite, lorsque vous appelez **Update**, RFX compare chaque valeur des membres de données à la valeur **PSEUDO\_NULL**.  S'il existe une différence, alors le membre de données a été défini. \(**PSEUDO\_NULL** n'est pas la même chose qu'une colonne d'enregistrement ayant la valeur Null ou que la valeur **NULL en C\+\+**.\)  
  
     À l'inverse de l'appel **Update** de `AddNew`, l'appel **Update** de **Edit** compare les valeurs mises à jour avec les valeurs précédemment stockées plutôt que d'utiliser **PSEUDO\_NULL**.  La différence est que `AddNew` n'a pas de valeurs préalablement stockées qui puissent être prises à titre de comparaison.  
  
3.  Vous définissez directement les valeurs des membres de données de champ que vous souhaitez modifier ou renseigner pour un nouvel enregistrement.  Vous pouvez être amené à appeler de `SetFieldNull`.  
  
4.  L'appel de [Update](../Topic/CRecordset::Update.md) vérifie la présence de membres de données de type champ ayant été modifiés, comme indiqué à l'étape 2 \(consultez le tableau [Ordre des opérations RFX lors du défilement](#_core_sequence_of_rfx_operations_during_scrolling)\).  S'il n'y a aucun changement, **Update** retourne 0.  Si certaines données membres de champ ont changé, **Update** prépare et exécute une instruction SQL **INSERT** qui contient des valeurs pour tous les champs mis à jour dans l'enregistrement.  
  
5.  Pour `AddNew`, **Update** termine en restaurant les valeurs stockées précédemment dans l'enregistrement en cours juste avant l'appel `AddNew`.  Dans le cas de **Edit**, les nouvelles valeurs modifiées demeurent en place.  
  
 Le tableau ci\-après répertorie l'ordre des opérations RFX lorsque vous ajoutez un nouvel enregistrement ou modifiez un enregistrement existant.  
  
### Ordre des opérations RFX lors de l'ajout ou de la modification d'un enregistrement  
  
|Votre opération|DoFieldExchange|Opération de base de données\/SQL|  
|---------------------|---------------------|---------------------------------------|  
|1.  Appeler `AddNew` ou **Edit**.|||  
||2.  Sauvegarder le tampon d'édition.||  
||3.  Pour `AddNew`, marquer les membres de données de champ comme « clean » et Null.||  
|4.  Assigner des valeurs aux membres de données de champ de recordset.|||  
|5.  Appeler **Update**.|||  
||6.  Vérifier les champs modifiés.||  
||7.  Générer l'instruction SQL **INSERT** pour `AddNew` ou l'instruction **UPDATE** pour **Edit**.||  
|||8.  Envoyer l'instruction SQL.|  
||9.  Pour `AddNew`, restaurer le tampon d'édition avec son contenu sauvegardé.  Dans le cas de **Edit**, supprimer la sauvegarde.||  
  
### RFX : suppression d'enregistrements existants  
 Lorsque vous supprimez un enregistrement, RFX attribue la valeur **NULL** à tous les champs afin que vous vous rappeliez que l'enregistrement a été supprimé et que vous devez l'enlever.  Vous n'avez besoin d'aucune autre information sur l'ordre des événements RFX.  
  
## Voir aussi  
 [Record Field Exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md)   
 [MFC ODBC, consommation](../../mfc/reference/adding-an-mfc-odbc-consumer.md)   
 [Macros, fonctions globales et variables globales](../Topic/Macros,%20Global%20Functions,%20and%20Global%20Variables.md)   
 [CFieldExchange Class](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)