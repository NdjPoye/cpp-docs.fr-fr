---
title: "CRecordset Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CRecordset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRecordset class"
  - "database records [C++]"
  - "ODBC (recordsets C++), CRecordset (objets)"
  - "sets of records [C++]"
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRecordset Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un ensemble d'enregistrements sélectionnés à partir d'une source de données.  
  
## Syntaxe  
  
```  
class CRecordset : public CObject  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CRecordset::CRecordset](../Topic/CRecordset::CRecordset.md)|Construit un objet `CRecordset`.  Votre classe dérivée doit fournir un constructeur qui appelle celui\-ci.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRecordset::AddNew](../Topic/CRecordset::AddNew.md)|Se prépare à ajouter un nouvel enregistrement.  Appel `Update` pour effectuer l'addition.|  
|[CRecordset::CanAppend](../Topic/CRecordset::CanAppend.md)|Retourne une valeur différente de zéro si les nouveaux enregistrements peuvent être ajoutés au recordset via la fonction membre d' `AddNew` .|  
|[CRecordset::CanBookmark](../Topic/CRecordset::CanBookmark.md)|Retourne une valeur différente de zéro si le recordset prend en charge des signets.|  
|[CRecordset::Cancel](../Topic/CRecordset::Cancel.md)|Annule une opération asynchrone ou un processus d'un deuxième thread.|  
|[CRecordset::CancelUpdate](../Topic/CRecordset::CancelUpdate.md)|Annule toutes les mises à jour en attente en raison d'une opération d' `AddNew` ou d' `Edit` .|  
|[CRecordset::CanRestart](../Topic/CRecordset::CanRestart.md)|Retourne une valeur différente de zéro si `Requery` peut être appelé pour exécuter la requête du recordset de nouveau.|  
|[CRecordset::CanScroll](../Topic/CRecordset::CanScroll.md)|Retourne une valeur différente de zéro si vous pouvez parcourir les enregistrements.|  
|[CRecordset::CanTransact](../Topic/CRecordset::CanTransact.md)|Retourne une valeur différente de zéro si la source de données prend en charge les transactions.|  
|[CRecordset::CanUpdate](../Topic/CRecordset::CanUpdate.md)|Retourne une valeur différente de zéro si le recordset peut être mis à jour \(vous pouvez ajouter, mettre à jour, ou supprimer des enregistrements\).|  
|[CRecordset::CheckRowsetError](../Topic/CRecordset::CheckRowsetError.md)|Appelé pour gérer les erreurs générées pendant la récupération d'enregistrement.|  
|[CRecordset::Close](../Topic/CRecordset::Close.md)|Ferme le recordset et l'ODBC **HSTMT** associé.|  
|[CRecordset::Delete](../Topic/CRecordset::Delete.md)|Supprime l'enregistrement actif du recordset.  Vous devez explicitement le défilement à un autre enregistrement après la suppression.|  
|[CRecordset::DoBulkFieldExchange](../Topic/CRecordset::DoBulkFieldExchange.md)|Appelé pour échanger les lignes en bloc de données de la source de données vers le recordset.  Mécanisme RFX en bloc d'outils \(bulk RFX\).|  
|[CRecordset::DoFieldExchange](../Topic/CRecordset::DoFieldExchange.md)|Appelé pour échanger des données \(dans les deux sens\) entre les membres de données de type champ de recordset et l'enregistrement correspondant de la source de données.  Les outils signalent l'échange de RFX \(record field exchange\).|  
|[CRecordset::Edit](../Topic/CRecordset::Edit.md)|Se prépare à des modifications apportées à l'enregistrement courant.  Appel `Update` pour terminer la modification.|  
|[CRecordset::FlushResultSet](../Topic/CRecordset::FlushResultSet.md)|Retourne une valeur différente de zéro si un autre jeu de résultats à récupérer, en utilisant une requête prédéfinie.|  
|[CRecordset::GetBookmark](../Topic/CRecordset::GetBookmark.md)|Assigne la valeur du signet d'un enregistrement à l'objet paramètre.|  
|[CRecordset::GetDefaultConnect](../Topic/CRecordset::GetDefaultConnect.md)|Appelé pour obtenir la chaîne de connexion par défaut.|  
|[CRecordset::GetDefaultSQL](../Topic/CRecordset::GetDefaultSQL.md)|Appelé pour obtenir la chaîne SQL par défaut de l'exécution.|  
|[CRecordset::GetFieldValue](../Topic/CRecordset::GetFieldValue.md)|Retourne la valeur d'un champ d'un recordset.|  
|[CRecordset::GetODBCFieldCount](../Topic/CRecordset::GetODBCFieldCount.md)|Retourne le nombre de champs du recordset.|  
|[CRecordset::GetODBCFieldInfo](../Topic/CRecordset::GetODBCFieldInfo.md)|Retourne les types spécifiques d'informations sur les champs d'un recordset.|  
|[CRecordset::GetRecordCount](../Topic/CRecordset::GetRecordCount.md)|Retourne le nombre d'enregistrements du recordset.|  
|[CRecordset::GetRowsetSize](../Topic/CRecordset::GetRowsetSize.md)|Retourne le nombre d'enregistrements que vous souhaitez récupérer lors d'une seule extraction.|  
|[CRecordset::GetRowsFetched](../Topic/CRecordset::GetRowsFetched.md)|Retourne le nombre de lignes récupérées réel pendant un effort.|  
|[CRecordset::GetRowStatus](../Topic/CRecordset::GetRowStatus.md)|Retourne l'état de la ligne après un effort.|  
|[CRecordset::GetSQL](../Topic/CRecordset::GetSQL.md)|Obtient la chaîne SQL utilisée pour sélectionner des enregistrements du recordset.|  
|[CRecordset::GetStatus](../Topic/CRecordset::GetStatus.md)|Obtient l'état du recordset : l'index de l'enregistrement en cours et si un nombre final des enregistrements a été obtenu.|  
|[CRecordset::GetTableName](../Topic/CRecordset::GetTableName.md)|Obtient le nom de la table sur lequel le recordset est basé.|  
|[CRecordset::IsBOF](../Topic/CRecordset::IsBOF.md)|Retourne une valeur différente de zéro si le recordset a été positionné avant le premier enregistrement.  Il n'existe aucun enregistrement courant.|  
|[CRecordset::IsDeleted](../Topic/CRecordset::IsDeleted.md)|Retourne une valeur différente de zéro si le recordset est positionné sur un enregistrement supprimé.|  
|[CRecordset::IsEOF](../Topic/CRecordset::IsEOF.md)|Retourne une valeur différente de zéro si le recordset a été positionnée après le dernier enregistrement.  Il n'existe aucun enregistrement courant.|  
|[CRecordset::IsFieldDirty](../Topic/CRecordset::IsFieldDirty.md)|Retourne une valeur différente de zéro si le champ spécifié dans l'enregistrement en cours a été modifié.|  
|[CRecordset::IsFieldNull](../Topic/CRecordset::IsFieldNull.md)|Retourne une valeur différente de zéro si le champ spécifié dans l'enregistrement en cours est null \(n'a aucune valeur\).|  
|[CRecordset::IsFieldNullable](../Topic/CRecordset::IsFieldNullable.md)|Retourne une valeur différente de zéro si le champ spécifié dans l'enregistrement en cours peut avoir la valeur null \(n'ayant pas de valeur\).|  
|[CRecordset::IsOpen](../Topic/CRecordset::IsOpen.md)|Retourne une valeur différente de zéro si `Open` a été appelé précédemment.|  
|[CRecordset::Move](../Topic/CRecordset::Move.md)|Positionne le recordset en nombre d'enregistrements spécifié de l'enregistrement en cours dans l'un ou l'autre direction.|  
|[CRecordset::MoveFirst](../Topic/CRecordset::MoveFirst.md)|Positionne l'enregistrement actif sur le premier enregistrement du recordset.  Déterminez `IsBOF` en premier.|  
|[CRecordset::MoveLast](../Topic/CRecordset::MoveLast.md)|Positionne l'enregistrement actif sur le dernier enregistrement ou sur le dernier jeu de lignes.  Déterminez `IsEOF` en premier.|  
|[CRecordset::MoveNext](../Topic/CRecordset::MoveNext.md)|Positionne l'enregistrement en cours sur l'enregistrement suivant ou sur l'ensemble de lignes.  Déterminez `IsEOF` en premier.|  
|[CRecordset::MovePrev](../Topic/CRecordset::MovePrev.md)|Positionne l'enregistrement en cours sur l'enregistrement précédent ou sur le jeu de lignes précédent.  Déterminez `IsBOF` en premier.|  
|[CRecordset::OnSetOptions](../Topic/CRecordset::OnSetOptions.md)|Appelé pour définir des options \(utilisées sur la sélection\) pour l'instruction spécifiée ODBC.|  
|[CRecordset::OnSetUpdateOptions](../Topic/CRecordset::OnSetUpdateOptions.md)|Appelé pour définir des options \(utilisées sur la mise à jour\) pour l'instruction spécifiée ODBC.|  
|[CRecordset::Open](../Topic/CRecordset::Open.md)|Ouvre le recordset en extrayant la table ou en exécutant la requête que le recordset représente.|  
|[CRecordset::RefreshRowset](../Topic/CRecordset::RefreshRowset.md)|Actualise les données et l'état des lignes spécifiées.|  
|[CRecordset::Requery](../Topic/CRecordset::Requery.md)|Exécute la requête du recordset de nouveau pour actualiser les enregistrements sélectionnés.|  
|[CRecordset::SetAbsolutePosition](../Topic/CRecordset::SetAbsolutePosition.md)|Positionne le recordset dans l'enregistrement correspondant au numéro d'enregistrement spécifiée.|  
|[CRecordset::SetBookmark](../Topic/CRecordset::SetBookmark.md)|Positionne le recordset dans l'enregistrement spécifié par le signet.|  
|[CRecordset::SetFieldDirty](../Topic/CRecordset::SetFieldDirty.md)|Marque le champ spécifié dans l'enregistrement en cours comme changé.|  
|[CRecordset::SetFieldNull](../Topic/CRecordset::SetFieldNull.md)|Définit la valeur du champ spécifié dans l'enregistrement actif à null \(n'ayant pas de valeur\).|  
|[CRecordset::SetLockingMode](../Topic/CRecordset::SetLockingMode.md)|Définit le mode de verrouillage à verrouiller « optimiste » \(valeur par défaut\) ou à verrouillage pessimiste «  ».  Détermine comment les enregistrements sont verrouillés pour les mises à jour.|  
|[CRecordset::SetParamNull](../Topic/CRecordset::SetParamNull.md)|Définit le paramètre spécifié avec la valeur null \(n'ayant pas de valeur\).|  
|[CRecordset::SetRowsetCursorPosition](../Topic/CRecordset::SetRowsetCursorPosition.md)|Place le curseur sur la ligne spécifiée dans l'ensemble de lignes.|  
|[CRecordset::SetRowsetSize](../Topic/CRecordset::SetRowsetSize.md)|Spécifie le nombre d'enregistrements que vous souhaitez récupérer pendant un effort.|  
|[CRecordset::Update](../Topic/CRecordset::Update.md)|Termine une opération d' `AddNew` ou d' `Edit` en enregistrant les données nouvelles ou modifiées dans la source de données.|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CRecordset::m\_hstmt](../Topic/CRecordset::m_hstmt.md)|Contient le modèle d'instruction ODBC pour le recordset.  Tapez `HSTMT`|  
|[CRecordset::m\_nFields](../Topic/CRecordset::m_nFields.md)|Contient le nombre de membres de données de type champ du recordset.  Tapez `UINT`|  
|[CRecordset::m\_nParams](../Topic/CRecordset::m_nParams.md)|Contient le nombre de membres de données de type paramètre dans le recordset.  Tapez `UINT`|  
|[CRecordset::m\_pDatabase](../Topic/CRecordset::m_pDatabase.md)|Contient un pointeur vers l'objet d' `CDatabase` via lequel le recordset est connecté à une source de données.|  
|[CRecordset::m\_strFilter](../Topic/CRecordset::m_strFilter.md)|Contient `CString` qui spécifie une clause de `WHERE` \(SQL\) SQL.  Utilisé en tant que filtre pour sélectionner uniquement les enregistrements qui répondent à certains critères.|  
|[CRecordset::m\_strSort](../Topic/CRecordset::m_strSort.md)|Contient `CString` qui spécifie une clause SQL `ORDER BY` .  Utilisé pour contrôler la façon dont les enregistrements sont triés.|  
  
## Notes  
 Appelés « recordsets, » des objets d' `CRecordset` sont généralement utilisés sous deux formes : feuilles de réponse dynamiques et instantanés.  Une feuille de réponse dynamique reste synchronisé avec les mises à jour de données effectuées par d'autres utilisateurs.  Un instantané est une vue statique des données.  Chaque forme représente un ensemble d'enregistrements résolus au moment où le recordset est ouvert, mais lorsque vous accédez à un enregistrement dans une feuille de réponse dynamique, il indique ensuite les modifications apportées à l'enregistrement, par d'autres utilisateurs ou par d'autres recordsets de votre application.  
  
> [!NOTE]
>  Si vous utilisez DAO \(DAO\) classe plutôt que les classes ODBC \(Open Database Connectivity\), utilisez la classe [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) à la place.  Pour plus d'informations, consultez l'article [présentation : Programmation de bases de données](../../data/data-access-programming-mfc-atl.md).  
  
 Pour utiliser l'un ou l'autre de type de recordset, vous dérivez généralement une classe de recordset spécifique à l'application d' `CRecordset`.  Les recordsets des enregistrements d'une source de données, et vous pouvez ensuite :  
  
-   Parcourir les enregistrements.  
  
-   Mettre à jour des enregistrements et spécifiez à jour le mode de verrouillage.  
  
-   Filtrez le recordset pour limiter les enregistrements il choisit parmi celles disponibles dans la source de données.  
  
-   Trier le recordset.  
  
-   Paramétrer le recordset pour personnaliser la sélection des informations inconnues qu'au moment de l'exécution.  
  
 Pour utiliser votre classe, ouvrir une base de données et construire un objet recordset, en passant le constructeur un pointeur vers l'objet d' `CDatabase` .  Appelez la fonction membre de **Ouvrir** du recordset, où vous pouvez spécifier si l'objet est une feuille de réponse dynamique ou un instantané.  Appeler **Ouvrir** sélectionne des données de la source de données.  Une fois que l'objet recordset est ouvert, utilisez ses fonctions membres et données membres pour parcourir les enregistrements et pour les traiter.  Les opérations disponibles dépendent de si l'objet est une feuille de réponse dynamique ou un instantané, s'il peut être mise à jour ou en lecture seule \(cela dépend de la capacité de la source de données ODBC \(Open Database Connectivity\)\), et si vous avez implémenté l'extraction de lignes en bloc.  Pour actualiser les enregistrements qui ont peut\-être été modifiés ou ajoutés comme l'appel de **Ouvrir** , appelez la fonction membre de **Requery** de l'objet.  Appelez la fonction membre de **Fermer** de l'objet et détruisez l'objet lorsque vous avez terminé avec elle.  
  
 Dans une classe dérivée d' `CRecordset` , l'record field exchange \(bulk RFX\) ou RFX en bloc \(bulk RFX\) est utilisé pour prendre en charge la lecture et mettre à jour les champs d'enregistrement.  
  
 Pour plus d'informations sur les recordsets et l'record field exchange, consultez les articles [présentation : Programmation de bases de données](../../data/data-access-programming-mfc-atl.md), [recordset \(ODBC\)](../../data/odbc/recordset-odbc.md), [recordset : Extraction globale d'enregistrements \(ODBC\)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md), et [Record field exchange \(RFX\)](../../data/odbc/record-field-exchange-rfx.md).  Pour un focus sur les feuilles de réponse dynamiques et des instantanés, consultez les articles [dynaset](../../data/odbc/dynaset.md) et [instantané](../../data/odbc/snapshot.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CRecordset`  
  
## Configuration requise  
 **Header:** afxdb.h  
  
## Voir aussi  
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CDatabase Class](../../mfc/reference/cdatabase-class.md)   
 [CRecordView Class](../../mfc/reference/crecordview-class.md)