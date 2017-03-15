---
title: Classe CRecordset | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CRecordset
dev_langs:
- C++
helpviewer_keywords:
- database records [C++]
- CRecordset class
- ODBC recordsets [C++], CRecordset objects
- sets of records [C++]
ms.assetid: dd89a21d-ef39-4aab-891b-1e373d67c855
caps.latest.revision: 23
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: f7a05a5eefd6f55a68c6e9f1726dfb7c29f399f2
ms.lasthandoff: 02/24/2017

---
# <a name="crecordset-class"></a>CRecordset (classe)
Représente un ensemble d'enregistrements sélectionnés à partir d'une source de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CRecordset : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRecordset::CRecordset](#crecordset)|Construit un objet `CRecordset`. Votre classe dérivée doit fournir un constructeur qui appelle celui-ci.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CRecordset::AddNew](#addnew)|Prépare pour ajouter un nouvel enregistrement. Appelez `Update` pour terminer l’ajout.|  
|[CRecordset::CanAppend](#canappend)|Retourne zéro si les nouveaux enregistrements peuvent être ajoutés à l’objet recordset via la `AddNew` fonction membre.|  
|[CRecordset::CanBookmark](#canbookmark)|Retourne zéro si le jeu d’enregistrements prend en charge les signets.|  
|[CRecordset::Cancel](#cancel)|Annule une opération asynchrone ou un processus à partir d’un deuxième thread.|  
|[CRecordset::CancelUpdate](#cancelupdate)|Annule les mises à jour en attente due à une `AddNew` ou `Edit` opération.|  
|[CRecordset::CanRestart](#canrestart)|Retourne zéro si `Requery` peut être appelée pour exécuter de nouveau la requête du recordset.|  
|[CRecordset::CanScroll](#canscroll)|Retourne zéro si vous pouvez faire défiler les enregistrements.|  
|[CRecordset::CanTransact](#cantransact)|Retourne zéro si la source de données prend en charge les transactions.|  
|[CRecordset::CanUpdate](#canupdate)|Retourne zéro si le jeu d’enregistrements peut être mis à jour (vous pouvez ajouter, mettre à jour ou supprimer des enregistrements).|  
|[CRecordset::CheckRowsetError](#checkrowseterror)|Appelé pour gérer les erreurs générées lors de la lecture d’enregistrements.|  
|[Préférence CRecordset::Close](#close)|Ferme le recordset et ODBC **HSTMT** associé.|  
|[CRecordset::Delete](#delete)|Supprime l’enregistrement actif du jeu d’enregistrements. Après la suppression, vous devez explicitement faire défiler à un autre enregistrement.|  
|[CRecordset::DoBulkFieldExchange](#dobulkfieldexchange)|Appelé pour échanger des lignes en bloc des données à partir de la source de données vers le recordset. Implémente en masse d’échange de champs d’enregistrements (RFX en bloc).|  
|[CRecordset::DoFieldExchange](#dofieldexchange)|Appelé pour échanger des données (dans les deux sens) entre les membres de données de champ du jeu d’enregistrements et l’enregistrement correspondant de la source de données. Implémente enregistre l’échange de champs (RFX).|  
|[CRecordset::Edit](#edit)|Prépare les modifications à l’enregistrement actif. Appelez `Update` pour terminer la modification.|  
|[CRecordset::FlushResultSet](#flushresultset)|Retourne zéro s’il existe un autre résultat défini à récupérer, lors de l’utilisation d’une requête prédéfinie.|  
|[CRecordset::GetBookmark](#getbookmark)|Affecte la valeur du signet d’un enregistrement à l’objet de paramètre.|  
|[CRecordset::GetDefaultConnect](#getdefaultconnect)|Appelé pour obtenir la chaîne de connexion par défaut.|  
|[CRecordset::GetDefaultSQL](#getdefaultsql)|Appelé pour obtenir la chaîne SQL par défaut à exécuter.|  
|[CRecordset::GetFieldValue](#getfieldvalue)|Retourne la valeur d’un champ dans un jeu d’enregistrements.|  
|[CRecordset::GetODBCFieldCount](#getodbcfieldcount)|Retourne le nombre de champs dans le jeu d’enregistrements.|  
|[CRecordset::GetODBCFieldInfo](#getodbcfieldinfo)|Retourne des informations sur les champs particuliers dans un jeu d’enregistrements.|  
|[CRecordset::GetRecordCount](#getrecordcount)|Retourne le nombre d’enregistrements dans le jeu d’enregistrements.|  
|[CRecordset::GetRowsetSize](#getrowsetsize)|Retourne le nombre d’enregistrements que vous souhaitez récupérer au cours d’une seule extraction.|  
|[CRecordset::GetRowsFetched](#getrowsfetched)|Retourne le nombre réel de lignes récupérées lors d’une extraction.|  
|[CRecordset::GetRowStatus](#getrowstatus)|Retourne l’état de la ligne après une extraction.|  
|[CRecordset::GetSQL](#getsql)|Obtient la chaîne SQL utilisée pour sélectionner des enregistrements du jeu d’enregistrements.|  
|[CRecordset::GetStatus](#getstatus)|Obtient l’état de l’objet recordset : l’index de l’enregistrement en cours et si un nombre final des enregistrements a été obtenu.|  
|[CRecordset::GetTableName](#gettablename)|Obtient le nom de la table sur laquelle repose le jeu d’enregistrements.|  
|[CRecordset::IsBOF](#isbof)|Retourne zéro si le jeu d’enregistrements a été positionné avant le premier enregistrement. Il n’existe aucun enregistrement actif.|  
|[CRecordset::IsDeleted](#isdeleted)|Retourne zéro si le recordset est positionné sur un enregistrement supprimé.|  
|[CRecordset::IsEOF](#iseof)|Retourne zéro si le jeu d’enregistrements a été positionné après le dernier enregistrement. Il n’existe aucun enregistrement actif.|  
|[CRecordset::IsFieldDirty](#isfielddirty)|Retourne zéro si le champ spécifié dans l’enregistrement actif a été modifié.|  
|[CRecordset::IsFieldNull](#isfieldnull)|Retourne zéro si le champ spécifié dans l’enregistrement actif est null (n’a aucune valeur).|  
|[CRecordset::IsFieldNullable](#isfieldnullable)|Retourne zéro si le champ spécifié dans l’enregistrement actif peut être défini sur null (n’ayant aucune valeur).|  
|[CRecordset::IsOpen](#isopen)|Retourne zéro si `Open` a été appelé précédemment.|  
|[CRecordset::Move](#move)|Positionne le jeu d’enregistrements à un nombre spécifié d’enregistrements à partir de l’enregistrement en cours dans les deux sens.|  
|[CRecordset::MoveFirst](#movefirst)|Positionne l’enregistrement actif sur le premier enregistrement du jeu d’enregistrements. Test de `IsBOF` première.|  
|[CRecordset::MoveLast](#movelast)|Positionne l’enregistrement actif sur le dernier enregistrement ou sur le dernier jeu de lignes. Test de `IsEOF` première.|  
|[CRecordset::MoveNext](#movenext)|Positionne l’enregistrement en cours sur l’enregistrement suivant ou sur l’ensemble de lignes suivant. Test de `IsEOF` première.|  
|[CRecordset::MovePrev](#moveprev)|Positionne l’enregistrement en cours sur l’enregistrement précédent ou sur l’ensemble de lignes précédente. Test de `IsBOF` première.|  
|[CRecordset::OnSetOptions](#onsetoptions)|Appelé pour définir les options (utilisées dans la sélection) pour l’instruction ODBC spécifiée.|  
|[CRecordset::OnSetUpdateOptions](#onsetupdateoptions)|Appelé pour définir les options (utilisées sur la mise à jour) pour l’instruction ODBC spécifiée.|  
|[CRecordset::Open](#open)|Ouvre le recordset en exécutant la requête qui représente le jeu d’enregistrements ou de récupération de la table.|  
|[CRecordset::RefreshRowset](#refreshrowset)|Actualise les données et l’état de la ligne (s) spécifié.|  
|[CRecordset::Requery](#requery)|Exécute la requête du recordset pour actualiser les enregistrements sélectionnés.|  
|[CRecordset::SetAbsolutePosition](#setabsoluteposition)|Positionne le jeu d’enregistrements dans l’enregistrement correspondant au numéro d’enregistrement spécifié.|  
|[CRecordset::SetBookmark](#setbookmark)|Positionne le jeu d’enregistrements dans l’enregistrement spécifié par le signet.|  
|[CRecordset::SetFieldDirty](#setfielddirty)|Marque le champ spécifié dans l’enregistrement actif comme étant modifié.|  
|[CRecordset::SetFieldNull](#setfieldnull)|Définit la valeur du champ spécifié dans l’enregistrement actif null (n’ayant aucune valeur).|  
|[CRecordset::SetLockingMode](#setlockingmode)|Définit le mode de verrouillage « optimiste » verrouillage (par défaut) ou « pessimiste ». Détermine la façon dont les enregistrements sont verrouillés pour les mises à jour.|  
|[CRecordset::SetParamNull](#setparamnull)|Définit le paramètre spécifié en valeur null (n’ayant aucune valeur).|  
|[CRecordset::SetRowsetCursorPosition](#setrowsetcursorposition)|Positionne le curseur sur la ligne spécifiée dans l’ensemble de lignes.|  
|[CRecordset::SetRowsetSize](#setrowsetsize)|Spécifie le nombre d’enregistrements que vous souhaitez récupérer lors d’une extraction.|  
|[CRecordset::Update](#update)|Termine une `AddNew` ou `Edit` opération en enregistrant les données nouvelles ou modifiées sur la source de données.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CRecordset::m_hstmt](#m_hstmt)|Contient le descripteur d’instruction ODBC pour le jeu d’enregistrements. Tapez `HSTMT`.|  
|[CRecordset::m_nFields](#m_nfields)|Contient le nombre de membres de données de champ dans le jeu d’enregistrements. Tapez `UINT`.|  
|[CRecordset::m_nParams](#m_nparams)|Contient le nombre de membres de données de paramètre dans le jeu d’enregistrements. Tapez `UINT`.|  
|[CRecordset::m_pDatabase](#m_pdatabase)|Contient un pointeur vers le `CDatabase` objet via lequel le jeu d’enregistrements est connecté à une source de données.|  
|[CRecordset::m_strFilter](#m_strfilter)|Contient un `CString` qui spécifie un langage SQL (Structured Query) `WHERE` clause. Utilisé comme un filtre pour sélectionner uniquement les enregistrements qui répondent à certains critères.|  
|[CRecordset::m_strSort](#m_strsort)|Contient un `CString` qui spécifie une SQL `ORDER BY` clause. Utilisé pour contrôler la façon dont les enregistrements sont triés.|  
  
## <a name="remarks"></a>Remarques  
 Appelé « jeux d’enregistrements, » `CRecordset` objets sont généralement utilisés dans les deux formes : feuilles de réponse dynamiques et les instantanés. Feuille de réponse dynamique reste synchronisé avec les mises à jour de données effectuées par d’autres utilisateurs. Un instantané est une vue statique des données. Chaque écran représente un jeu d’enregistrements au moment de que l’objet recordset est ouvert, mais lorsque vous accédez à un enregistrement dans une feuille de réponse dynamique, il reflète les modifications apportées par la suite à l’enregistrement, par d’autres utilisateurs ou par d’autres jeux d’enregistrements dans votre application.  
  
> [!NOTE]
>  Si vous travaillez avec les classes d’objets d’accès aux données (DAO) plutôt que les classes Open Database Connectivity (ODBC), utilisez la classe [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) à la place. Pour plus d’informations, consultez l’article [vue d’ensemble : programmation de base de données](../../data/data-access-programming-mfc-atl.md).  
  
 Pour utiliser un type de jeu d’enregistrements, vous en général, dérivez une classe de jeu d’enregistrements spécifiques à l’application depuis `CRecordset`. Jeux d’enregistrements de sélectionner des enregistrements à partir d’une source de données, et vous pouvez ensuite :  
  
-   Faites défiler les enregistrements.  
  
-   Mettre à jour les enregistrements et spécifier un mode verrouillage.  
  
-   Filtrer le jeu d’enregistrements pour limiter les enregistrements qu’il sélectionne parmi ceux disponibles sur la source de données.  
  
-   Trier le jeu d’enregistrements.  
  
-   Paramétrer le recordset pour personnaliser sa sélection avec des informations inconnues jusqu’au moment de l’exécution.  
  
 Pour utiliser votre classe, ouvrez une base de données et construire un objet recordset, en passant le constructeur un pointeur vers votre `CDatabase` objet. Puis appelez le jeu d’enregistrements **Open** fonction membre, dans laquelle vous pouvez spécifier si l’objet est un dynaset ou un instantané. Appel de **Open** sélectionne les données de la source de données. Une fois que l’objet recordset est ouvert, utilisez ses membres de données et des fonctions membres pour faire défiler les enregistrements et opérer sur les. Les opérations disponibles varient selon que l’objet est une feuille de réponse dynamique ou un instantané, si elle est modifiable ou en lecture seule (Cela dépend de la capacité de la source de données Open Database Connectivity (ODBC)), et si vous avez implémenté l’extraction de lignes en bloc. Pour actualiser les enregistrements qui ont été être modifiés ou ajoutés depuis la **Open** appeler, appelez l’objet **Requery** fonction membre. Appelez l’objet **fermer** membre de fonction et de détruire l’objet lorsque vous avez terminé avec lui.  
  
 Dans un dérivé `CRecordset` de classe, d’enregistrer l’échange de champs (RFX) ou RFX en bloc (RFX en bloc) est utilisé pour prendre en charge la lecture et la mise à jour des champs d’enregistrement.  
  
 Pour plus d’informations sur l’échange de champs d’enregistrement et de jeux d’enregistrements, consultez les articles [vue d’ensemble : programmation de base de données](../../data/data-access-programming-mfc-atl.md), [Recordset (ODBC)](../../data/odbc/recordset-odbc.md), [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md), et [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md). Pour une vue sur les instantanés et les feuilles de réponse dynamiques, consultez les articles [Dynaset](../../data/odbc/dynaset.md) et [instantanés](../../data/odbc/snapshot.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CRecordset`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdb.h  
  
##  <a name="a-nameaddnewa--crecordsetaddnew"></a><a name="addnew"></a>CRecordset::AddNew  
 Prépare pour ajouter un nouvel enregistrement à la table.  
  
```  
virtual void AddNew();
```  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler le [Requery](#requery) fonction membre pour afficher le dernier enregistrement ajouté. Champs de l’enregistrement sont initialement nulle. (Dans la terminologie de base de données, Null donne « aucune valeur » et n’est pas le même que **NULL** en C++.) Pour terminer l’opération, vous devez appeler le [mise à jour](#update) fonction membre. **Mise à jour** enregistre vos modifications dans la source de données.  
  
> [!NOTE]
>  Si vous avez implémenté l’extraction de lignes en bloc, vous ne pouvez pas appeler `AddNew`. Cela entraîne un échec d’assertion. Bien que classe `CRecordset` ne fournit pas de mécanisme de mise à jour en bloc des lignes de données, vous pouvez écrire vos propres fonctions à l’aide de la fonction API ODBC **SQLSetPos**. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 `AddNew`prépare un nouvel enregistrement vide à l’aide des données membres de champ du jeu d’enregistrements. Après avoir appelé `AddNew`, définissez les valeurs souhaitées dans les données membres de champ du jeu d’enregistrements. (Vous n’avez pas à appeler le [modifier](#edit) fonction membre à cet effet ; utilisez **modifier** uniquement pour les enregistrements existants.) Lorsque vous appelez ensuite **mise à jour**, modifié les valeurs dans les membres de données de champ sont enregistrées dans la source de données.  
  
> [!CAUTION]
>  Si vous accédez à un nouvel enregistrement avant d’appeler **mise à jour**, le nouvel enregistrement est perdu et aucun avertissement n’est donné.  
  
 Si la source de données prend en charge les transactions, vous pouvez rendre votre `AddNew` des appels, partie d’une transaction. Pour plus d’informations sur les transactions, consultez la classe [CDatabase](../../mfc/reference/cdatabase-class.md). Notez que vous devez appeler [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) avant d’appeler `AddNew`.  
  
> [!NOTE]
>  Pour les dynasets, les nouveaux enregistrements sont ajoutés à l’objet recordset en tant que dernier enregistrement. Les enregistrements ajoutés ne sont pas ajoutés aux instantanés ; Vous devez appeler **Requery** pour actualiser le jeu d’enregistrements.  
  
 Il est interdit d’appeler `AddNew` pour un objet recordset dont **Open** fonction membre n’a pas été appelée. A `CDBException` est levée si vous appelez `AddNew` pour un jeu d’enregistrements qui ne peut pas être ajouté au. Vous pouvez déterminer si le jeu d’enregistrements est modifiable en appelant [CanAppend](#canappend).  
  
 Pour plus d’informations, consultez les articles suivants : [Recordset : mise à jour des enregistrements de jeux d’enregistrements (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md), [Recordset : ajout, modification et suppression d’enregistrements (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md), et [Transaction (ODBC)](../../data/odbc/transaction-odbc.md).  
  
### <a name="example"></a>Exemple  
 Consultez l’article [Transaction : exécution d’une Transaction dans un Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
##  <a name="a-namecanappenda--crecordsetcanappend"></a><a name="canappend"></a>CRecordset::CanAppend  
 Détermine si le jeu d’enregistrements précédemment ouvert vous permet d’ajouter des enregistrements.  
  
```  
BOOL CanAppend() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le jeu d’enregistrements permet d’ajouter de nouveaux enregistrements ; sinon 0. `CanAppend`retourne 0 si vous avez ouvert le jeu d’enregistrements en lecture seule.  
  
##  <a name="a-namecanbookmarka--crecordsetcanbookmark"></a><a name="canbookmark"></a>CRecordset::CanBookmark  
 Détermine si le jeu d’enregistrements vous permet de marquer les enregistrements à l’aide de signets.  
  
```  
BOOL CanBookmark() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le jeu d’enregistrements prend en charge les signets. sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est indépendante de la **CRecordset::useBookmarks** option dans le `dwOptions` paramètre de la [Open](#open) fonction membre. `CanBookmark`Indique si le pilote ODBC et le curseur type de prise en charge des signets. **CRecordset::useBookmarks** indique si les signets seront disponibles, sous réserve qu’ils sont pris en charge.  
  
> [!NOTE]
>  Les signets ne sont pas pris en charge sur les recordsets avant uniquement.  
  
 Pour plus d’informations sur les signets et de navigation de jeu d’enregistrements, consultez les articles [Recordset : signets et Positions absolues (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) et [Recordset : défilement (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="a-namecancela--crecordsetcancel"></a><a name="cancel"></a>CRecordset::Cancel  
 Demande que la source de données annule une opération asynchrone en cours ou un processus à partir d’un deuxième thread.  
  
```  
void Cancel();
```  
  
### <a name="remarks"></a>Notes  
 Notez que les classes ODBC MFC ne plus utilisent le traitement asynchrone ; Pour effectuer une opération asynchrone, vous devez appeler directement la fonction API ODBC **SQLSetConnectOption**. Pour plus d’informations, consultez la rubrique « L’exécution de fonctions en mode asynchrone » dans le *Guide du programmeur ODBC SDK*.  
  
##  <a name="a-namecancelupdatea--crecordsetcancelupdate"></a><a name="cancelupdate"></a>CRecordset::CancelUpdate  
 Annule toute en attente de mises à jour, provoqués par une [modifier](#edit) ou [AddNew](#addnew) opération, avant de [mise à jour](#update) est appelée.  
  
```  
void CancelUpdate();
```  
  
### <a name="remarks"></a>Notes  
  
> [!NOTE]
>  Cette fonction membre n’est pas applicable sur les jeux d’enregistrements qui est l’extraction de lignes en bloc, dans la mesure où ces jeux d’enregistrements ne peuvent pas appeler **modifier**, `AddNew`, ou **mise à jour**. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Si la vérification de champ incorrecte automatique est activée, `CancelUpdate` permet de restaurer les valeurs qu’ils avaient avant les variables de membre **modifier** ou `AddNew` a été appelé ; sinon, les modifications des valeurs restera. Par défaut, le contrôle de champ automatique est activé lorsque le jeu d’enregistrements est ouvert. Pour le désactiver, vous devez spécifier le **CRecordset::noDirtyFieldCheck** dans les `dwOptions` paramètre de la [Open](#open) fonction membre.  
  
 Pour plus d’informations sur la mise à jour des données, consultez l’article [Recordset : ajout, modification et suppression d’enregistrements (ODBC)](../../data/odbc/recordset-adding-updating-and-deleting-records-odbc.md).  
  
##  <a name="a-namecanrestarta--crecordsetcanrestart"></a><a name="canrestart"></a>CRecordset::CanRestart  
 Détermine si le jeu d’enregistrements autorise le redémarrage de la requête (pour actualiser ses enregistrements) en appelant le **Requery** fonction membre.  
  
```  
BOOL CanRestart() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si requery est autorisée ; sinon 0.  
  
##  <a name="a-namecanscrolla--crecordsetcanscroll"></a><a name="canscroll"></a>CRecordset::CanScroll  
 Détermine si le jeu d’enregistrements autorise le défilement.  
  
```  
BOOL CanScroll() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le jeu d’enregistrements permet le défilement ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations sur le défilement, consultez l’article [Recordset : défilement (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="a-namecantransacta--crecordsetcantransact"></a><a name="cantransact"></a>CRecordset::CanTransact  
 Détermine si le jeu d’enregistrements autorise les transactions.  
  
```  
BOOL CanTransact() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le jeu d’enregistrements autorise les transactions ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez l’article [Transaction (ODBC)](../../data/odbc/transaction-odbc.md).  
  
##  <a name="a-namecanupdatea--crecordsetcanupdate"></a><a name="canupdate"></a>CRecordset::CanUpdate  
 Détermine si le jeu d’enregistrements peut être mis à jour.  
  
```  
BOOL CanUpdate() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le jeu d’enregistrements peut être mis à jour ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Un jeu d’enregistrements peut être en lecture seule si la source de données sous-jacente est en lecture seule ou si vous avez spécifié **CRecordset::readOnly** dans le `dwOptions` paramètre lorsque vous avez ouvert le jeu d’enregistrements.  
  
##  <a name="a-namecheckrowseterrora--crecordsetcheckrowseterror"></a><a name="checkrowseterror"></a>CRecordset::CheckRowsetError  
 Appelé pour gérer les erreurs générées lors de la lecture d’enregistrements.  
  
```  
virtual void CheckRowsetError(RETCODE nRetCode);
```  
  
### <a name="parameters"></a>Paramètres  
 `nRetCode`  
 Code de retour de fonction d’API ODBC. Pour plus d'informations, consultez Notes.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre virtuelle gère les erreurs qui se produisent lorsque les enregistrements sont extraits, et est utile lors de l’extraction de lignes en bloc. Vous pouvez substituer `CheckRowsetError` pour implémenter votre propre gestion des erreurs.  
  
 `CheckRowsetError`est appelé automatiquement dans une opération de navigation de curseur, tels que **Open**, **Requery**, ou n’importe quel **déplacer** opération. Il est transmis à la valeur de retour de la fonction API ODBC **SQLExtendedFetch**. Le tableau suivant répertorie les valeurs possibles pour le `nRetCode` paramètre.  
  
|nRetCode|Description|  
|--------------|-----------------|  
|**SQL_SUCCESS**|Fonction a été exécutée avec succès ; Aucune information supplémentaire n’est disponible.|  
|**SQL_SUCCESS_WITH_INFO**|Fonction s’est terminée avec succès, éventuellement avec une erreur non fatale. Informations supplémentaires peuvent être obtenues en appelant **SQLError**.|  
|**SQL_NO_DATA_FOUND**|Toutes les lignes du jeu de résultats qui ont été extraites.|  
|**SQL_ERROR**|Échec de la fonction. Informations supplémentaires peuvent être obtenues en appelant **SQLError**.|  
|**SQL_INVALID_HANDLE**|Fonction a échoué en raison d’un handle d’environnement non valide, un handle de connexion ou un descripteur d’instruction. Cela indique une erreur de programmation. Aucune information supplémentaire n’est disponible à partir de **SQLError**.|  
|`SQL_STILL_EXECUTING`|Une fonction qui a été démarrée en mode asynchrone est en cours d’exécution. Notez que, par défaut, MFC ne passent jamais cette valeur pour `CheckRowsetError`; MFC continuera à appeler la méthode **SQLExtendedFetch** jusqu'à ce qu’il ne retourne plus `SQL_STILL_EXECUTING`.|  
  
 Pour plus d’informations sur **SQLError**, consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="a-nameclosea--crecordsetclose"></a><a name="close"></a>Préférence CRecordset::Close  
 Ferme l’objet recordset.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarques  
 ODBC **HSTMT** et toute la mémoire du framework allouée pour le jeu d’enregistrements sont libérés. Généralement après un appel **fermer**, vous supprimez l’objet recordset C++ si elle a été allouée avec **nouveau**.  
  
 Vous pouvez appeler **Open** à nouveau après avoir appelé **fermer**. Cela vous permet de réutiliser l’objet recordset. L’alternative consiste à appeler **Requery**.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDatabase&#17;](../../mfc/codesnippet/cpp/crecordset-class_1.cpp)]  
  
##  <a name="a-namecrecordseta--crecordsetcrecordset"></a><a name="crecordset"></a>CRecordset::CRecordset  
 Construit un objet `CRecordset`.  
  
```  
CRecordset(CDatabase* pDatabase = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDatabase`  
 Contient un pointeur vers un `CDatabase` objet ou la valeur **NULL**. Si ce n’est pas **NULL** et `CDatabase` l’objet **ouvrir** fonction membre n’a pas été appelée pour vous connecter à la source de données, le jeu d’enregistrements tente de l’ouvrir au cours de son propre **ouvrir** appeler. Si vous transmettez **NULL**, un `CDatabase` objet est construit et connecté automatiquement à l’aide des informations de source de données vous avez spécifié lorsque vous avez dérivé votre classe de recordset avec ClassWizard.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez utiliser `CRecordset` directement ou dériver une classe spécifique à l’application à partir de `CRecordset`. Vous pouvez utiliser ClassWizard pour dériver vos classes de jeu d’enregistrements.  
  
> [!NOTE]
>  Une classe dérivée *doit* fournir son propre constructeur. Dans le constructeur de votre classe dérivée, appelez le constructeur `CRecordset::CRecordset`, en passant les paramètres appropriés sur lui.  
  
 Transmettez **NULL** au constructeur de votre jeu d’enregistrements d’avoir un `CDatabase` objet construit et connecté automatiquement pour vous. Il s’agit d’un raccourci utile ne nécessitant pas construire et connecter un `CDatabase` objet avant de générer votre jeu d’enregistrements.  
  
### <a name="example"></a>Exemple  
 Pour plus d’informations, consultez l’article [Recordset : déclaration de la classe d’une Table (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).  
  
##  <a name="a-namedeletea--crecordsetdelete"></a><a name="delete"></a>CRecordset::Delete  
 Supprime l’enregistrement actif.  
  
```  
virtual void Delete();
```  
  
### <a name="remarks"></a>Notes  
 Après une suppression réussie, les données membres de champ du jeu d’enregistrements sont définies sur une valeur Null, et vous devez appeler explicitement une de le **déplacer** fonctions afin de déplacer l’enregistrement supprimé. Une fois que vous quittez l’enregistrement supprimé, il n’est pas possible d’y revenir. Si la source de données prend en charge les transactions, vous pouvez rendre le **supprimer** des appels, partie d’une transaction. Pour plus d’informations, consultez l’article [Transaction (ODBC)](../../data/odbc/transaction-odbc.md).  
  
> [!NOTE]
>  Si vous avez implémenté l’extraction de lignes en bloc, vous ne pouvez pas appeler **supprimer**. Cela entraîne un échec d’assertion. Bien que classe `CRecordset` ne fournit pas de mécanisme de mise à jour en bloc des lignes de données, vous pouvez écrire vos propres fonctions à l’aide de la fonction API ODBC **SQLSetPos**. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
> [!CAUTION]
>  Le jeu d’enregistrements doit être mis à jour et il doit y avoir un enregistrement valide dans le jeu d’enregistrements lorsque vous appelez **supprimer**; sinon, une erreur se produit. Par exemple, si vous supprimez un enregistrement, mais ne pas faire défiler à un nouvel enregistrement avant d’appeler **supprimer** , **supprimer** lève une [CDBException](../../mfc/reference/cdbexception-class.md).  
  
 Contrairement aux [AddNew](#addnew) et [modifier](#edit), un appel à **supprimer** n’est pas suivi par un appel à [mise à jour](#update). Si un **supprimer** appel échoue, les données des champs membres restent inchangées.  
  
### <a name="example"></a>Exemple  
 Cet exemple illustre un jeu d’enregistrements créé dans le cadre d’une fonction. L’exemple suppose l’existence de `m_dbCust`, une variable membre de type `CDatabase` déjà connecté à la source de données.  
  
 [!code-cpp[NVC_MFCDatabase&#18;](../../mfc/codesnippet/cpp/crecordset-class_2.cpp)]  
  
##  <a name="a-namedobulkfieldexchangea--crecordsetdobulkfieldexchange"></a><a name="dobulkfieldexchange"></a>CRecordset::DoBulkFieldExchange  
 Appelé pour échanger des lignes en bloc des données à partir de la source de données vers le recordset. Implémente en masse d’échange de champs d’enregistrements (RFX en bloc).  
  
```  
virtual void DoBulkFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Paramètres  
 `pFX`  
 Un pointeur vers un [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) objet. L’infrastructure sera déjà avoir configuré cet objet pour spécifier un contexte pour l’opération d’échange de champs.  
  
### <a name="remarks"></a>Notes  
 Lors de l’extraction de lignes en bloc est implémentée, le framework appelle cette fonction membre pour transférer automatiquement les données à partir de la source de données à l’objet recordset. `DoBulkFieldExchange`lie également les membres de données de paramètre, si une, les espaces réservés des paramètres dans la chaîne d’instruction SQL pour la sélection du jeu d’enregistrements.  
  
 Si l’extraction de lignes en bloc n’est pas implémentée, le framework appelle [DoFieldExchange](#dofieldexchange). Pour implémenter l’extraction de lignes en bloc, vous devez spécifier le `CRecordset::useMultiRowFetch` option de la `dwOptions` paramètre dans le [Open](#open) fonction membre.  
  
> [!NOTE]
> `DoBulkFieldExchange`est disponible uniquement si vous utilisez une classe dérivée de `CRecordset`. Si vous avez créé un objet recordset directement à partir de `CRecordset`, vous devez appeler le [GetFieldValue](#getfieldvalue) fonction membre pour récupérer des données.  
  
 RFX en bloc (RFX en bloc) est similaire à l’échange de champs d’enregistrements (RFX). Données sont automatiquement transférées à partir de la source de données à l’objet recordset. Toutefois, vous ne pouvez pas appeler `AddNew`, **modifier**, **supprimer**, ou **mise à jour** pour transférer les modifications apportées à la source de données. Classe `CRecordset` actuellement ne fournit pas un mécanisme de mise à jour en bloc des lignes de données ; Toutefois, vous pouvez écrire vos propres fonctions à l’aide de la fonction API ODBC **SQLSetPos**.  
  
 Notez que ClassWizard ne prend pas en charge RFX en bloc ; Par conséquent, vous devez substituer `DoBulkFieldExchange` manuellement en écrivant les appels aux fonctions RFX en bloc. Pour plus d’informations sur ces fonctions, consultez la rubrique [Record Field Exchange Functions](../../mfc/reference/record-field-exchange-functions.md).  
  
 Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Pour plus d’informations, consultez l’article [Record Field Exchange (RFX)](../../data/odbc/record-field-exchange-rfx.md).  
  
##  <a name="a-namedofieldexchangea--crecordsetdofieldexchange"></a><a name="dofieldexchange"></a>CRecordset::DoFieldExchange  
 Appelé pour échanger des données (dans les deux sens) entre les membres de données de champ du jeu d’enregistrements et l’enregistrement correspondant de la source de données. Implémente enregistre l’échange de champs (RFX).  
  
```  
virtual void DoFieldExchange(CFieldExchange* pFX);
```  
  
### <a name="parameters"></a>Paramètres  
 `pFX`  
 Un pointeur vers un [CFieldExchange](../../mfc/reference/cfieldexchange-class.md) objet. L’infrastructure sera déjà avoir configuré cet objet pour spécifier un contexte pour l’opération d’échange de champs.  
  
### <a name="remarks"></a>Remarques  
 Lors de l’extraction de lignes en bloc n’est pas implémentée, l’infrastructure appelle cette fonction membre pour échanger automatiquement les données entre les membres de données de champ de votre objet recordset et les colonnes correspondantes de l’enregistrement actif dans la source de données. `DoFieldExchange`lie également les membres de données de paramètre, si une, les espaces réservés des paramètres dans la chaîne d’instruction SQL pour la sélection du jeu d’enregistrements.  
  
 Si l’extraction de lignes en bloc est implémentée, le framework appelle [DoBulkFieldExchange](#dobulkfieldexchange). Pour implémenter l’extraction de lignes en bloc, vous devez spécifier le `CRecordset::useMultiRowFetch` option de la `dwOptions` paramètre dans le [Open](#open) fonction membre.  
  
> [!NOTE]
> `DoFieldExchange`est disponible uniquement si vous utilisez une classe dérivée de `CRecordset`. Si vous avez créé un objet recordset directement à partir de `CRecordset`, vous devez appeler le [GetFieldValue](#getfieldvalue) fonction membre pour récupérer des données.  
  
 L’échange de données de champ, appelées échange de champs d’enregistrements (RFX), fonctionne dans les deux sens : de membres de données de champ de l’objet recordset pour les champs de l’enregistrement de la source de données et de l’enregistrement sur la source de données à l’objet recordset.  
  
 La seule action que vous devez normalement suivre pour implémenter `DoFieldExchange` pour le jeu d’enregistrements dérivée classe consiste à créer la classe avec ClassWizard et spécifiez les noms et types de données des membres de données du champ. Vous pouvez également ajouter le code à ce que ClassWizard écrit pour spécifier les membres de données de paramètre ou de faire face à toutes les colonnes que vous liez dynamiquement. Pour plus d’informations, consultez l’article [Recordset : liaison dynamique des colonnes de données (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md).  
  
 Lorsque vous déclarez votre classe de recordset dérivée avec ClassWizard, l’Assistant écrit une substitution de `DoFieldExchange` , qui ressemble à l’exemple suivant :  
  
 [!code-cpp[NVC_MFCDatabase n °&19;](../../mfc/codesnippet/cpp/crecordset-class_3.cpp)]  
  
 Pour plus d’informations sur les fonctions RFX, consultez la rubrique [Record Field Exchange Functions](../../mfc/reference/record-field-exchange-functions.md).  
  
 Pour plus d’exemples et plus d’informations sur `DoFieldExchange`, consultez l’article [Record Field Exchange : fonctionnement de RFX](../../data/odbc/record-field-exchange-how-rfx-works.md). Pour obtenir des informations générales sur RFX, consultez l’article [Record Field Exchange](../../data/odbc/record-field-exchange-rfx.md).  
  
##  <a name="a-nameedita--crecordsetedit"></a><a name="edit"></a>CRecordset::Edit  
 Permet des modifications à l’enregistrement actif.  
  
```  
virtual void Edit();
```  
  
### <a name="remarks"></a>Remarques  
 Après avoir appelé **modifier**, vous pouvez modifier les données membres de champ en réinitialisant directement leurs valeurs. L’opération est terminée lorsque vous appelez ensuite la [mise à jour](#update) fonction membre pour enregistrer vos modifications sur la source de données.  
  
> [!NOTE]
>  Si vous avez implémenté l’extraction de lignes en bloc, vous ne pouvez pas appeler **modifier**. Cela entraîne un échec d’assertion. Bien que classe `CRecordset` ne fournit pas de mécanisme de mise à jour en bloc des lignes de données, vous pouvez écrire vos propres fonctions à l’aide de la fonction API ODBC **SQLSetPos**. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 **Modifier** enregistre les valeurs des membres de données du jeu d’enregistrements. Si vous appelez **modifier**, apporter des modifications, puis appelez **modifier** là encore, les valeurs de l’enregistrement sont restaurés qu’ils étaient avant le premier **modifier** appeler.  
  
 Dans certains cas, vous souhaiterez peut-être mettre à jour une colonne en le rendant Null (ne contenant aucune donnée). Pour ce faire, appelez [SetFieldNull](#setfieldnull) avec un paramètre de **TRUE** pour marquer le champ Null ; Ceci entraîne également la colonne à mettre à jour. Si vous souhaitez qu’un champ pour être écrites dans la source de données, même si sa valeur n’a pas changé, appelez [SetFieldDirty](#setfielddirty) avec un paramètre de **TRUE**. Cela fonctionne même si le champ a la valeur Null.  
  
 Si la source de données prend en charge les transactions, vous pouvez rendre le **modifier** des appels, partie d’une transaction. Notez que vous devez appeler [CDatabase::BeginTrans](../../mfc/reference/cdatabase-class.md#begintrans) avant d’appeler **modifier** et après le jeu d’enregistrements a été ouvert. Notez également que l’appel [CDatabase::CommitTrans](../../mfc/reference/cdatabase-class.md#committrans) n’est pas un substitut pour appeler la méthode **mise à jour** pour terminer le **modifier** opération. Pour plus d’informations sur les transactions, consultez la classe [CDatabase](../../mfc/reference/cdatabase-class.md).  
  
 Selon le mode de verrouillage en cours, l’enregistrement mis à jour peut être verrouillé par **modifier** jusqu'à ce que vous appeliez **mise à jour** ou accédez à un autre enregistrement, ou il peut être verrouillé que pendant la **modifier** appeler. Vous pouvez modifier le mode de verrouillage avec [SetLockingMode](#setlockingmode).  
  
 La valeur précédente de l’enregistrement actif est restaurée si vous accédez à un nouvel enregistrement avant d’appeler **mise à jour**. A `CDBException` est levée si vous appelez **modifier** pour un jeu d’enregistrements qui ne peut pas être mis à jour ou s’il n’existe aucun enregistrement en cours.  
  
 Pour plus d’informations, consultez les articles [Transaction (ODBC)](../../data/odbc/transaction-odbc.md) et [Recordset : verrouillage d’enregistrements (ODBC)](../../data/odbc/recordset-locking-records-odbc.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDatabase&#20;](../../mfc/codesnippet/cpp/crecordset-class_4.cpp)]  
  
##  <a name="a-nameflushresultseta--crecordsetflushresultset"></a><a name="flushresultset"></a>CRecordset::FlushResultSet  
 Récupère le jeu de résultats suivant d’une requête prédéfinie (procédure stockée), s’il existe plusieurs jeux de résultats.  
  
```  
BOOL FlushResultSet();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro s’il existe plusieurs jeux de résultats à récupérer ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler `FlushResultSet` uniquement lorsque vous avez complètement terminé avec le curseur sur le jeu de résultats actuel. Notez que lorsque vous récupérez le résultat suivant est défini en appelant `FlushResultSet`, le curseur n’est pas valide sur ce jeu de résultats, vous devez appeler le [MoveNext](#movenext) fonction membre après avoir appelé `FlushResultSet`.  
  
 Si une requête prédéfinie utilise un paramètre de sortie ou des paramètres d’entrée/sortie, vous devez appeler `FlushResultSet` jusqu'à ce qu’elle retourne `FALSE` (la valeur 0), afin d’obtenir ces valeurs de paramètre.  
  
 `FlushResultSet`appelle la fonction API ODBC `SQLMoreResults`. Si `SQLMoreResults` retourne `SQL_ERROR` ou `SQL_INVALID_HANDLE`, puis `FlushResultSet` lève une exception. Pour plus d’informations sur `SQLMoreResults`, consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Votre procédure stockée doit avoir lié les champs si vous souhaitez appeler `FlushResultSet`.  
  
### <a name="example"></a>Exemple  
 Le code suivant suppose que `COutParamRecordset` est un `CRecordset`-objet dérivé basé sur une requête prédéfinie avec un paramètre d’entrée et un paramètre de sortie et avoir plusieurs jeux de résultats. Remarque la structure de la [DoFieldExchange](#dofieldexchange) remplacer.  
  
 [!code-cpp[NVC_MFCDatabase n °&21;](../../mfc/codesnippet/cpp/crecordset-class_5.cpp)]  
  
 [!code-cpp[NVC_MFCDatabase&#22;](../../mfc/codesnippet/cpp/crecordset-class_6.cpp)]  
  
##  <a name="a-namegetbookmarka--crecordsetgetbookmark"></a><a name="getbookmark"></a>CRecordset::GetBookmark  
 Obtient la valeur du signet de l’enregistrement actuel.  
  
```  
void GetBookmark(CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>Paramètres  
 `varBookmark`  
 Une référence à un [CDBVariant](../../mfc/reference/cdbvariant-class.md) objet représentant le signet sur l’enregistrement actif.  
  
### <a name="remarks"></a>Remarques  
 Pour déterminer si les signets sont pris en charge sur le jeu d’enregistrements, appelez [CanBookmark](#canbookmark). Pour rendre les signets si elles sont prises en charge, vous devez configurer le **CRecordset::useBookmarks** option dans le `dwOptions` paramètre de la [Open](#open) fonction membre.  
  
> [!NOTE]
>  Si les signets sont pris en charge ou non disponible, l’appel `GetBookmark` entraîne une exception est levée. Les signets ne sont pas pris en charge sur les recordsets avant uniquement.  
  
 `GetBookmark`affecte la valeur du signet de l’enregistrement actuel à un `CDBVariant` objet. Pour revenir à cet enregistrement à tout moment après avoir déplacé vers un autre enregistrement, appelez [SetBookmark](#setbookmark) avec correspondants `CDBVariant` objet.  
  
> [!NOTE]
>  Après certaines opérations de jeu d’enregistrements, les signets peuvent ne plus être valides. Par exemple, si vous appelez `GetBookmark` suivie **Requery**, vous n’êtes peut-être pas en mesure de revenir à l’enregistrement avec `SetBookmark`. Appelez [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) pour vérifier si vous pouvez appeler en toute sécurité `SetBookmark`.  
  
 Pour plus d’informations sur les signets et de navigation de jeu d’enregistrements, consultez les articles [Recordset : signets et Positions absolues (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) et [Recordset : défilement (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="a-namegetdefaultconnecta--crecordsetgetdefaultconnect"></a><a name="getdefaultconnect"></a>CRecordset::GetDefaultConnect  
 Appelé pour obtenir la chaîne de connexion par défaut.  
  
```  
virtual CString GetDefaultConnect();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CString` qui contient la chaîne de connexion par défaut.  
  
### <a name="remarks"></a>Remarques  
 L’infrastructure appelle cette fonction membre pour obtenir la chaîne de connexion par défaut pour la source de données sur lequel repose le jeu d’enregistrements. ClassWizard implémente cette fonction pour vous en identifiant la source de données que vous utilisez dans ClassWizard pour obtenir des informations sur les tables et les colonnes. Il est probablement utile s’appuyer sur cette connexion par défaut lors du développement de votre application. Mais la connexion par défaut peut ne pas convenir pour les utilisateurs de votre application. Si tel est le cas, vous devez réimplémenter cette fonction, en ignorant les version de ClassWizard. Pour plus d’informations sur les chaînes de connexion, consultez l’article [Source de données (ODBC)](../../data/odbc/data-source-odbc.md).  
  
##  <a name="a-namegetdefaultsqla--crecordsetgetdefaultsql"></a><a name="getdefaultsql"></a>CRecordset::GetDefaultSQL  
 Appelé pour obtenir la chaîne SQL par défaut à exécuter.  
  
```  
virtual CString GetDefaultSQL();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CString` qui contient l’instruction SQL par défaut.  
  
### <a name="remarks"></a>Notes  
 L’infrastructure appelle cette fonction membre pour obtenir l’instruction SQL par défaut sur lequel repose le jeu d’enregistrements. Cela peut être un nom de table ou SQL **sélectionnez** instruction.  
  
 Vous définissez indirectement l’instruction SQL par défaut en déclarant de la classe de recordset avec ClassWizard et ClassWizard effectue cette tâche pour vous.  
  
 Si vous avez besoin de la chaîne de l’instruction SQL pour votre propre usage, appelez `GetSQL`, qui retourne l’instruction SQL utilisée pour sélectionner les enregistrements du jeu d’enregistrements lorsqu’il a été ouvert. Vous pouvez modifier la chaîne SQL par défaut dans la substitution de votre classe de `GetDefaultSQL`. Par exemple, vous pouvez spécifier un appel à une requête prédéfinie en utilisant un **appeler** instruction. (Notez, cependant, que si vous modifiez `GetDefaultSQL`, vous devez également modifier `m_nFields` correspondant au nombre de colonnes dans la source de données.)  
  
 Pour plus d’informations, consultez l’article [Recordset : déclaration de la classe d’une Table (ODBC)](../../data/odbc/recordset-declaring-a-class-for-a-table-odbc.md).  
  
> [!CAUTION]
>  Le nom de la table est vide si l’infrastructure n’a pas pu identifier un nom de table, si plusieurs noms de tables ont été fournies, ou si un **appeler** instruction n’a pas pu être interprétée. Notez que lorsque vous utilisez un **appeler** instruction, vous ne devez pas insérer d’espace entre l’accolade et **appeler** (mot clé), ni doit insérer d’espaces avant l’accolade ou avant le **sélectionnez** mot clé dans une **sélectionnez** instruction.  
  
##  <a name="a-namegetfieldvaluea--crecordsetgetfieldvalue"></a><a name="getfieldvalue"></a>CRecordset::GetFieldValue  
 Récupère les données du champ dans l’enregistrement actif.  
  
```  
void GetFieldValue(
    LPCTSTR lpszName,  
    CDBVariant& varValue,  
    short nFieldType = DEFAULT_FIELD_TYPE);

 
void GetFieldValue(
    short nIndex,  
    CDBVariant& varValue,  
    short nFieldType = DEFAULT_FIELD_TYPE);

 
void GetFieldValue(
    short nIndex,  
    CStringA& strValue);

 
void GetFieldValue(
    short nIndex,  
    CStringW& strValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Le nom d’un champ.  
  
 *varValu*e  
 Une référence à un [CDBVariant](../../mfc/reference/cdbvariant-class.md) objet qui stocke la valeur du champ.  
  
 `nFieldType`  
 Le type de données ODBC C du champ. À l’aide de la valeur par défaut, **DEFAULT_FIELD_TYPE**, force `GetFieldValue` pour déterminer le type de données C à partir du type de données SQL, selon le tableau suivant. Sinon, vous pouvez spécifier les données taper directement ou choisissez un type de données compatible. par exemple, vous pouvez stocker n’importe quel type de données en **SQL_C_CHAR**.  
  
|Type de données C|Type de données SQL|  
|-----------------|-------------------|  
|**SQL_C_BIT**|**SQL_BIT**|  
|**SQL_C_UTINYINT**|**SQL_TINYINT**|  
|**SQL_C_SSHORT**|**SQL_SMALLINT**|  
|**SQL_C_SLONG**|**SQL_INTEGER**|  
|**SQL_C_FLOAT**|**SQL_REAL**|  
|**SQL_C_DOUBLE**|**SQL_FLOATSQL_DOUBLE**|  
|**SQL_C_TIMESTAMP**|**SQL_DATESQL_TIMESQL_TIMESTAMP**|  
|**SQL_C_CHAR**|**SQL_NUMERICSQL_DECIMALSQL_BIGINTSQL_CHARSQL_VARCHARSQL_LONGVARCHAR**|  
|**SQL_C_BINARY**|**SQL_BINARYSQL_VARBINARYSQL_LONGVARBINARY**|  
  
 Pour plus d’informations sur les types de données ODBC, consultez les rubriques « Types de données SQL » et « Types de données C » dans l’annexe D de la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 `nIndex`  
 Index de base zéro du champ.  
  
 `strValue`  
 Une référence à un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet qui stocke la valeur du champ est converti en texte, quel que soit le type de données.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez rechercher un champ par nom ou par index. Vous pouvez stocker la valeur du champ, que ce soit une `CDBVariant` objet ou un `CString` objet.  
  
 Si vous avez implémenté l’extraction de lignes en bloc, l’enregistrement en cours est toujours positionnée sur le premier enregistrement dans un ensemble de lignes. Pour utiliser `GetFieldValue` sur un enregistrement dans un ensemble de lignes donné, vous devez d’abord appeler la [SetRowsetCursorPosition](#setrowsetcursorposition) fonction membre pour déplacer le curseur sur la ligne souhaitée dans cet ensemble de lignes. Appelez ensuite `GetFieldValue` pour cette ligne. Pour implémenter l’extraction de lignes en bloc, vous devez spécifier le `CRecordset::useMultiRowFetch` option de la `dwOptions` paramètre dans le [Open](#open) fonction membre.  
  
 Vous pouvez utiliser `GetFieldValue` pour extraire des champs dynamiquement au moment de l’exécution, plutôt que de les lier statiquement au moment du design. Par exemple, si vous avez déclaré un objet recordset directement à partir de `CRecordset`, vous devez utiliser `GetFieldValue` pour récupérer les données de champ, échange de champs d’enregistrements (RFX) ou RFX en bloc (RFX en bloc), n’est pas implémentée.  
  
> [!NOTE]
>  Si vous déclarez un objet recordset sans dériver `CRecordset`, n’ont pas de la bibliothèque de curseurs ODBC chargé. La bibliothèque de curseurs nécessite que le jeu d’enregistrements ont au moins une colonne dépendante ; Toutefois, lorsque vous utilisez `CRecordset` directement, les colonnes sont liées. Les fonctions membres [CDatabase::OpenEx](../../mfc/reference/cdatabase-class.md#openex) et [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) contrôler si la bibliothèque de curseurs sera chargée.  
  
 `GetFieldValue`appelle la fonction API ODBC **SQLGetData**. Si votre pilote renvoie la valeur **SQL_NO_TOTAL** pour la longueur réelle de la valeur du champ, `GetFieldValue` lève une exception. Pour plus d’informations sur **SQLGetData**, consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 L’exemple de code suivant illustre des appels à `GetFieldValue` pour un objet recordset déclaré directement à partir de `CRecordset`.  
  
 [!code-cpp[NVC_MFCDatabase n °&23;](../../mfc/codesnippet/cpp/crecordset-class_7.cpp)]  
  
> [!NOTE]
>  Contrairement à la classe DAO `CDaoRecordset`, `CRecordset` n’a pas une `SetFieldValue` fonction membre. Si vous créez un objet directement à partir de `CRecordset`, il est effectivement en lecture seule.  
  
 Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="a-namegetodbcfieldcounta--crecordsetgetodbcfieldcount"></a><a name="getodbcfieldcount"></a>CRecordset::GetODBCFieldCount  
 Récupère le nombre total de champs dans l’objet recordset.  
  
```  
short GetODBCFieldCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de champs dans le jeu d’enregistrements.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations sur la création de jeux d’enregistrements, consultez l’article [Recordset : création et fermeture de Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
##  <a name="a-namegetodbcfieldinfoa--crecordsetgetodbcfieldinfo"></a><a name="getodbcfieldinfo"></a>CRecordset::GetODBCFieldInfo  
 Obtient des informations sur les champs dans le jeu d’enregistrements.  
  
```  
void GetODBCFieldInfo(
    LPCTSTR lpszName,  
    CODBCFieldInfo& fieldinfo);

 
void GetODBCFieldInfo(
    short nIndex,  
    CODBCFieldInfo& fieldinfo);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Le nom d’un champ.  
  
 `fieldinfo`  
 Une référence à un `CODBCFieldInfo` structure.  
  
 `nIndex`  
 Index de base zéro du champ.  
  
### <a name="remarks"></a>Notes  
 Une version de la fonction vous permet de rechercher un champ par nom. L’autre version vous permet de rechercher un champ par index.  
  
 Pour obtenir une description sur les informations renvoyées, consultez la [CODBCFieldInfo](../../mfc/reference/codbcfieldinfo-structure.md) structure.  
  
 Pour plus d’informations sur la création de jeux d’enregistrements, consultez l’article [Recordset : création et fermeture de Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
##  <a name="a-namegetrecordcounta--crecordsetgetrecordcount"></a><a name="getrecordcount"></a>CRecordset::GetRecordCount  
 Détermine la taille de l’objet recordset.  
  
```  
long GetRecordCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre d’enregistrements dans l’objet recordset. 0 si l’objet recordset ne contient aucun enregistrement ; ou -1 si le nombre d’enregistrements ne peut pas être déterminé.  
  
### <a name="remarks"></a>Notes  
  
> [!CAUTION]
>  Le nombre d’enregistrements est conservé comme une « limite supérieure, « l’enregistrement le plus élevé numérotées encore vu que l’utilisateur parcourt les enregistrements. Le nombre total d’enregistrements est appelée uniquement une fois que l’utilisateur a déplacé au-delà du dernier enregistrement. Pour des raisons de performances, le nombre n’est pas actualisé lorsque vous appelez `MoveLast`. Pour compter les enregistrements vous-même, appelez `MoveNext` à plusieurs reprises jusqu'à ce que `IsEOF` retourne zéro. Ajout d’un enregistrement via **CRecordset:AddNew** et **mise à jour** augmente le nombre ; la suppression d’un enregistrement via `CRecordset::Delete` diminue le nombre.  
  
##  <a name="a-namegetrowsetsizea--crecordsetgetrowsetsize"></a><a name="getrowsetsize"></a>CRecordset::GetRowsetSize  
 Obtient le paramètre actuel pour le nombre de lignes que vous souhaitez récupérer lors d’une extraction donnée.  
  
```  
DWORD GetRowsetSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de lignes à récupérer lors d’une extraction donnée.  
  
### <a name="remarks"></a>Notes  
 Si vous utilisez l’extraction de lignes en bloc, la taille par défaut lors de l’ouverture de l’objet recordset est 25 ; dans le cas contraire, il est 1.  
  
 Pour implémenter l’extraction de lignes en bloc, vous devez spécifier le `CRecordset::useMultiRowFetch` option dans le `dwOptions` paramètre de la [Open](#open) fonction membre. Pour modifier le paramètre de la taille de l’ensemble de lignes, appelez [SetRowsetSize](#setrowsetsize).  
  
 Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="a-namegetrowsfetcheda--crecordsetgetrowsfetched"></a><a name="getrowsfetched"></a>CRecordset::GetRowsFetched  
 Détermine le nombre d’enregistrements ont été réellement récupéré après une extraction.  
  
```  
DWORD GetRowsFetched() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de lignes récupérées à partir de la source de données après une extraction donnée.  
  
### <a name="remarks"></a>Remarques  
 Cela est utile lorsque vous avez implémenté l’extraction de lignes en bloc. La taille de l’ensemble de lignes indique généralement le nombre de lignes est récupéré à partir d’une instruction fetch ; Toutefois, le nombre total de lignes dans le jeu d’enregistrements affecte également le nombre de lignes sera extrait dans un ensemble de lignes. Par exemple, si votre jeu d’enregistrements a 10 enregistrements avec un paramètre de taille d’ensemble de lignes de 4, puis boucler dans le jeu d’enregistrements en appelant `MoveNext` entraîne l’ensemble de lignes final des enregistrements seulement 2.  
  
 Pour implémenter l’extraction de lignes en bloc, vous devez spécifier le `CRecordset::useMultiRowFetch` option dans le `dwOptions` paramètre de la [Open](#open) fonction membre. Pour spécifier la taille de l’ensemble de lignes, appelez [SetRowsetSize](#setrowsetsize).  
  
 Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDatabase&#24;](../../mfc/codesnippet/cpp/crecordset-class_8.cpp)]  
  
##  <a name="a-namegetrowstatusa--crecordsetgetrowstatus"></a><a name="getrowstatus"></a>CRecordset::GetRowStatus  
 Obtient l’état d’une ligne dans l’ensemble de lignes en cours.  
  
```  
WORD GetRowStatus(WORD wRow) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `wRow`  
 Basée sur une position d’une ligne dans l’ensemble de lignes en cours. Cette valeur peut varier de 1 à la taille de l’ensemble de lignes.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur d’état de la ligne. Pour plus d'informations, consultez Notes.  
  
### <a name="remarks"></a>Notes  
 `GetRowStatus`Retourne une valeur qui indique une modification de statut à la ligne depuis le dernier extraites de la source de données, ou qui aucune ligne correspondant à `wRow` a été extraite. Le tableau ci-dessous répertorie les valeurs de retour possibles.  
  
|Valeur d’état|Description|  
|------------------|-----------------|  
|`SQL_ROW_SUCCESS`|La ligne est inchangée.|  
|`SQL_ROW_UPDATED`|La ligne a été mise à jour.|  
|`SQL_ROW_DELETED`|La ligne a été supprimée.|  
|`SQL_ROW_ADDED`|La ligne a été ajoutée.|  
|`SQL_ROW_ERROR`|La ligne n’est pas récupérables en raison d’une erreur.|  
|`SQL_ROW_NOROW`|Il n’y a aucune ligne qui correspond à `wRow`.|  
  
 Pour plus d’informations, consultez la fonction d’API ODBC **SQLExtendedFetch** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetstatusa--crecordsetgetstatus"></a><a name="getstatus"></a>CRecordset::GetStatus  
 Détermine l’index de l’enregistrement actif dans le jeu d’enregistrements et si le dernier enregistrement est apparue.  
  
```  
void GetStatus(CRecordsetStatus& rStatus) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `rStatus`  
 Une référence à un **CRecordsetStatus** objet. Pour plus d'informations, consultez la section Notes.  
  
### <a name="remarks"></a>Remarques  
 `CRecordset`tente d’effectuer le suivi de l’index, mais dans certaines circonstances cela ne peut pas être possible. Consultez la page [GetRecordCount](#getrecordcount) pour obtenir une explication.  
  
 Le **CRecordsetStatus** structure a la forme suivante :  
  
 `struct CRecordsetStatus`  
  
 `{`  
  
 `long m_lCurrentRecord;`  
  
 `BOOL m_bRecordCountFinal;`  
  
 `};`  
  
 Les deux membres de **CRecordsetStatus** ont les significations suivantes :  
  
- **m_lCurrentRecord** contient l’index de base zéro de l’enregistrement actif dans le jeu d’enregistrements, s’il est connu. Si l’index ne peut pas être déterminé, ce membre contient **AFX_CURRENT_RECORD_UNDEFINED** – (2). Si `IsBOF` est **TRUE** (vider le jeu d’enregistrements ou tentative de défilement avant le premier enregistrement), puis **m_lCurrentRecord** a **AFX_CURRENT_RECORD_BOF** (-1). Si sur le premier enregistrement, puis elle est définie sur 0, ensuite enregistrer 1 et ainsi de suite.  
  
- **m_bRecordCountFinal** Nonzero si le nombre total d’enregistrements dans le jeu d’enregistrements a été déterminé. Généralement cela doit être accompli en commençant au début du jeu d’enregistrements et en appelant `MoveNext` jusqu'à ce que `IsEOF` retourne zéro. Si ce membre est égal à zéro, l’enregistrement de nombre tel que retourné par `GetRecordCount`, si pas –&1;, n'est que le nombre « limite supérieure » des enregistrements.  
  
##  <a name="a-namegetsqla--crecordsetgetsql"></a><a name="getsql"></a>CRecordset::GetSQL  
 Appelez cette fonction membre pour obtenir l’instruction SQL qui a été utilisée pour sélectionner les enregistrements du jeu d’enregistrements lorsqu’il a été ouvert.  
  
```  
const CString& GetSQL() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **const** une référence vers un `CString` qui contient l’instruction SQL.  
  
### <a name="remarks"></a>Remarques  
 Il s’agit généralement d’un SQL **sélectionnez** instruction. La chaîne retournée par `GetSQL` est en lecture seule.  
  
 La chaîne retournée par `GetSQL` est généralement différent à partir de n’importe quelle chaîne que vous avez peut-être passé au jeu d’enregistrements dans la `lpszSQL` paramètre à la **Open** fonction membre. C’est parce que l’objet recordset construit l’instruction SQL complète en fonction de ce que vous avez transmis à **Open**, ce que vous avez spécifié avec ClassWizard, ce que vous avez spécifié dans le **m_strFilter** et `m_strSort` les membres de données et tous les paramètres que vous avez spécifié. Pour plus d’informations sur la façon dont le jeu d’enregistrements construit cette instruction SQL, consultez l’article [Recordset : sélection d’enregistrements (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
> [!NOTE]
>  Appelez cette fonction membre uniquement après avoir appelé [ouvrir](#open).  
  
##  <a name="a-namegettablenamea--crecordsetgettablename"></a><a name="gettablename"></a>CRecordset::GetTableName  
 Obtient le nom de la table SQL sur laquelle repose la requête du recordset.  
  
```  
const CString& GetTableName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **const** une référence vers un `CString` qui contient la table name, si le jeu d’enregistrements est basé sur une table ; sinon, une chaîne vide.  
  
### <a name="remarks"></a>Notes  
 `GetTableName`est valide uniquement si le jeu d’enregistrements est basé sur une table, pas une jointure de plusieurs tables ou d’une requête prédéfinie (procédure stockée). Le nom est en lecture seule.  
  
> [!NOTE]
>  Appelez cette fonction membre uniquement après avoir appelé [ouvrir](#open).  
  
##  <a name="a-nameisbofa--crecordsetisbof"></a><a name="isbof"></a>CRecordset::IsBOF  
 Retourne zéro si le jeu d’enregistrements a été positionné avant le premier enregistrement. Il n’existe aucun enregistrement actif.  
  
```  
BOOL IsBOF() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le jeu d’enregistrements ne contient aucun enregistrement ou si vous avez fait défiler vers l’arrière avant le premier enregistrement ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction membre avant que vous accédez à partir de l’enregistrement à enregistrement pour savoir si vous avez suivi avant le premier enregistrement de l’objet recordset. Vous pouvez également utiliser `IsBOF` avec `IsEOF` pour déterminer si l’objet recordset contient des enregistrements ou est vide. Immédiatement après l’appel de **Open**, si le jeu d’enregistrements ne contient aucun enregistrement, `IsBOF` retourne zéro. Lorsque vous ouvrez un objet recordset qui contient au moins un enregistrement, le premier enregistrement est l’enregistrement actif et `IsBOF` renvoie la valeur 0.  
  
 Si le premier enregistrement est l’enregistrement actif et que vous appelez `MovePrev`, `IsBOF` retournera ensuite différente de zéro. Si `IsBOF` retourne zéro et que vous appelez `MovePrev`, une erreur se produit. Si `IsBOF` retourne zéro, l’enregistrement actif n’est pas défini, et toute action qui nécessite un enregistrement actuel entraînera une erreur.  
  
### <a name="example"></a>Exemple  
 Cet exemple utilise `IsBOF` et `IsEOF` pour détecter les limites d’un jeu d’enregistrements que le code défile dans le jeu d’enregistrements dans les deux sens.  
  
 [!code-cpp[NVC_MFCDatabase&#25;](../../mfc/codesnippet/cpp/crecordset-class_9.cpp)]  
  
##  <a name="a-nameisdeleteda--crecordsetisdeleted"></a><a name="isdeleted"></a>CRecordset::IsDeleted  
 Détermine si l’enregistrement actuel a été supprimé.  
  
```  
BOOL IsDeleted() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le jeu d’enregistrements est positionné sur un enregistrement supprimé. sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Si vous accédez à un enregistrement et `IsDeleted` retourne **TRUE** (différente de zéro), puis vous devez accéder à un autre enregistrement avant d’effectuer toute autre opération de jeu d’enregistrements.  
  
 Le résultat de `IsDeleted` dépend de nombreux facteurs, tels que le type de votre jeu d’enregistrements, si le jeu d’enregistrements est modifiable, si vous avez spécifié le **CRecordset::skipDeletedRecords** option lorsque vous avez ouvert le jeu d’enregistrements, si les jeux de pilotes des enregistrements supprimés, et s’il existe plusieurs utilisateurs.  
  
 Pour plus d’informations sur **CRecordset::skipDeletedRecords** et le pilote de compression, consultez la [Open](#open) fonction membre.  
  
> [!NOTE]
>  Si vous avez implémenté l’extraction de lignes en bloc, vous ne devez pas appeler `IsDeleted`. Au lieu de cela, appelez le [GetRowStatus](#getrowstatus) fonction membre. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="a-nameiseofa--crecordsetiseof"></a><a name="iseof"></a>CRecordset::IsEOF  
 Retourne zéro si le jeu d’enregistrements a été positionné après le dernier enregistrement. Il n’existe aucun enregistrement actif.  
  
```  
BOOL IsEOF() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le jeu d’enregistrements ne contient aucun enregistrement ou si vous avez déplacé au-delà du dernier enregistrement ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction membre que vous accédez à partir de l’enregistrement à enregistrement pour savoir si vous avez dépassé le dernier enregistrement du jeu d’enregistrements. Vous pouvez également utiliser `IsEOF` pour déterminer si l’objet recordset contient des enregistrements ou est vide. Immédiatement après l’appel de **Open**, si le jeu d’enregistrements ne contient aucun enregistrement, `IsEOF` retourne zéro. Lorsque vous ouvrez un objet recordset qui contient au moins un enregistrement, le premier enregistrement est l’enregistrement actif et `IsEOF` renvoie la valeur 0.  
  
 Si le dernier enregistrement est l’enregistrement actif lorsque vous appelez `MoveNext`, `IsEOF` retournera ensuite différente de zéro. Si `IsEOF` retourne zéro et que vous appelez `MoveNext`, une erreur se produit. Si `IsEOF` retourne zéro, l’enregistrement actif n’est pas défini, et toute action qui nécessite un enregistrement actuel entraînera une erreur.  
  
### <a name="example"></a>Exemple  
 Consultez l’exemple de [IsBOF](#isbof).  
  
##  <a name="a-nameisfielddirtya--crecordsetisfielddirty"></a><a name="isfielddirty"></a>CRecordset::IsFieldDirty  
 Détermine si le membre de données du champ spécifié a été modifié depuis [modifier](#edit) ou [AddNew](#addnew) a été appelée.  
  
```  
BOOL IsFieldDirty(void* pv);
```  
  
### <a name="parameters"></a>Paramètres  
 `pv`  
 Un pointeur vers le membre de données du champ dont vous souhaitez vérifier, l’état ou **NULL** pour déterminer si les champs sont incorrectes.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le membre de données du champ spécifié a changé depuis l’appel `AddNew` ou **modifier**; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Les données de tous les membres de données de champ incorrectes seront transférées à l’enregistrement de la source de données lors de l’enregistrement actif est mis à jour par un appel à la [mise à jour](#update) fonction membre de `CRecordset` (après un appel à **modifier** ou `AddNew`).  
  
> [!NOTE]
>  Cette fonction membre n’est pas applicable sur les jeux d’enregistrements qui est à l’aide de l’extraction de lignes en bloc. Si vous avez implémenté l’extraction de lignes en bloc, puis `IsFieldDirty` renvoie toujours **FALSE** et entraîne un échec d’assertion. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Appel de `IsFieldDirty` rétablira les effets des appels à précédentes [SetFieldDirty](#setfielddirty) étant donné que l’état du champ modifié est réévaluée. Dans la `AddNew` cas, si la valeur du champ est différente de la valeur null de pseudo, l’état du champ a la valeur incorrecte. Dans le **modifier** cas, si la valeur du champ est différente de la valeur mise en cache, puis l’état du champ est modifié.  
  
 `IsFieldDirty`est implémenté via [DoFieldExchange](#dofieldexchange).  
  
 Pour plus d’informations sur l’indicateur de changement, consultez l’article [Recordset : sélection d’enregistrements (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
##  <a name="a-nameisfieldnulla--crecordsetisfieldnull"></a><a name="isfieldnull"></a>CRecordset::IsFieldNull  
 Retourne zéro si le champ spécifié dans l’enregistrement actif est Null (n’a aucune valeur).  
  
```  
BOOL IsFieldNull(void* pv);
```  
  
### <a name="parameters"></a>Paramètres  
 `pv`  
 Un pointeur vers le membre de données du champ dont vous souhaitez vérifier, l’état ou **NULL** pour déterminer si les champs sont Null.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le membre de données du champ spécifié est marqué avec la valeur Null ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction membre pour déterminer si le membre de données de champ spécifié d’un objet recordset a été marqué comme étant Null. (Dans la terminologie de base de données, Null donne « aucune valeur » et n’est pas le même que **NULL** en C++.) Si un membre de données de champ est marqué avec la valeur Null, il est interprété comme une colonne de l’enregistrement en cours pour lequel il n’existe aucune valeur.  
  
> [!NOTE]
>  Cette fonction membre n’est pas applicable sur les jeux d’enregistrements qui est à l’aide de l’extraction de lignes en bloc. Si vous avez implémenté l’extraction de lignes en bloc, puis `IsFieldNull` renvoie toujours **FALSE** et entraîne un échec d’assertion. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 `IsFieldNull`est implémenté via [DoFieldExchange](#dofieldexchange).  
  
##  <a name="a-nameisfieldnullablea--crecordsetisfieldnullable"></a><a name="isfieldnullable"></a>CRecordset::IsFieldNullable  
 Retourne zéro si le champ spécifié dans l’enregistrement actif peut être défini avec la valeur Null (n’ayant aucune valeur).  
  
```  
BOOL IsFieldNullable(void* pv);
```  
  
### <a name="parameters"></a>Paramètres  
 `pv`  
 Un pointeur vers le membre de données du champ dont vous souhaitez vérifier, l’état ou **NULL** pour déterminer si les champs peuvent être définies sur une valeur Null.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction membre pour déterminer si le membre de données du champ spécifié est « nullable » (peut être une valeur Null ; C++ **NULL** n’est pas identique à Null, ce qui, dans la terminologie de base de données, signifie « n’avoir aucune valeur »).  
  
> [!NOTE]
>  Si vous avez implémenté l’extraction de lignes en bloc, vous ne pouvez pas appeler `IsFieldNullable`. Au lieu de cela, appelez le [GetODBCFieldInfo au](#getodbcfieldinfo) fonction membre pour déterminer si un champ peut être défini à une valeur Null. Notez que vous pouvez toujours appeler `GetODBCFieldInfo`, indépendamment de si vous avez implémenté l’extraction de lignes en bloc. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Un champ qui ne peut pas être Null doit avoir une valeur. Si vous essayez de définir un tel champ null lors de l’ajout ou la mise à jour d’un enregistrement, la source de données rejette l’ajout ou la mise à jour, et [mise à jour](#update) lève une exception. L’exception se produit lorsque vous appelez **mise à jour**, pas lorsque vous appelez [SetFieldNull](#setfieldnull).  
  
 À l’aide de **NULL** pour le premier argument de la fonction s’applique uniquement à la fonction **outputColumn** ne champs pas **param** champs. Par exemple, l’appel  
  
 [!code-cpp[NVC_MFCDatabase&#26;](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 définit uniquement **outputColumn** champs **NULL**; **param** champs ne seront pas affectées.  
  
 Pour travailler sur **param** champs, vous devez fournir l’adresse réelle de l’individu **param** à utiliser, tel que :  
  
 [!code-cpp[27 NVC_MFCDatabase](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Cela signifie que vous ne pouvez pas définir toutes les **param** champs **NULL**, comme vous pouvez le faire avec **outputColumn** champs.  
  
 `IsFieldNullable`est implémenté via [DoFieldExchange](#dofieldexchange).  
  
##  <a name="a-nameisopena--crecordsetisopen"></a><a name="isopen"></a>CRecordset::IsOpen  
 Détermine si l’objet recordset est déjà ouvert.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’objet recordset [Open](#open) ou [Requery](#requery) fonction membre a été précédemment appelée et le jeu d’enregistrements n’a pas été fermée ; sinon, 0.  
  
##  <a name="a-namemhstmta--crecordsetmhstmt"></a><a name="m_hstmt"></a>CRecordset::m_hstmt  
 Contient un handle vers la structure de données instruction ODBC, de type **HSTMT**, associés à l’objet recordset.  
  
### <a name="remarks"></a>Remarques  
 Chaque requête à une source de données ODBC est associé un **HSTMT**.  
  
> [!CAUTION]
>  N’utilisez pas **m_hstmt** avant [Open](#open) a été appelée.  
  
 Normalement, vous n’avez pas besoin d’accéder à la **HSTMT** directement, mais vous pouvez en avoir besoin pour l’exécution directe des instructions SQL. Le `ExecuteSQL` fonction membre de classe `CDatabase` fournit un exemple d’utilisation de **m_hstmt**.  
  
##  <a name="a-namemnfieldsa--crecordsetmnfields"></a><a name="m_nfields"></a>CRecordset::m_nFields  
 Contient le nombre de membres de données de champ dans la classe de recordset. Autrement dit, le nombre de colonnes sélectionnées par le jeu d’enregistrements à partir de la source de données.  
  
### <a name="remarks"></a>Remarques  
 Le constructeur de la classe de recordset doit initialiser `m_nFields` avec le nombre correct. Si vous n’avez pas implémenté l’extraction de lignes en bloc, ClassWizard écrit cette initialisation pour vous lorsque vous l’utilisez pour déclarer la classe de recordset. Vous pouvez également l’écrire manuellement.  
  
 L’infrastructure utilise ce numéro pour gérer l’interaction entre les membres de données de champ et les colonnes correspondantes de l’enregistrement actif dans la source de données.  
  
> [!CAUTION]
>  Ce numéro doit correspondre au nombre de « colonnes de sortie » inscrit dans `DoFieldExchange` ou `DoBulkFieldExchange` après un appel à [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) avec le paramètre **CFieldExchange::outputColumn**.  
  
 Vous pouvez lier des colonnes dynamiquement, comme expliqué dans l’article « Recordset : dynamiquement les colonnes de données de liaison. » Si vous procédez ainsi, vous devez augmenter le nombre de `m_nFields` pour refléter le nombre de RFX ou RFX en bloc des appels dans votre `DoFieldExchange` ou `DoBulkFieldExchange` fonction membre pour les colonnes liées dynamiquement.  
  
 Pour plus d’informations, consultez les articles [Recordset : liaison dynamique des colonnes de données (ODBC)](../../data/odbc/recordset-dynamically-binding-data-columns-odbc.md) et [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Exemple  
 Consultez l’article [Record Field Exchange : utilisation de RFX](../../data/odbc/record-field-exchange-using-rfx.md).  
  
##  <a name="a-namemnparamsa--crecordsetmnparams"></a><a name="m_nparams"></a>CRecordset::m_nParams  
 Contient le nombre de membres de données de paramètre dans la classe de recordset. Autrement dit, le nombre de paramètres transmis avec la requête du recordset.  
  
### <a name="remarks"></a>Remarques  
 Si votre classe de recordset possède des membres de données de paramètre, le constructeur de la classe doit initialiser `m_nParams` avec le nombre correct. La valeur de `m_nParams` est 0 par défaut. Si vous ajoutez des membres de données de paramètre (qui vous devez le faire manuellement) vous devez également ajouter manuellement une initialisation dans le constructeur de classe pour refléter le nombre de paramètres (qui doit être au moins aussi grand que le nombre de « espaces réservés dans vos **m_strFilter** ou `m_strSort` chaîne).  
  
 L’infrastructure utilise ce numéro lorsqu’il ajuste la requête du recordset.  
  
> [!CAUTION]
>  Ce numéro doit correspondre au nombre de « param » est enregistré dans `DoFieldExchange` ou `DoBulkFieldExchange` après un appel à [SetFieldType](../../mfc/reference/cfieldexchange-class.md#setfieldtype) avec une valeur de paramètre **CFieldExchange::inputParam**, **CFieldExchange::param**, **CFieldExchange::outputParam**, ou **CFieldExchange::inoutParam**.  
  
### <a name="example"></a>Exemple  
  Consultez les articles [Recordset : paramétrage d’un Recordset (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md) et [Record Field Exchange : utilisation de RFX](../../data/odbc/record-field-exchange-using-rfx.md).  
  
##  <a name="a-namempdatabasea--crecordsetmpdatabase"></a><a name="m_pdatabase"></a>CRecordset::m_pDatabase  
 Contient un pointeur vers le `CDatabase` objet via lequel le jeu d’enregistrements est connecté à une source de données.  
  
### <a name="remarks"></a>Notes  
 Cette variable est définie de deux manières. En règle générale, vous passez un pointeur à un socket déjà `CDatabase` de l’objet lorsque vous construisez l’objet recordset. Si vous transmettez **NULL** au lieu de cela, `CRecordset` crée un `CDatabase` de l’objet pour vous et le connecte. Dans les deux cas, `CRecordset` stocke le pointeur dans cette variable.  
  
 Normalement vous serez directement inutile d’utiliser le pointeur stocké dans **m_pDatabase**. Si vous écrivez vos propres extensions à `CRecordset`, toutefois, vous devrez peut-être utiliser le pointeur. Par exemple, vous devrez peut-être le pointeur si vous levez vos propres `CDBException`s. Ou vous pouvez en avoir besoin si vous devez faire quelque chose à l’aide de la même `CDatabase` objet, telles que l’exécution des transactions, la définition de délais, ou en appelant le `ExecuteSQL` fonction membre de classe `CDatabase` pour exécuter directement des instructions SQL.  
  
##  <a name="a-namemstrfiltera--crecordsetmstrfilter"></a><a name="m_strfilter"></a>CRecordset::m_strFilter  
 Après avoir construit l’objet recordset, mais avant d’appeler sa **Open** membre de fonction, ce membre de données permet de stocker un `CString` contenant SQL **où** clause.  
  
### <a name="remarks"></a>Remarques  
 Le jeu d’enregistrements utilise la chaîne pour contraindre (ou) les enregistrements qu’il sélectionne au cours de la **Open** ou **Requery** appeler. Cela est utile pour sélectionner un sous-ensemble d’enregistrements, tels que « tous les vendeurs en fonction de Californie » (« état = CA »). La syntaxe ODBC SQL pour un **où** clause est  
  
 `WHERE search-condition`  
  
 Notez que vous n’incluez pas le **où** mot clé dans votre chaîne. Fournit l’infrastructure.  
  
 Vous pouvez également paramétrer la chaîne de filtre en plaçant des « espaces réservés, déclarer un membre de données dans votre classe pour chaque espace réservé et en passant les paramètres du jeu d’enregistrements au moment de l’exécution. Cela vous permet de construire le filtre au moment de l’exécution. Pour plus d’informations, consultez l’article [Recordset : paramétrage d’un Recordset (ODBC)](../../data/odbc/recordset-parameterizing-a-recordset-odbc.md).  
  
 Pour plus d’informations sur SQL **où** clauses, consultez l’article [SQL](../../data/odbc/sql.md). Pour plus d’informations sur la sélection et filtrage d’enregistrements, consultez l’article [Recordset : filtrage d’enregistrements (ODBC)](../../data/odbc/recordset-filtering-records-odbc.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[30 NVC_MFCDatabase](../../mfc/codesnippet/cpp/crecordset-class_12.cpp)]  
  
##  <a name="a-namemstrsorta--crecordsetmstrsort"></a><a name="m_strsort"></a>CRecordset::m_strSort  
 Après avoir construit l’objet recordset, mais avant d’appeler sa **Open** membre de fonction, ce membre de données permet de stocker un `CString` contenant SQL **ORDER BY** clause.  
  
### <a name="remarks"></a>Remarques  
 Le jeu d’enregistrements utilise la chaîne de tri des enregistrements qu’il sélectionne au cours de la **Open** ou **Requery** appeler. Vous pouvez utiliser cette fonctionnalité pour trier un jeu d’enregistrements dans une ou plusieurs colonnes. La syntaxe ODBC SQL pour un **ORDER BY** clause est  
  
 `ORDER BY sort-specification [, sort-specification]...`  
  
 une spécification de classement étant un entier ou un nom de colonne. Vous pouvez également spécifier l’ordre croissant ou décroissant (par défaut, l’ordre est croissant) en ajoutant « ASC » ou « DESC » à la liste des colonnes dans la chaîne de tri. Les enregistrements sélectionnés sont triés d’abord par la première colonne répertoriée, puis par la deuxième et ainsi de suite. Par exemple, vous pouvez commander un jeu d’enregistrements « Customers » par le nom de famille, puis par prénom. Le nombre de colonnes que vous pouvez afficher la liste dépend de la source de données. Pour plus d’informations, consultez la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] *.*  
  
 Notez que vous n’incluez pas le **ORDER BY** mot clé dans votre chaîne. Fournit l’infrastructure.  
  
 Pour plus d’informations sur les clauses SQL, consultez l’article [SQL](../../data/odbc/sql.md). Pour plus d’informations sur le tri d’enregistrements, consultez l’article [Recordset : tri d’enregistrements (ODBC)](../../data/odbc/recordset-sorting-records-odbc.md).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDatabase&#31;](../../mfc/codesnippet/cpp/crecordset-class_13.cpp)]  
  
##  <a name="a-namemovea--crecordsetmove"></a><a name="move"></a>CRecordset::Move  
 Déplace le pointeur d’enregistrement actif dans le jeu d’enregistrements vers l’avant ou vers l’arrière.  
  
```  
virtual void Move(
    long nRows,  
    WORD wFetchType = SQL_FETCH_RELATIVE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nRows`  
 Le nombre de lignes à avancer ou reculer. Les valeurs positives déplacent vers l’avant, vers la fin de l’objet recordset. Les valeurs négatives déplacent vers le haut, vers le début.  
  
 `wFetchType`  
 Détermine l’ensemble de lignes qui **déplacer** extrait. Pour plus d'informations, consultez Notes.  
  
### <a name="remarks"></a>Remarques  
 Si vous passez une valeur de 0 pour `nRows`, **déplacer** actualise l’enregistrement actif. **Déplacer** prendra fin toutes `AddNew` ou **modifier** mode et restaure la valeur de l’enregistrement actif avant de `AddNew` ou **modifier** a été appelée.  
  
> [!NOTE]
>  Lorsque vous parcourez un jeu d’enregistrements, vous ne pouvez pas ignorer les enregistrements supprimés. Consultez la page [CRecordset::IsDeleted](#isdeleted) pour plus d’informations. Lorsque vous ouvrez un `CRecordset` avec la **skipDeletedRecords** option set, **déplacer** déclare si le `nRows` paramètre est 0. Ce comportement empêche l’actualisation des lignes supprimées par d’autres applications clientes qui utilisent les mêmes données. Consultez le `dwOption` paramètre [Open](#open) pour obtenir une description de **skipDeletedRecords**.  
  
 **Déplacer** repositionne le jeu d’enregistrements par jeu de lignes. Selon les valeurs de `nRows` et `wFetchType`, **déplacer** extrait l’ensemble de lignes approprié et puis fait l’enregistrement actif du premier enregistrement de cet ensemble de lignes. Si vous n’avez pas implémenté l’extraction de lignes en bloc, la taille de l’ensemble de lignes est toujours 1. Lors de l’extraction d’un ensemble de lignes, **déplacer** appelle directement la [CheckRowsetError](#checkrowseterror) fonction membre pour gérer les erreurs résultant de l’extraction.  
  
 En fonction des valeurs que vous passez, **déplacer** équivaut à d’autres `CRecordset` les fonctions membres. En particulier, la valeur de `wFetchType` peut indiquer une fonction membre qui n’est plus intuitive et souvent la méthode recommandée pour déplacer l’enregistrement courant.  
  
 Le tableau suivant répertorie les valeurs possibles de `wFetchType`, l’ensemble de lignes qui **déplacer** extrait selon `wFetchType` et `nRows`et n’importe quelle fonction membre équivalent correspondant à `wFetchType`.  
  
|wFetchType|Ensemble de lignes lues|Fonction membre équivalent|  
|----------------|--------------------|--------------------------------|  
|`SQL_FETCH_RELATIVE`(la valeur par défaut)|Le démarrage de l’ensemble de lignes `nRows` ou les lignes à partir de la première ligne dans l’ensemble de lignes en cours.||  
|`SQL_FETCH_NEXT`|L’ensemble de lignes suivant ; `nRows` est ignoré.|[MoveNext](#movenext)|  
|`SQL_FETCH_PRIOR`|L’ensemble de lignes précédente ; `nRows` est ignoré.|[MovePrev](#moveprev)|  
|`SQL_FETCH_FIRST`|Le premier ensemble de lignes dans le jeu d’enregistrements ; `nRows` est ignoré.|[MoveFirst](#movefirst)|  
|`SQL_FETCH_LAST`|Le dernier ensemble de lignes dans le jeu d’enregistrements ; `nRows` est ignoré.|[MoveLast](#movelast)|  
|`SQL_FETCH_ABSOLUTE`|Si `nRows` > 0, l’ensemble de lignes commençant `nRows` ou les lignes à partir du début du jeu d’enregistrements. Si `nRows` < 0,="" the="" rowset="" starting=""> `nRows` ou les lignes à partir de la fin de l’objet recordset. Si `nRows` = 0, une condition de début de fichier (BOF) est retournée.|[SetAbsolutePosition](#setabsoluteposition)|  
|`SQL_FETCH_BOOKMARK`|L’ensemble de lignes commençant à la ligne dont la valeur signet correspond à `nRows`.|[SetBookmark](#setbookmark)|  
  
> [!NOTE]
>  Pour les recordsets avant uniquement, **déplacer** est valide uniquement avec une valeur de `SQL_FETCH_NEXT` pour `wFetchType`.  
  
> [!CAUTION]
>  Appel de **déplacer** lève une exception si l’objet recordset ne comporte aucun enregistrement. Pour déterminer si tous les enregistrements du jeu d’enregistrements, appelez [IsBOF](#isbof) et [IsEOF](#iseof).  
  
> [!NOTE]
>  Si vous avez atteint le début ou la fin de l’objet recordset ( `IsBOF` ou `IsEOF` retourne zéro), l’appel une **déplacer** fonction lève éventuellement une `CDBException`. Par exemple, si `IsEOF` retourne zéro et `IsBOF` ne fait pas, puis `MoveNext` lève une exception, mais `MovePrev` ne sera pas.  
  
> [!NOTE]
>  Si vous appelez **déplacer** lors de l’enregistrement actif est mis à jour ou ajouté, les mises à jour sont perdues sans avertissement.  
  
 Pour plus d’informations sur la navigation de jeu d’enregistrements, consultez les articles [Recordset : défilement (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) et [Recordset : signets et Positions absolues (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Pour plus d’informations, consultez la fonction d’API ODBC **SQLExtendedFetch** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDatabase&#28;](../../mfc/codesnippet/cpp/crecordset-class_14.cpp)]  
  
##  <a name="a-namemovefirsta--crecordsetmovefirst"></a><a name="movefirst"></a>CRecordset::MoveFirst  
 Sélectionne le premier enregistrement dans le premier ensemble de lignes de l’enregistrement actif.  
  
```  
void MoveFirst();
```  
  
### <a name="remarks"></a>Remarques  
 Quelle que soit implémenté ou non l’extraction de lignes en bloc a été, ce sera toujours le premier enregistrement du jeu d’enregistrements.  
  
 Vous n’avez pas à appeler **MoveFirst** immédiatement après l’ouverture du jeu d’enregistrements. À ce stade, le premier enregistrement (le cas échéant) est automatiquement l’enregistrement actif.  
  
> [!NOTE]
>  Cette fonction membre n’est pas valide pour les recordsets avant uniquement.  
  
> [!NOTE]
>  Lorsque vous parcourez un jeu d’enregistrements, vous ne pouvez pas ignorer les enregistrements supprimés. Consultez le [IsDeleted](#isdeleted) fonction membre pour plus d’informations.  
  
> [!CAUTION]
>  L’appel de la **déplacer** fonctions lève une exception si l’objet recordset ne comporte aucun enregistrement. Pour déterminer si tous les enregistrements du jeu d’enregistrements, appelez `IsBOF` et `IsEOF`.  
  
> [!NOTE]
>  Si vous appelez une de la **déplacer** fonctions lors de l’enregistrement actif est mis à jour ou ajouté, les mises à jour sont perdues sans avertissement.  
  
 Pour plus d’informations sur la navigation de jeu d’enregistrements, consultez les articles [Recordset : défilement (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) et [Recordset : signets et Positions absolues (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [IsBOF](#isbof).  
  
##  <a name="a-namemovelasta--crecordsetmovelast"></a><a name="movelast"></a>CRecordset::MoveLast  
 Sélectionne le premier enregistrement dans le dernier ensemble de lignes de l’enregistrement actif.  
  
```  
void MoveLast();
```  
  
### <a name="remarks"></a>Notes  
 Si vous n’avez pas implémenté l’extraction de lignes en bloc, le jeu d’enregistrements a une taille d’ensemble de lignes de 1, si bien que `MoveLast` simplement déplace vers le dernier enregistrement du jeu d’enregistrements.  
  
> [!NOTE]
>  Cette fonction membre n’est pas valide pour les recordsets avant uniquement.  
  
> [!NOTE]
>  Lorsque vous parcourez un jeu d’enregistrements, vous ne pouvez pas ignorer les enregistrements supprimés. Consultez le [IsDeleted](#isdeleted) fonction membre pour plus d’informations.  
  
> [!CAUTION]
>  L’appel de la **déplacer** fonctions lève une exception si l’objet recordset ne comporte aucun enregistrement. Pour déterminer si tous les enregistrements du jeu d’enregistrements, appelez `IsBOF` et `IsEOF`.  
  
> [!NOTE]
>  Si vous appelez une de la **déplacer** fonctions lors de l’enregistrement actif est mis à jour ou ajouté, les mises à jour sont perdues sans avertissement.  
  
 Pour plus d’informations sur la navigation de jeu d’enregistrements, consultez les articles [Recordset : défilement (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) et [Recordset : signets et Positions absolues (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [IsBOF](#isbof).  
  
##  <a name="a-namemovenexta--crecordsetmovenext"></a><a name="movenext"></a>CRecordset::MoveNext  
 Sélectionne le premier enregistrement dans l’ensemble de lignes suivant l’enregistrement actif.  
  
```  
void MoveNext();
```  
  
### <a name="remarks"></a>Remarques  
 Si vous n’avez pas implémenté l’extraction de lignes en bloc, le jeu d’enregistrements a une taille d’ensemble de lignes de 1, si bien que `MoveNext` simplement se déplace vers l’enregistrement suivant.  
  
> [!NOTE]
>  Lorsque vous parcourez un jeu d’enregistrements, vous ne pouvez pas ignorer les enregistrements supprimés. Consultez le [IsDeleted](#isdeleted) fonction membre pour plus d’informations.  
  
> [!CAUTION]
>  L’appel de la **déplacer** fonctions lève une exception si l’objet recordset ne comporte aucun enregistrement. Pour déterminer si tous les enregistrements du jeu d’enregistrements, appelez `IsBOF` et `IsEOF`.  
  
> [!NOTE]
>  Il est également recommandé d’appeler `IsEOF` avant d’appeler `MoveNext`. Par exemple, si vous avez atteint après la fin de l’objet recordset, `IsEOF` retournera différente de zéro, un appel ultérieur à `MoveNext` lève une exception.  
  
> [!NOTE]
>  Si vous appelez une de la **déplacer** fonctions lors de l’enregistrement actif est mis à jour ou ajouté, les mises à jour sont perdues sans avertissement.  
  
 Pour plus d’informations sur la navigation de jeu d’enregistrements, consultez les articles [Recordset : défilement (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) et [Recordset : signets et Positions absolues (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [IsBOF](#isbof).  
  
##  <a name="a-namemovepreva--crecordsetmoveprev"></a><a name="moveprev"></a>CRecordset::MovePrev  
 Sélectionne le premier enregistrement dans l’ensemble de lignes précédent de l’enregistrement actif.  
  
```  
void MovePrev();
```  
  
### <a name="remarks"></a>Remarques  
 Si vous n’avez pas implémenté l’extraction de lignes en bloc, le jeu d’enregistrements a une taille d’ensemble de lignes de 1, si bien que `MovePrev` simplement se déplace vers l’enregistrement précédent.  
  
> [!NOTE]
>  Cette fonction membre n’est pas valide pour les recordsets avant uniquement.  
  
> [!NOTE]
>  Lorsque vous parcourez un jeu d’enregistrements, vous ne pouvez pas ignorer les enregistrements supprimés. Consultez le [IsDeleted](#isdeleted) fonction membre pour plus d’informations.  
  
> [!CAUTION]
>  L’appel de la **déplacer** fonctions lève une exception si l’objet recordset ne comporte aucun enregistrement. Pour déterminer si tous les enregistrements du jeu d’enregistrements, appelez `IsBOF` et `IsEOF`.  
  
> [!NOTE]
>  Il est également recommandé d’appeler `IsBOF` avant d’appeler `MovePrev`. Par exemple, si vous avez atteint le début du jeu d’enregistrements, `IsBOF` retournera différente de zéro, un appel ultérieur à `MovePrev` lève une exception.  
  
> [!NOTE]
>  Si vous appelez une de la **déplacer** fonctions lors de l’enregistrement actif est mis à jour ou ajouté, les mises à jour sont perdues sans avertissement.  
  
 Pour plus d’informations sur la navigation de jeu d’enregistrements, consultez les articles [Recordset : défilement (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) et [Recordset : signets et Positions absolues (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md). Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [IsBOF](#isbof).  
  
##  <a name="a-nameonsetoptionsa--crecordsetonsetoptions"></a><a name="onsetoptions"></a>CRecordset::OnSetOptions  
 Appelé pour définir les options (utilisées dans la sélection) pour l’instruction ODBC spécifiée.  
  
```  
virtual void OnSetOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Paramètres  
 `hstmt`  
 Le **HSTMT** de l’instruction ODBC dont les options doivent être définies.  
  
### <a name="remarks"></a>Notes  
 Appelez `OnSetOptions` pour définir les options (utilisées dans la sélection) pour l’instruction ODBC spécifiée. L’infrastructure appelle cette fonction membre pour définir les options initiales pour le jeu d’enregistrements. `OnSetOptions`Détermine la prise en charge de la source de données pour les curseurs permettant le défilement et d’accès concurrentiel au curseur et définit les options du jeu d’enregistrements en conséquence. (Alors que `OnSetOptions` est utilisé pour les opérations de sélection, `OnSetUpdateOptions` est utilisé pour les opérations de mise à jour.)  
  
 Substituer `OnSetOptions` pour définir les options spécifiques au pilote ou à la source de données. Par exemple, si votre source de données prend en charge l’ouverture d’un accès exclusif, vous pouvez substituer `OnSetOptions` pour tirer parti de cette capacité.  
  
 Pour plus d’informations sur les curseurs, consultez l’article [ODBC](../../data/odbc/odbc-basics.md).  
  
##  <a name="a-nameonsetupdateoptionsa--crecordsetonsetupdateoptions"></a><a name="onsetupdateoptions"></a>CRecordset::OnSetUpdateOptions  
 Appelé pour définir les options (utilisées sur la mise à jour) pour l’instruction ODBC spécifiée.  
  
```  
virtual void OnSetUpdateOptions(HSTMT hstmt);
```  
  
### <a name="parameters"></a>Paramètres  
 `hstmt`  
 Le **HSTMT** de l’instruction ODBC dont les options doivent être définies.  
  
### <a name="remarks"></a>Remarques  
 Appelez `OnSetUpdateOptions` pour définir les options (utilisées sur la mise à jour) pour l’instruction ODBC spécifiée. L’infrastructure appelle cette fonction membre après avoir créé un HSTMT pour mettre à jour des enregistrements dans un jeu d’enregistrements. (Alors que `OnSetOptions` est utilisé pour les opérations de sélection, `OnSetUpdateOptions` est utilisé pour les opérations de mise à jour.) `OnSetUpdateOptions` détermine la prise en charge de la source de données pour les curseurs permettant le défilement et d’accès concurrentiel au curseur et définit les options du jeu d’enregistrements en conséquence.  
  
 Substituer `OnSetUpdateOptions` pour définir les options d’une instruction ODBC avant que cette instruction est utilisée pour accéder à une base de données.  
  
 Pour plus d’informations sur les curseurs, consultez l’article [ODBC](../../data/odbc/odbc-basics.md).  
  
##  <a name="a-nameopena--crecordsetopen"></a><a name="open"></a>CRecordset::Open  
 Ouvre le recordset en exécutant la requête qui représente le jeu d’enregistrements ou de récupération de la table.  
  
```  
virtual BOOL Open(
    UINT nOpenType = AFX_DB_USE_DEFAULT_TYPE,  
    LPCTSTR lpszSQL = NULL,  
    DWORD dwOptions = none);
```  
  
### <a name="parameters"></a>Paramètres  
 `nOpenType`  
 Acceptez la valeur par défaut, **AFX_DB_USE_DEFAULT_TYPE**, ou utilisez une de ces valeurs à partir de la **enum OpenType**:  
  
- **CRecordset::dynaset** un jeu d’enregistrements avec défilement bidirectionnel. L’appartenance et l’ordre des enregistrements sont déterminées lors de l’objet recordset est ouvert, mais les modifications apportées par d’autres utilisateurs aux valeurs de données sont visibles après une opération d’extraction. Feuilles de réponse dynamiques sont également appelés curseurs pilotés par les jeux d’enregistrements.  
  
- **CRecordset::snapshot** un jeu d’enregistrements statique avec défilement bidirectionnel. L’appartenance et l’ordre des enregistrements sont déterminées lors de l’objet recordset est ouvert ; les valeurs de données sont déterminés lorsque les enregistrements sont extraits. Modifications apportées par d’autres utilisateurs ne sont pas visibles tant que l’objet recordset est fermé, puis rouvert.  
  
- **CRecordset::dynamic** un jeu d’enregistrements avec défilement bidirectionnel. Modifications apportées par d’autres utilisateurs aux valeurs d’appartenance, de tri et de données sont visibles après une opération d’extraction. Notez que de nombreux pilotes ODBC ne prennent pas en charge ce type de jeu d’enregistrements.  
  
- **CRecordset::forwardOnly** un jeu d’enregistrements en lecture seule avec défilement vers l’avant uniquement.  
  
     Pour `CRecordset`, la valeur par défaut est **CRecordset::snapshot**. Le mécanisme de valeur par défaut permet les Assistants Visual C++ interagir avec les deux ODBC `CRecordset` et DAO `CDaoRecordset`, qui ont différentes valeurs par défaut.  
  
 Pour plus d’informations sur ces types de jeu d’enregistrements, consultez l’article [Recordset (ODBC)](../../data/odbc/recordset-odbc.md). Pour plus d’informations, consultez l’article « À l’aide de bloc et curseurs permettant le défilement » dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
> [!CAUTION]
>  Si le type demandé n’est pas pris en charge, le framework lève une exception.  
  
 `lpszSQL`  
 Un pointeur de chaîne contenant l’une des opérations suivantes :  
  
-   A **NULL** pointeur.  
  
-   Nom d'une table.  
  
-   SQL **sélectionnez** instruction (éventuellement avec SQL **où** ou **ORDER BY** clause).  
  
-   A **appeler** instruction en spécifiant le nom d’une requête prédéfinie (procédure stockée). Veillez à ce que vous n’insérez pas d’espace entre l’accolade et **appeler** (mot clé).  
  
 Pour plus d’informations sur cette chaîne, consultez la table et la présentation du rôle de ClassWizard sous la section Notes.  
  
> [!NOTE]
>  L’ordre des colonnes dans le jeu de résultats doit correspondre à l’ordre de la RFX ou RFX en bloc fonction appelle dans votre [DoFieldExchange](#dofieldexchange) ou [DoBulkFieldExchange](#dobulkfieldexchange) fonction de remplacement.  
  
 `dwOptions`  
 Masque de bits qui peut spécifier une combinaison des valeurs répertoriées ci-dessous. Certains d'entre eux sont mutuellement exclusifs. La valeur par défaut est **aucun**.  
  
- **CRecordset::none** aucun jeu d’options. Cette valeur de paramètre est mutuellement exclusive avec toutes les autres valeurs. Par défaut, le jeu d’enregistrements peut être mis à jour avec [modifier](#edit) ou [supprimer](#delete) et permet l’ajout de nouveaux enregistrements avec [AddNew](#addnew). Mise à jour dépend de la source de données, ainsi que dans le `nOpenType` option que vous spécifiez. Optimisation pour les ajouts en bloc n’est pas disponible. L’extraction de lignes en bloc n’est pas effectuée. Les enregistrements supprimés ne seront pas être ignorés pendant la navigation de jeu d’enregistrements. Les signets ne sont pas disponibles. La vérification automatique de champ incorrecte est implémentée.  
  
- **CRecordset::appendOnly** n’autorisent pas **modifier** ou **supprimer** sur le jeu d’enregistrements. Autoriser `AddNew` uniquement. Cette option s’exclut mutuellement avec **CRecordset::readOnly**.  
  
- **CRecordset::readOnly** ouvrir le jeu d’enregistrements en lecture seule. Cette option s’exclut mutuellement avec **CRecordset::appendOnly**.  
  
- **CRecordset::optimizeBulkAdd** utiliser une instruction SQL préparée pour optimiser l’ajout de plusieurs enregistrements à la fois. S’applique uniquement si vous n’utilisez pas la fonction d’API ODBC **SQLSetPos** pour mettre à jour le jeu d’enregistrements. La première mise à jour détermine quels champs sont marqués comme modifiés. Cette option s’exclut mutuellement avec `CRecordset::useMultiRowFetch`.  
  
- `CRecordset::useMultiRowFetch`Implémenter l’extraction de lignes en bloc pour autoriser plusieurs lignes doivent être extraites par une opération de lecture seule. Il s’agit d’une fonctionnalité avancée conçue pour améliorer les performances ; Toutefois, RFX en bloc n’est pas pris en charge par ClassWizard. Cette option s’exclut mutuellement avec **CRecordset::optimizeBulkAdd**. Notez que si vous spécifiez `CRecordset::useMultiRowFetch`, puis l’option **CRecordset::noDirtyFieldCheck** sera activé automatiquement (double tampon ne pas être disponible) ; sur les recordsets avant uniquement, l’option **CRecordset::useExtendedFetch** est activé automatiquement. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
- **CRecordset::skipDeletedRecords** ignorer tous les enregistrements supprimés lors de la navigation dans le jeu d’enregistrements. Cela ralentit les performances dans certaines extractions relatives. Cette option n’est pas valide sur les recordsets avant uniquement. Si vous appelez [déplacer](#move) avec le `nRows` paramètre la valeur 0 et le **CRecordset::skipDeletedRecords** option set, **déplacer** sera évaluée. Notez que **CRecordset::skipDeletedRecords** est similaire à *compression du pilote*, ce qui signifie que les lignes supprimées est supprimées du jeu d’enregistrements. Toutefois, si votre pilote de packs d’enregistrements, puis il ignorera uniquement les enregistrements que vous supprimez ; il ignore pas les enregistrements supprimés par d’autres utilisateurs, tandis que le jeu d’enregistrements est ouvert. **CRecordset::skipDeletedRecords** ignorera les lignes supprimées par d’autres utilisateurs.  
  
- **CRecordset::useBookmarks** peut utiliser des signets sur le recordset, si pris en charge. Signets ralentissement la récupération des données mais améliorent les performances de navigation dans les données. Non valide sur les recordsets avant uniquement. Pour plus d’informations, consultez l’article [Recordset : signets et Positions absolues (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
- **CRecordset::noDirtyFieldCheck** désactiver automatique de champ incorrecte vérification (double mise en mémoire tampon). Cela améliorera les performances ; Toutefois, vous devez marquer manuellement les champs comme telles en appelant le `SetFieldDirty` et `SetFieldNull` les fonctions membres. Notez ce mécanisme de double tampon dans la classe `CRecordset` est similaire à la double mise en tampon dans la classe `CDaoRecordset`. Toutefois, dans `CRecordset`, vous ne pouvez pas activer la double mise en tampon sur les champs individuels ; vous l’activer pour tous les champs ou le désactiver pour tous les champs. Notez que si vous spécifiez l’option `CRecordset::useMultiRowFetch`, puis **CRecordset::noDirtyFieldCheck** sera activé automatiquement ; Toutefois, `SetFieldDirty` et `SetFieldNull` ne peuvent pas être utilisées sur les recordsets qui implémentent l’extraction de lignes en bloc.  
  
- **CRecordset::executeDirect** n’utilisez pas une instruction SQL préparée. Pour améliorer les performances, spécifiez cette option si le **Requery** fonction membre ne sera jamais appelée.  
  
- **CRecordset::useExtendedFetch** implémentez **SQLExtendedFetch** au lieu de **SQLFetch**. Il est conçu pour l’implémentation de l’extraction de lignes en bloc sur les recordsets avant uniquement. Si vous spécifiez l’option `CRecordset::useMultiRowFetch` sur un recordset en avant seulement, puis **CRecordset::useExtendedFetch** est activé automatiquement.  
  
- **CRecordset::userAllocMultiRowBuffers** l’utilisateur alloue des tampons de stockage pour les données. Utilisez cette option conjointement avec `CRecordset::useMultiRowFetch` si vous souhaitez allouer votre propre stockage ; sinon, le framework automatiquement alloue le stockage nécessaire. Pour plus d’informations, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md). Notez que la spécification **CRecordset::userAllocMultiRowBuffers** sans spécifier `CRecordset::useMultiRowFetch` entraîne un échec d’assertion.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le `CRecordset` objet a été ouvert ; sinon, 0 si [CDatabase::Open](../../mfc/reference/cdatabase-class.md#open) (s’il est appelé) renvoie la valeur 0.  
  
### <a name="remarks"></a>Notes  
 Vous devez appeler cette fonction membre pour exécuter la requête définie par l’objet recordset. Avant d’appeler **Open**, vous devez créer l’objet recordset.  
  
 Connexion de ce jeu d’enregistrements à la source de données dépend de la façon dont vous construisez le recordset avant d’appeler **ouvrir**. Si vous passez un [CDatabase](../../mfc/reference/cdatabase-class.md) de l’objet au constructeur de jeu d’enregistrements qui n’est pas connecté à la source de données, cette fonction membre utilise [GetDefaultConnect](#getdefaultconnect) pour essayer d’ouvrir l’objet de base de données. Si vous transmettez **NULL** au constructeur de jeu d’enregistrements, le constructeur construit un `CDatabase` objet, et **Open** tente de se connecter à l’objet de base de données. Pour plus d’informations sur la fermeture de l’objet recordset et la connexion dans ces circonstances différentes, consultez [fermer](#close).  
  
> [!NOTE]
>  Accès à une source de données via un `CRecordset` est toujours partagé. Contrairement à la `CDaoRecordset` (classe), vous ne pouvez pas utiliser un `CRecordset` objet pour ouvrir une source de données avec un accès exclusif.  
  
 Lorsque vous appelez **Open**, une requête, généralement SQL **sélectionner** , sélectionne les enregistrements selon des critères présentés dans le tableau suivant.  
  
|Valeur du paramètre lpszSQL|Enregistrements sélectionnés sont déterminés par|Exemple|  
|------------------------------------|----------------------------------------|-------------|  
|**VALEUR NULL**|La chaîne retournée par `GetDefaultSQL`.||  
|Nom de la table SQL|Toutes les colonnes de la liste de tables dans `DoFieldExchange` ou `DoBulkFieldExchange`.|`"Customer"`|  
|Nom de la requête prédéfinie (procédure stockée)|Les colonnes de que la requête est définie pour retourner.|`"{call OverDueAccts}"`|  
|**Sélectionnez** liste de colonnes **FROM** liste de table|Les colonnes spécifiées dans les tables spécifiées.|`"SELECT CustId, CustName FROM`<br /><br /> `Customer"`|  
  
> [!CAUTION]
>  Veillez à ce que vous n’insérez pas d’espace blanc supplémentaire dans la chaîne SQL. Par exemple, si vous insérez un espace blanc entre les accolades et **appeler** (mot clé), MFC interprète la chaîne SQL comme nom de table et les incorporer dans une **sélectionnez** instruction, ce qui provoquera une exception est levée. De même, si votre requête prédéfinie utilise un paramètre de sortie, n’insérez pas d’espace entre l’accolade et la « symbole. Enfin, vous ne devez pas insérer les blancs avant l’accolade dans un **appeler** instruction ou avant le **sélectionnez** mot clé dans une **sélectionnez** instruction.  
  
 La procédure habituelle consiste à passer **NULL** à **Open**; dans ce cas, **Open** appelle [GetDefaultSQL](#getdefaultsql). Si vous utilisez un dérivé `CRecordset` (classe), **GetDefaultSQL** donne le nom de table spécifié dans ClassWizard. Vous pouvez spécifier à la place d’autres informations dans la `lpszSQL` paramètre.  
  
 Tout ce que vous passez, **Open** construit une dernière chaîne SQL pour la requête (la chaîne est peut-être SQL **où** et **ORDER BY** clauses ajouté à la `lpszSQL` chaîne transmise), puis exécute la requête. Vous pouvez examiner la chaîne construite en appelant [GetSQL](#getsql) après avoir appelé **ouvrir**. Pour plus d’informations concernant le jeu d’enregistrements crée une instruction SQL et sélectionne les enregistrements, consultez l’article [Recordset : sélection d’enregistrements (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md).  
  
 Données membres de champ de votre classe de jeu d’enregistrements sont liés aux colonnes de données sélectionnées. Si tous les enregistrements sont retournés, le premier enregistrement devient l’enregistrement actif.  
  
 Si vous souhaitez définir des options pour le jeu d’enregistrements, par exemple un filtre ou un tri, spécifiez ces après avoir construit l’objet recordset et avant d’appeler **ouvrir**. Si vous souhaitez actualiser les enregistrements dans le jeu d’enregistrements après le jeu d’enregistrements est déjà ouvert, appelez [Requery](#requery).  
  
 Pour plus d’informations, y compris des exemples supplémentaires, consultez les articles [Recordset (ODBC)](../../data/odbc/recordset-odbc.md), [Recordset : sélection d’enregistrements (ODBC)](../../data/odbc/recordset-how-recordsets-select-records-odbc.md), et [Recordset : création et fermeture de Recordsets (ODBC)](../../data/odbc/recordset-creating-and-closing-recordsets-odbc.md).  
  
### <a name="example"></a>Exemple  
 Les exemples de code suivants illustrent différentes formes de la **Open** appeler.  
  
 [!code-cpp[NVC_MFCDatabase&#16;](../../mfc/codesnippet/cpp/crecordset-class_15.cpp)]  
  
##  <a name="a-namerefreshrowseta--crecordsetrefreshrowset"></a><a name="refreshrowset"></a>CRecordset::RefreshRowset  
 Met à jour les données et l’état d’une ligne dans l’ensemble de lignes en cours.  
  
```  
void RefreshRowset(
    WORD wRow,  
    WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>Paramètres  
 `wRow`  
 Basée sur une position d’une ligne dans l’ensemble de lignes en cours. Cette valeur peut aller de zéro à la taille de l’ensemble de lignes.  
  
 `wLockType`  
 Une valeur indiquant le mode de verrouillage de la ligne après que qu’il a été actualisé. Pour plus d'informations, consultez Notes.  
  
### <a name="remarks"></a>Remarques  
 Si vous passez une valeur de zéro pour `wRow`, puis chaque ligne dans l’ensemble de lignes est actualisé.  
  
 Pour utiliser `RefreshRowset`, vous devez avoir implémenté l’extraction de lignes en bloc en spécifiant le **CRecordset::useMulitRowFetch** option dans le [Open](#open) fonction membre.  
  
 `RefreshRowset`appelle la fonction API ODBC **SQLSetPos**. Le `wLockType` paramètre spécifie l’état de la ligne après **SQLSetPos** a été exécutée. Le tableau suivant décrit les valeurs possibles pour `wLockTyp`e.  
  
|wLockType|Description|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE`(la valeur par défaut)|La source de données ou le pilote garantit que la ligne est dans le même état verrouillé ou déverrouillé qu’elle était avant `RefreshRowset` a été appelée.|  
|`SQL_LOCK_EXCLUSIVE`|La source de données ou de pilote verrouille exclusivement la ligne. Toutes les données sources ne prennent en charge ce type de verrou.|  
|`SQL_LOCK_UNLOCK`|La source de données ou de pilote déverrouille la ligne. Toutes les données sources ne prennent en charge ce type de verrou.|  
  
 Pour plus d’informations sur **SQLSetPos**, consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="a-namerequerya--crecordsetrequery"></a><a name="requery"></a>CRecordset::Requery  
 Reconstruit (actualisation) un jeu d’enregistrements.  
  
```  
virtual BOOL Requery();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le jeu d’enregistrements a été créé avec succès ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Si tous les enregistrements sont retournés, le premier enregistrement devient l’enregistrement actif.  
  
 Dans l’ordre du jeu d’enregistrements afin de refléter les ajouts et suppressions que vous ou autres utilisateurs effectuent dans la source de données, vous devez reconstruire le jeu d’enregistrements en appelant **Requery**. Si le jeu d’enregistrements est un dynaset, il reflète automatiquement les mises à jour vous ou autres utilisateurs à ses enregistrements existants (mais pas d’ajouts). Si le jeu d’enregistrements est un instantané, vous devez appeler **Requery** afin de refléter les modifications apportées par d’autres utilisateurs ainsi que les ajouts et les suppressions.  
  
 Pour une feuille de réponse dynamique ou un instantané, appelez **Requery** chaque fois que vous souhaitez reconstruire le jeu d’enregistrements à l’aide d’un nouveau filtre ou de tri ou de nouvelles valeurs de paramètre. Définissez la nouvelle propriété de filtrer ou trier en assignant de nouvelles valeurs à **m_strFilter** et `m_strSort` avant d’appeler **Requery**. Définir de nouveaux paramètres en assignant de nouvelles valeurs aux membres de données de paramètre avant d’appeler **Requery**. Si les chaînes de filtre et de tri sont identiques, vous pouvez réutiliser la requête, ce qui améliore les performances.  
  
 Si la tentative pour reconstruire le recordset échoue, l’objet recordset est fermé. Avant d’appeler **Requery**, vous pouvez déterminer si le jeu d’enregistrements peut être actualisée en appelant le `CanRestart` fonction membre. `CanRestart`ne garantit pas que **Requery** réussit.  
  
> [!CAUTION]
>  Appelez **Requery** uniquement après avoir appelé [ouvrir](#open).  
  
### <a name="example"></a>Exemple  
 Cet exemple reconstruit un jeu d’enregistrements pour appliquer un ordre de tri différent.  
  
 [!code-cpp[NVC_MFCDatabase&#29;](../../mfc/codesnippet/cpp/crecordset-class_16.cpp)]  
  
##  <a name="a-namesetabsolutepositiona--crecordsetsetabsoluteposition"></a><a name="setabsoluteposition"></a>CRecordset::SetAbsolutePosition  
 Positionne le jeu d’enregistrements dans l’enregistrement correspondant au numéro d’enregistrement spécifié.  
  
```  
void SetAbsolutePosition(long nRows);
```  
  
### <a name="parameters"></a>Paramètres  
 `nRows`  
 Basée sur une position ordinale de l’enregistrement actuel dans le jeu d’enregistrements.  
  
### <a name="remarks"></a>Notes  
 `SetAbsolutePosition`Déplace le pointeur d’enregistrement en cours en fonction de cette position ordinale.  
  
> [!NOTE]
>  Cette fonction membre n’est pas valide sur les recordsets avant uniquement.  
  
 Pour les jeux d’enregistrements ODBC, un paramètre de position absolue 1 fait référence au premier enregistrement du jeu d’enregistrements ; la valeur 0 fait référence à la position (BOF) de début du fichier.  
  
 Vous pouvez également transmettre des valeurs négatives pour `SetAbsolutePosition`. Dans ce cas la position du jeu d’enregistrements est évaluée à partir de la fin de l’objet recordset. Par exemple, `SetAbsolutePosition( -1 )` déplace le pointeur d’enregistrement actif vers le dernier enregistrement du jeu d’enregistrements.  
  
> [!NOTE]
>  Position absolue n’est pas destinée à être utilisée en tant que numéro d’enregistrement de substitution. Les signets sont toujours recommandé de conserver et renvoyer une position donnée, car une modification de position d’un enregistrement lorsque les enregistrements précédents sont supprimés. En outre, vous ne pouvez pas être sûr qu’un enregistrement donné possédera la même position absolue si le jeu d’enregistrements est recréé car l’ordre des enregistrements individuels dans un jeu d’enregistrements n’est pas garanti, sauf si elle est créée avec une instruction SQL à l’aide un **ORDER BY** clause.  
  
 Pour plus d’informations sur la navigation de jeu d’enregistrements et les signets, consultez les articles [Recordset : défilement (ODBC)](../../data/odbc/recordset-scrolling-odbc.md) et [Recordset : signets et Positions absolues (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md).  
  
##  <a name="a-namesetbookmarka--crecordsetsetbookmark"></a><a name="setbookmark"></a>CRecordset::SetBookmark  
 Positionne le jeu d’enregistrements sur l’enregistrement qui contient le signet spécifié.  
  
```  
void SetBookmark(const CDBVariant& varBookmark);
```  
  
### <a name="parameters"></a>Paramètres  
 `varBookmark`  
 Une référence à un [CDBVariant](../../mfc/reference/cdbvariant-class.md) objet contenant la valeur de signet d’un enregistrement spécifique.  
  
### <a name="remarks"></a>Remarques  
 Pour déterminer si les signets sont pris en charge sur le jeu d’enregistrements, appelez [CanBookmark](#canbookmark). Pour rendre les signets si elles sont prises en charge, vous devez configurer le **CRecordset::useBookmarks** option dans le `dwOptions` paramètre de la [Open](#open) fonction membre.  
  
> [!NOTE]
>  Si les signets sont pris en charge ou non disponible, l’appel `SetBookmark` entraîne une exception est levée. Les signets ne sont pas pris en charge sur les recordsets avant uniquement.  
  
 Pour tout d’abord récupérer le signet de l’enregistrement en cours, appelez [GetBookmark](#getbookmark), qui enregistre la valeur du signet à un `CDBVariant` objet. Plus tard, vous pouvez revenir à cet enregistrement en appelant `SetBookmark` à l’aide de la valeur du signet enregistré.  
  
> [!NOTE]
>  Après certaines opérations de jeu d’enregistrements, vous devez vérifier la persistance de signet avant d’appeler `SetBookmark`. Par exemple, si vous récupérez un signet avec `GetBookmark` , puis appelez **Requery**, le signet peut ne plus être valide. Appelez [CDatabase::GetBookmarkPersistence](../../mfc/reference/cdatabase-class.md#getbookmarkpersistence) pour vérifier si vous pouvez appeler en toute sécurité `SetBookmark`.  
  
 Pour plus d’informations sur les signets et de navigation de jeu d’enregistrements, consultez les articles [Recordset : signets et Positions absolues (ODBC)](../../data/odbc/recordset-bookmarks-and-absolute-positions-odbc.md) et [Recordset : défilement (ODBC)](../../data/odbc/recordset-scrolling-odbc.md).  
  
##  <a name="a-namesetfielddirtya--crecordsetsetfielddirty"></a><a name="setfielddirty"></a>CRecordset::SetFieldDirty  
 Marque un membre de données de champ du jeu d’enregistrements modifié ou inchangé.  
  
```  
void SetFieldDirty(void* pv, BOOL bDirty = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pv`  
 Contient l’adresse d’un membre de données de champ dans le jeu d’enregistrements ou **NULL**. Si **NULL**, tous les membres de données de champ dans le jeu d’enregistrements marqués. (C++ **NULL** n’est pas identique à la valeur Null dans la terminologie de base de données, ce qui signifie « n’avoir aucune valeur ».)  
  
 `bDirty`  
 **TRUE** si le membre de données de champ doit être marqué comme « dirty » (modifiés). Dans le cas contraire **FALSE** si le membre de données de champ doit être marqué comme étant « nettoyer » (non modifié).  
  
### <a name="remarks"></a>Remarques  
 Marquage des champs restent inchangés garantit le champ n’est pas mis à jour et entraîne moins de trafic SQL.  
  
> [!NOTE]
>  Cette fonction membre n’est pas applicable sur les jeux d’enregistrements qui est à l’aide de l’extraction de lignes en bloc. Si vous avez implémenté l’extraction de lignes en bloc, puis `SetFieldDirty` entraîne un échec d’assertion. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Les marques de framework modifié des données membres de champ pour vous assurer qu’ils seront écrits à l’enregistrement dans la source de données par le mécanisme record field exchange (RFX). En général la modification de la valeur d’un champ définit le champ modifié automatiquement, donc vous devrez rarement appeler `SetFieldDirty` vous-même, mais vous pouvez parfois souhaiter vous assurer que les colonnes seront explicitement mis à jour ou insérées, quelle que soit la valeur est le champ membre de données.  
  
> [!CAUTION]
>  Appelez cette fonction membre uniquement après avoir appelé [modifier](#edit) ou [AddNew](#addnew).  
  
 À l’aide de **NULL** pour le premier argument de la fonction s’applique uniquement à la fonction **outputColumn** ne champs pas **param** champs. Par exemple, l’appel  
  
 [!code-cpp[NVC_MFCDatabase&#26;](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 définit uniquement **outputColumn** champs **NULL**; **param** champs ne seront pas affectées.  
  
 Pour travailler sur **param** champs, vous devez fournir l’adresse réelle de l’individu **param** à utiliser, tel que :  
  
 [!code-cpp[27 NVC_MFCDatabase](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Cela signifie que vous ne pouvez pas définir toutes les **param** champs **NULL**, comme vous pouvez le faire avec **outputColumn** champs.  
  
##  <a name="a-namesetfieldnulla--crecordsetsetfieldnull"></a><a name="setfieldnull"></a>CRecordset::SetFieldNull  
 Marque un membre de données de champ du jeu d’enregistrements en tant que valeur Null (en particulier n’avoir aucune valeur) ou non Null.  
  
```  
void SetFieldNull(void* pv, BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pv`  
 Contient l’adresse d’un membre de données de champ dans le jeu d’enregistrements ou **NULL**. Si **NULL**, tous les membres de données de champ dans le jeu d’enregistrements marqués. (C++ **NULL** n’est pas identique à la valeur Null dans la terminologie de base de données, ce qui signifie « n’avoir aucune valeur ».)  
  
 `bNull`  
 Différent de zéro si le membre de données de champ doit être marquée comme en ne comportant aucun valeur (Null). Sinon, 0 si le membre de données de champ doit être marquée comme étant non Null.  
  
### <a name="remarks"></a>Remarques  
 Lorsque vous ajoutez un nouvel enregistrement à un jeu d’enregistrements, tous les membres de données de champ sont initialement définies sur une valeur Null et marqués comme « dirty » (modifiés). Lorsque vous récupérez un enregistrement d’une source de données, ses colonnes déjà ont des valeurs ou sont Null.  
  
> [!NOTE]
>  N’appelez pas cette fonction membre sur les jeux d’enregistrements qui est à l’aide de l’extraction de lignes en bloc. Si vous avez implémenté l’extraction de lignes en bloc, l’appel `SetFieldNull` entraîne un échec d’assertion. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Si vous voulez désigner un champ de l’enregistrement actuel comme n’ayant ne pas une valeur, appelez `SetFieldNull` avec `bNull` la valeur **TRUE** marquer en tant que valeur Null. Si un champ marqué Null et que vous voulez lui attribuer une valeur, définissez simplement sa nouvelle valeur. Vous n’avez pas à supprimer l’indicateur Null avec `SetFieldNull`. Pour déterminer si le champ peut être Null, appelez `IsFieldNullable`.  
  
> [!CAUTION]
>  Appelez cette fonction membre uniquement après avoir appelé [modifier](#edit) ou [AddNew](#addnew).  
  
 À l’aide de **NULL** pour le premier argument de la fonction s’applique uniquement à la fonction **outputColumn** ne champs pas **param** champs. Par exemple, l’appel  
  
 [!code-cpp[NVC_MFCDatabase&#26;](../../mfc/codesnippet/cpp/crecordset-class_10.cpp)]  
  
 définit uniquement **outputColumn** champs **NULL**; **param** champs ne seront pas affectées.  
  
 Pour travailler sur **param** champs, vous devez fournir l’adresse réelle de l’individu **param** à utiliser, tel que :  
  
 [!code-cpp[27 NVC_MFCDatabase](../../mfc/codesnippet/cpp/crecordset-class_11.cpp)]  
  
 Cela signifie que vous ne pouvez pas définir toutes les **param** champs **NULL**, comme vous pouvez le faire avec **outputColumn** champs.  
  
> [!NOTE]
>  Lors de la définition des paramètres NULL, un appel à `SetFieldNull` avant que le jeu d’enregistrements est ouvert entraîne une assertion. Dans ce cas, appelez [SetParamNull](#setparamnull).  
  
 `SetFieldNull`est implémenté via [DoFieldExchange](#dofieldexchange).  
  
##  <a name="a-namesetlockingmodea--crecordsetsetlockingmode"></a><a name="setlockingmode"></a>CRecordset::SetLockingMode  
 Définit le mode de verrouillage « optimiste » verrouillage (par défaut) ou « pessimiste ». Détermine la façon dont les enregistrements sont verrouillés pour les mises à jour.  
  
```  
void SetLockingMode(UINT nMode);
```  
  
### <a name="parameters"></a>Paramètres  
 `nMode`  
 Contient l’une des valeurs suivantes à partir de la **enum LockMode**:  
  
- **optimiste** le verrouillage optimiste verrouille l’enregistrement mis à jour uniquement lors de l’appel à **mise à jour**.  
  
- **pessimiste** le verrouillage pessimiste verrouille l’enregistrement dès que **modifier** est appelée et le conserve bloqué jusqu'à ce que la **mise à jour** fin de l’appel ou de vous déplacer vers un nouvel enregistrement.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction membre, si vous devez spécifier les deux stratégies de verrouillage des enregistrements à l’aide de l’objet recordset pour les mises à jour. Par défaut, le mode de verrouillage d’un objet recordset est **optimiste**. Vous pouvez remplacer plus prudent **pessimiste** la stratégie de verrouillage. Appelez `SetLockingMode` une fois que vous construisez et ouvrez l’objet recordset, mais avant d’appeler **modifier**.  
  
##  <a name="a-namesetparamnulla--crecordsetsetparamnull"></a><a name="setparamnull"></a>CRecordset::SetParamNull  
 Marque un paramètre en tant que valeur Null (en particulier n’avoir aucune valeur) ou non Null.  
  
```  
void SetParamNull(
    int nIndex,  
    BOOL bNull = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de base zéro du paramètre.  
  
 `bNull`  
 Si **TRUE** (la valeur par défaut), le paramètre est marqué comme étant Null. Sinon, le paramètre est marqué comme non Null.  
  
### <a name="remarks"></a>Notes  
 Contrairement aux [SetFieldNull](#setfieldnull), vous pouvez appeler `SetParamNull` avant que vous avez ouvert le jeu d’enregistrements.  
  
 `SetParamNull`est généralement utilisé avec les requêtes prédéfinies (procédures stockées).  
  
##  <a name="a-namesetrowsetcursorpositiona--crecordsetsetrowsetcursorposition"></a><a name="setrowsetcursorposition"></a>CRecordset::SetRowsetCursorPosition  
 Déplace le curseur à une ligne dans l’ensemble de lignes en cours.  
  
```  
void SetRowsetCursorPosition(WORD wRow, WORD wLockType = SQL_LOCK_NO_CHANGE);
```  
  
### <a name="parameters"></a>Paramètres  
 `wRow`  
 Basée sur une position d’une ligne dans l’ensemble de lignes en cours. Cette valeur peut varier de 1 à la taille de l’ensemble de lignes.  
  
 `wLockType`  
 Valeur indiquant le mode de verrouillage de la ligne après que qu’il a été actualisé. Pour plus d'informations, consultez Notes.  
  
### <a name="remarks"></a>Remarques  
 Lors de l’implémentation de l’extraction de lignes en bloc, les enregistrements sont extraits par les ensembles de lignes, où le premier enregistrement de l’ensemble de lignes lues est l’enregistrement actif. Pour activer un autre enregistrement dans l’ensemble de lignes, appelez `SetRowsetCursorPosition`. Par exemple, vous pouvez combiner `SetRowsetCursorPosition` avec la [GetFieldValue](#getfieldvalue) fonction membre pour récupérer dynamiquement les données à partir de n’importe quel enregistrement de votre jeu d’enregistrements.  
  
 Pour utiliser `SetRowsetCursorPosition`, vous devez avoir implémenté l’extraction de lignes en bloc en spécifiant le `CRecordset::useMultiRowFetch` option de la `dwOptions` paramètre dans le [Open](#open) fonction membre.  
  
 `SetRowsetCursorPosition`appelle la fonction API ODBC **SQLSetPos**. Le `wLockType` paramètre spécifie l’état de la ligne après **SQLSetPos** a été exécutée. Le tableau suivant décrit les valeurs possibles pour `wLockTyp`e.  
  
|wLockType|Description|  
|---------------|-----------------|  
|`SQL_LOCK_NO_CHANGE`(la valeur par défaut)|La source de données ou le pilote garantit que la ligne est dans le même état verrouillé ou déverrouillé qu’elle était avant `SetRowsetCursorPosition` a été appelée.|  
|`SQL_LOCK_EXCLUSIVE`|La source de données ou de pilote verrouille exclusivement la ligne. Toutes les données sources ne prennent en charge ce type de verrou.|  
|`SQL_LOCK_UNLOCK`|La source de données ou de pilote déverrouille la ligne. Toutes les données sources ne prennent en charge ce type de verrou.|  
  
 Pour plus d’informations sur **SQLSetPos**, consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="a-namesetrowsetsizea--crecordsetsetrowsetsize"></a><a name="setrowsetsize"></a>CRecordset::SetRowsetSize  
 Spécifie le nombre d’enregistrements que vous souhaitez récupérer lors d’une extraction.  
  
```  
virtual void SetRowsetSize(DWORD dwNewRowsetSize);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwNewRowsetSize*  
 Le nombre de lignes à récupérer lors d’une extraction donnée.  
  
### <a name="remarks"></a>Notes  
 Cette fonction membre virtuelle Spécifie le nombre de lignes à extraire au cours d’une seule extraction lors de l’extraction de lignes en bloc. Pour implémenter l’extraction de lignes en bloc, vous devez définir le `CRecordset::useMultiRowFetch` option dans le `dwOptions` paramètre de la [Open](#open) fonction membre.  
  
> [!NOTE]
>  Appel de `SetRowsetSize` sans avoir à implémenter en bloc l’extraction de lignes entraîne un échec d’assertion.  
  
 Appelez `SetRowsetSize` avant d’appeler **Open** de définir initialement la taille de l’ensemble de lignes du jeu d’enregistrements. La taille par défaut lors de l’implémentation de l’extraction de lignes en bloc est 25.  
  
> [!NOTE]
>  Soyez prudent lors de l’appel `SetRowsetSize`. Si vous affectez manuellement stockage pour les données (comme spécifié par le **CRecordset::userAllocMultiRowBuffers** option du paramètre dwOptions dans **Open**), vous devez vérifier si vous devez réaffecter ces tampons de stockage après l’appel à `SetRowsetSize`, mais avant d’effectuer toute opération de navigation du curseur.  
  
 Pour obtenir la valeur actuelle de la taille de l’ensemble de lignes, appelez [GetRowsetSize](#getrowsetsize).  
  
 Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
##  <a name="a-nameupdatea--crecordsetupdate"></a><a name="update"></a>CRecordset::Update  
 Termine une `AddNew` ou **modifier** opération en enregistrant les données nouvelles ou modifiées sur la source de données.  
  
```  
virtual BOOL Update();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si un enregistrement a été correctement mis à jour ; Sinon, 0 si aucune colonne n’ont été modifiés. Si aucun enregistrement n’a été mis à jour, ou si plus d’un enregistrement a été mis à jour, une exception est levée. Une exception est également levée pour toute autre défaillance sur la source de données.  
  
### <a name="remarks"></a>Notes  
 Appelez cette fonction membre après un appel à la [AddNew](#addnew) ou [modifier](#edit) fonction membre. Cet appel est nécessaire pour terminer le `AddNew` ou **modifier** opération.  
  
> [!NOTE]
>  Si vous avez implémenté l’extraction de lignes en bloc, vous ne pouvez pas appeler **mise à jour**. Cela entraîne un échec d’assertion. Bien que classe `CRecordset` ne fournit pas de mécanisme de mise à jour en bloc des lignes de données, vous pouvez écrire vos propres fonctions à l’aide de la fonction API ODBC **SQLSetPos**. Pour plus d’informations sur l’extraction de lignes en bloc, consultez l’article [Recordset : extraction globale d’enregistrements en bloc (ODBC)](../../data/odbc/recordset-fetching-records-in-bulk-odbc.md).  
  
 Les deux `AddNew` et **modifier** préparer un tampon d’édition dans lequel sont placées les données ajoutées ou modifiées pour l’enregistrement dans la source de données. **Mise à jour** enregistre les données. Seuls les champs marqués ou détecté comme étant modifiées sont mises à jour.  
  
 Si la source de données prend en charge les transactions, vous pouvez rendre le **mise à jour** appeler (et de son `AddNew` ou **modifier** appeler) dans le cadre d’une transaction. Pour plus d’informations sur les transactions, consultez l’article [Transaction (ODBC)](../../data/odbc/transaction-odbc.md).  
  
> [!CAUTION]
>  Si vous appelez **mise à jour** sans d’abord appeler `AddNew` ou **modifier**, **mise à jour** lève une `CDBException`. Si vous appelez `AddNew` ou **modifier**, vous devez appeler **mise à jour** avant d’appeler un **déplacer** opération ou avant de fermer le jeu d’enregistrements ou la connexion de source de données. Dans le cas contraire, vos modifications sont perdues sans notification.  
  
 Pour plus d’informations sur la gestion des **mise à jour** échecs, consultez l’article [Recordset : mise à jour des enregistrements de jeux d’enregistrements (ODBC)](../../data/odbc/recordset-how-recordsets-update-records-odbc.md).  
  
### <a name="example"></a>Exemple  
 Consultez l’article [Transaction : exécution d’une Transaction dans un Recordset (ODBC)](../../data/odbc/transaction-performing-a-transaction-in-a-recordset-odbc.md).  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CDatabase (classe)](../../mfc/reference/cdatabase-class.md)   
 [CRecordView (classe)](../../mfc/reference/crecordview-class.md)

