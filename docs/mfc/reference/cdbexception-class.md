---
title: Classe de CDBException | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDBException
- AFXDB/CDBException
- AFXDB/CDBException::m_nRetCode
- AFXDB/CDBException::m_strError
- AFXDB/CDBException::m_strStateNativeOrigin
dev_langs:
- C++
helpviewer_keywords:
- CDBException class
- exceptions [C++], database
- database exceptions [C++]
- ODBC classes [C++], exceptions
- errors [C++], database
ms.assetid: eb9e1119-89f5-49a7-b9d4-b91cee1ccc82
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: fc3bf7be273bf509dd1ee79fb42e69050070e830
ms.lasthandoff: 02/24/2017

---
# <a name="cdbexception-class"></a>CDBException (classe)
Représente une condition d'exception résultant des classes de base de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDBException : public CException  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDBException::m_nRetCode](#m_nretcode)|Contient un code de retour Open Database Connectivity (ODBC), de type **et RETCODE contient**.|  
|[CDBException::m_strError](#m_strerror)|Contient une chaîne qui décrit l’erreur en termes alphanumérique.|  
|[CDBException::m_strStateNativeOrigin](#m_strstatenativeorigin)|Contient une chaîne décrivant l’erreur en termes des codes d’erreur retournée par ODBC.|  
  
## <a name="remarks"></a>Remarques  
 La classe inclut deux membres de données publics que vous pouvez utiliser pour déterminer la cause de l’exception ou d’afficher un message décrivant l’exception. `CDBException`les objets sont construits et levées par les fonctions membres des classes de base de données.  
  
> [!NOTE]
>  Cette classe est une des classes de Open Database Connectivity (ODBC) de MFC. Si vous utilisez à la place les nouvelles classes d’objets d’accès aux données (DAO), utilisez [CDaoException](../../mfc/reference/cdaoexception-class.md) à la place. Tous les noms de classe DAO ont « CDao » comme préfixe. Pour plus d’informations, consultez l’article [vue d’ensemble : programmation de base de données](../../data/data-access-programming-mfc-atl.md).  
  
 Les exceptions sont des cas d’exécution anormale impliquant des conditions en dehors du contrôle du programme, telles que la source de données ou les erreurs d’e/s réseau. Les erreurs que vous pouvez vous attendre à voir dans le cours normal de l’exécution de votre programme ne sont généralement pas considérées comme des exceptions.  
  
 Vous pouvez accéder à ces objets dans la portée d’un **CATCH** expression. Vous pouvez aussi lever `CDBException` objets à partir de votre propre code avec la `AfxThrowDBException` fonction globale.  
  
 Pour plus d’informations sur la gestion des exceptions en général, ou sur `CDBException` , consultez les articles [la gestion des exceptions (MFC)](../../mfc/exception-handling-in-mfc.md) et [Exceptions : Exceptions de base de données](../../mfc/exceptions-database-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CDBException`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdb.h  
  
##  <a name="m_nretcode"></a>CDBException::m_nRetCode  
 Contient un code d’erreur de type ODBC **et RETCODE contient** retourné par une fonction d’API (interface) de programmation d’application ODBC.  
  
### <a name="remarks"></a>Notes  
 Ce type inclut les codes SQL avec le préfixe définis par ODBC et préfixée par sa AFX_SQL définies par les classes de base de données. Pour un `CDBException`, ce membre contient une des valeurs suivantes :  
  
- **AFX_SQL_ERROR_API_CONFORMANCE** le pilote pour un `CDatabase::OpenEx` ou `CDatabase::Open` appel n’est pas conforme au niveau de conformité d’API ODBC requis 1 ( **SQL_OAC_LEVEL1**).  
  
- **AFX_SQL_ERROR_CONNECT_FAIL** Échec de la connexion à la source de données. Vous transmis un **NULL** `CDatabase` pointeur vers le constructeur de votre objet recordset et la tentative suivante pour créer une connexion basée sur `GetDefaultConnect` a échoué.  
  
- **AFX_SQL_ERROR_DATA_TRUNCATED** vous avez demandé plus de données que vous avez fourni le stockage pour. Pour plus d’informations sur l’augmentation du stockage des données fournies pour `CString` ou `CByteArray` des types de données, consultez la `nMaxLength` argument pour [RFX_Text](http://msdn.microsoft.com/library/de3c7581-d26c-40cb-81f3-c492ef4809f6) et [RFX_Binary](http://msdn.microsoft.com/library/908ff945-3ad0-43a1-9932-cdcdc8b14915) sous « Macros and Globals ».  
  
- **AFX_SQL_ERROR_DYNASET_NOT_SUPPORTED** un appel à `CRecordset::Open` Échec de la demande d’une feuille de réponse dynamique. Feuilles de réponse dynamiques ne sont pas pris en charge par le pilote.  
  
- **AFX_SQL_ERROR_EMPTY_COLUMN_LIST** tentative d’ouverture d’une table (ou vous avez donné n’a pas été identifié comme un appel de procédure ou **sélectionnez** instruction), mais aucune colonne identifié dans les appels de fonction exchange (RFX) de champs d’enregistrements dans votre `DoFieldExchange` remplacer.  
  
- **AFX_SQL_ERROR_FIELD_SCHEMA_MISMATCH** le type d’une fonction RFX dans votre `DoFieldExchange` remplacement n’est pas compatible avec le type de données dans le jeu d’enregistrements.  
  
- **AFX_SQL_ERROR_ILLEGAL_MODE** vous avez appelé `CRecordset::Update` sans appeler auparavant `CRecordset::AddNew` ou `CRecordset::Edit`.  
  
- **AFX_SQL_ERROR_LOCK_MODE_NOT_SUPPORTED** votre demande de verrouiller des enregistrements de mise à jour ne pourrait pas être satisfaite, car votre pilote ODBC ne prend pas en charge le verrouillage.  
  
- **AFX_SQL_ERROR_MULTIPLE_ROWS_AFFECTED apparaît** vous avez appelé `CRecordset::Update` ou **supprimer** pour une table sans clé unique et plusieurs enregistrements modifiés.  
  
- **AFX_SQL_ERROR_NO_CURRENT_RECORD** vous avez tenté de modifier ou supprimer un enregistrement supprimé précédemment. Vous devez accéder à un nouvel enregistrement en cours après une suppression.  
  
- **AFX_SQL_ERROR_NO_POSITIONED_UPDATES** votre demande pour une feuille de réponse dynamique n’a pas pu être satisfaite car votre pilote ODBC ne prend pas en charge de mises à jour positionnées.  
  
- **AFX_SQL_ERROR_NO_ROWS_AFFECTED** vous avez appelé `CRecordset::Update` ou **supprimer**, mais lorsque l’opération a commencé l’enregistrement n’est plus introuvable.  
  
- **AFX_SQL_ERROR_ODBC_LOAD_FAILED** tentative de chargement d’ODBC. Échec de la DLL ; Windows n’a pas été trouvé ou Impossible de charger cette DLL. Cette erreur est irrécupérable.  
  
- **AFX_SQL_ERROR_ODBC_V2_REQUIRED** votre demande d’une feuille de réponse dynamique ne pourrait pas être satisfaite, car un pilote ODBC conforme 2 niveau est requis.  
  
- **AFX_SQL_ERROR_RECORDSET_FORWARD_ONLY** une tentative de défilement n’a pas abouti car la source de données ne prend pas en charge le défilement arrière.  
  
- **AFX_SQL_ERROR_SNAPSHOT_NOT_SUPPORTED** un appel à `CRecordset::Open` Échec de la demande d’un instantané. Les instantanés ne sont pas pris en charge par le pilote. (Cela ne devrait se produire lorsque la bibliothèque de curseurs ODBC â €» ODBCCURS. DLL â » n’est pas présent.)  
  
- **AFX_SQL_ERROR_SQL_CONFORMANCE** le pilote pour un `CDatabase::OpenEx` ou `CDatabase::Open` appel n’est pas conforme au niveau de conformité de SQL ODBC requis « Minimum » ( **SQL_OSC_MINIMUM**).  
  
- **AFX_SQL_ERROR_SQL_NO_TOTAL** le pilote ODBC n’a pas pu spécifier la taille totale d’un `CLongBinary` valeur de données. L’opération a probablement échoué, car un bloc de mémoire globale n’a pas pu être préalloué.  
  
- **AFX_SQL_ERROR_RECORDSET_READONLY** vous avez tenté de mettre à jour un jeu d’enregistrements en lecture seule, ou la source de données est en lecture seule. Aucune opération de mise à jour ne peut être effectuée avec le jeu d’enregistrements ou `CDatabase` objet lui est associée.  
  
- **SQL_ERROR** échouée de la fonction. Le message d’erreur retourné par la fonction ODBC **SQLError** est stocké dans le **m_strError** membre de données.  
  
- **SQL_INVALID_HANDLE** fonction a échoué en raison d’un handle d’environnement non valide, un handle de connexion ou un descripteur d’instruction. Cela indique une erreur de programmation. Aucune information supplémentaire n’est disponible à partir de la fonction ODBC **SQLError**.  
  
 Les codes SQL avec le préfixe sont définis par ODBC. Les codes préfixée par sa AFX sont définies dans AFXDB. H, trouvé dans MFC\INCLUDE.  
  
##  <a name="m_strerror"></a>CDBException::m_strError  
 Contient une chaîne décrivant l’erreur qui a provoqué l’exception.  
  
### <a name="remarks"></a>Remarques  
 La chaîne décrit l’erreur en termes alphanumérique. Pour plus d’informations, consultez **m_strStateNativeOrigin**.  
  
##  <a name="m_strstatenativeorigin"></a>CDBException::m_strStateNativeOrigin  
 Contient une chaîne décrivant l’erreur qui a provoqué l’exception.  
  
### <a name="remarks"></a>Remarques  
 La chaîne est le formulaire « état : % s, natif : % ld, origine : % s », où les codes de format, dans l’ordre, sont remplacées par les valeurs qui décrivent :  
  
-   Le **SQLSTATE**, une chaîne contenant un code d’erreur à cinq caractères retourné dans la *szSqlState* paramètre de la fonction ODBC **SQLError**. **SQLSTATE** valeurs sont répertoriées dans l’annexe A, [Codes d’erreur ODBC](https://msdn.microsoft.com/library/ms714687.aspx), dans le *de référence du programmeur ODBC*. Exemple : « S0022 ».  
  
-   Le code d’erreur natif spécifique à la source de données retournées dans le *pfNativeError* paramètre de la **SQLError** (fonction). Exemple : 207.  
  
-   Le texte de message d’erreur retourné dans le *szErrorMsg* paramètre de la **SQLError** (fonction). Ce message se compose de plusieurs noms entre crochets. En tant qu’une erreur est transmise à l’utilisateur à partir de sa source, chaque composant ODBC (source de données, pilote, le Gestionnaire de pilote) ajoute son propre nom. Ces informations aident à identifier l’origine de l’erreur. Exemple : [Microsoft] [pilote ODBC SQL Server] [SQL Server]  
  
 Le framework interprète la chaîne d’erreur et place ses composants dans **m_strStateNativeOrigin**; si **m_strStateNativeOrigin** contient des informations pour plusieurs erreurs, les erreurs sont séparées par des sauts de ligne. Elle place le texte d’erreur alphanumérique en **m_strError**.  
  
 Pour plus d’informations sur les codes utilisées pour créer cette chaîne, consultez la [SQLError](https://msdn.microsoft.com/library/ms716312.aspx) de fonction dans le *de référence du programmeur ODBC*.  
  
### <a name="example"></a>Exemple  
  À partir d’ODBC : « Origine, natif :&207;, état : S0022 : [Microsoft] [pilote ODBC SQL Server] nom de colonne non valide [SQL Server] « Nom de colonne » »  
  
 Dans **m_strStateNativeOrigin**: « origine, natif :&207;, état : S0022 : [Microsoft] [pilote ODBC SQL Server] [SQL Server] »  
  
 Dans **m_strError**: « nom de colonne non valide « Nom de colonne » »  
  
## <a name="see-also"></a>Voir aussi  
 [CException (classe)](../../mfc/reference/cexception-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CDatabase (classe)](../../mfc/reference/cdatabase-class.md)   
 [CRecordset (classe)](../../mfc/reference/crecordset-class.md)   
 [CFieldExchange (classe)](../../mfc/reference/cfieldexchange-class.md)   
 [CRecordset::Update](../../mfc/reference/crecordset-class.md#update)   
 [CRecordset::Delete](../../mfc/reference/crecordset-class.md#delete)   
 [CException (classe)](../../mfc/reference/cexception-class.md)

