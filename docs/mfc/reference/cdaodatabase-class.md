---
title: CDaoDatabase (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDaoDatabase
- AFXDAO/CDaoDatabase
- AFXDAO/CDaoDatabase::CDaoDatabase
- AFXDAO/CDaoDatabase::CanTransact
- AFXDAO/CDaoDatabase::CanUpdate
- AFXDAO/CDaoDatabase::Close
- AFXDAO/CDaoDatabase::Create
- AFXDAO/CDaoDatabase::CreateRelation
- AFXDAO/CDaoDatabase::DeleteQueryDef
- AFXDAO/CDaoDatabase::DeleteRelation
- AFXDAO/CDaoDatabase::DeleteTableDef
- AFXDAO/CDaoDatabase::Execute
- AFXDAO/CDaoDatabase::GetConnect
- AFXDAO/CDaoDatabase::GetName
- AFXDAO/CDaoDatabase::GetQueryDefCount
- AFXDAO/CDaoDatabase::GetQueryDefInfo
- AFXDAO/CDaoDatabase::GetQueryTimeout
- AFXDAO/CDaoDatabase::GetRecordsAffected
- AFXDAO/CDaoDatabase::GetRelationCount
- AFXDAO/CDaoDatabase::GetRelationInfo
- AFXDAO/CDaoDatabase::GetTableDefCount
- AFXDAO/CDaoDatabase::GetTableDefInfo
- AFXDAO/CDaoDatabase::GetVersion
- AFXDAO/CDaoDatabase::IsOpen
- AFXDAO/CDaoDatabase::Open
- AFXDAO/CDaoDatabase::SetQueryTimeout
- AFXDAO/CDaoDatabase::m_pDAODatabase
- AFXDAO/CDaoDatabase::m_pWorkspace
dev_langs:
- C++
helpviewer_keywords:
- database classes [C++], DAO
- CDaoDatabase class, vs. CDatabase class
- CDaoDatabase class, and workspace
- CDaoDatabase class
- CDatabase class, vs. CDaoDatabase class
ms.assetid: 8ff5b342-964d-449d-bef1-d0ff56aadf6d
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: c173ea0c0132752c08504053d9b00cdec8d3f69b
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cdaodatabase-class"></a>CDaoDatabase (classe)
Représente une connexion à une base de données, par l'intermédiaire de laquelle vous pouvez utiliser les données.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CDaoDatabase : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDaoDatabase::CDaoDatabase](#cdaodatabase)|Construit un objet `CDaoDatabase`. Appelez **ouvrir** pour connecter l’objet à une base de données.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDaoDatabase::CanTransact](#cantransact)|Retourne zéro si la base de données prend en charge les transactions.|  
|[CDaoDatabase::CanUpdate](#canupdate)|Retourne zéro si le `CDaoDatabase` objet est modifiable (pas en lecture seule).|  
|[CDaoDatabase::Close](#close)|Ferme la connexion de base de données.|  
|[CDaoDatabase::Create](#create)|Crée l’objet de base de données DAO sous-jacent et initialise le `CDaoDatabase` objet.|  
|[CDaoDatabase::CreateRelation](#createrelation)|Définit une relation entre les tables dans la base de données.|  
|[CDaoDatabase::DeleteQueryDef](#deletequerydef)|Supprime un objet querydef enregistré dans la collection QueryDefs de la base de données.|  
|[CDaoDatabase::DeleteRelation](#deleterelation)|Supprime une relation existante entre les tables dans la base de données.|  
|[CDaoDatabase::DeleteTableDef](#deletetabledef)|Supprime la définition d’une table dans la base de données. Cela supprime la table et toutes ses données.|  
|[CDaoDatabase::Execute](#execute)|Exécute une requête d’action. Appel de **Execute** pour une requête qui retourne des résultats lève une exception.|  
|[CDaoDatabase::GetConnect](#getconnect)|Retourne la chaîne de connexion utilisée pour connecter le `CDaoDatabase` objet à une base de données. Utilisé pour ODBC.|  
|[CDaoDatabase::GetName](#getname)|Retourne le nom de la base de données actuellement en cours d’utilisation.|  
|[CDaoDatabase::GetQueryDefCount](#getquerydefcount)|Retourne le nombre de requêtes définies pour la base de données.|  
|[CDaoDatabase::GetQueryDefInfo](#getquerydefinfo)|Retourne des informations sur une requête spécifiée définie dans la base de données.|  
|[CDaoDatabase::GetQueryTimeout](#getquerytimeout)|Retourne le nombre de secondes après la base de données des opérations de requête expire. Affecte toutes les ouvrir, ajouter de nouvelles, mises à jour et modifier les opérations et autres opérations sur les sources de données ODBC (uniquement) telles que **Execute** appels.|  
|[CDaoDatabase::GetRecordsAffected](#getrecordsaffected)|Retourne le nombre d’enregistrements affecté par la dernière mise à jour, modifier ou ajouter une opération ou par un appel à **Execute**.|  
|[CDaoDatabase::GetRelationCount](#getrelationcount)|Retourne le nombre de relations définies entre les tables dans la base de données.|  
|[CDaoDatabase::GetRelationInfo](#getrelationinfo)|Retourne des informations sur une relation spécifiée définie entre les tables dans la base de données.|  
|[CDaoDatabase::GetTableDefCount](#gettabledefcount)|Retourne le nombre de tables définies dans la base de données.|  
|[CDaoDatabase::GetTableDefInfo](#gettabledefinfo)|Retourne des informations sur une table spécifiée dans la base de données.|  
|[CDaoDatabase::GetVersion](#getversion)|Retourne la version du moteur de base de données associé à la base de données.|  
|[CDaoDatabase::IsOpen](#isopen)|Retourne zéro si le `CDaoDatabase` objet est actuellement connecté à une base de données.|  
|[CDaoDatabase::Open](#open)|Établit une connexion à une base de données.|  
|[CDaoDatabase::SetQueryTimeout](#setquerytimeout)|Définit le nombre de secondes après la base de données de requête opérations (sur des sources de données ODBC uniquement) expire. Affecte toutes les ouvre, ajouter de nouvelles, mettre à jour et suppressions.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CDaoDatabase::m_pDAODatabase](#m_pdaodatabase)|Pointeur vers l’objet de base de données DAO sous-jacent.|  
|[CDaoDatabase::m_pWorkspace](#m_pworkspace)|Un pointeur vers le [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) objet qui contient la base de données et définit son espace de transaction.|  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations sur les formats de base de données pris en charge, consultez la [GetName](../../mfc/reference/cdaoworkspace-class.md#getname) fonction membre. Vous pouvez avoir une ou plusieurs `CDaoDatabase` objets actifs en même temps dans un « espace de travail donné, « représenté par une [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) objet. L’espace de travail gère une collection d’objets de base de données ouverte, appelée la collection de bases de données.  
  
> [!NOTE]
>  Les classes de base de données DAO de MFC sont distinctes des classes de base de données MFC basées sur ODBC. Tous les noms de classe de base de données DAO ont le préfixe « CDao ». Classe `CDaoDatabase` fournit une interface similaire à celle de la classe ODBC [CDatabase](../../mfc/reference/cdatabase-class.md). La principale différence est que `CDatabase` accède au SGBD via Open Database Connectivity (ODBC) et un pilote ODBC pour ce système SGBD. `CDaoDatabase`accède aux données via un objet (DAO) basé sur le moteur de base de données Microsoft Jet. En général, les classes MFC basées sur DAO sont plus efficaces que les classes MFC basées sur ODBC ; les classes basées sur DAO peuvent accéder aux données, y compris via les pilotes ODBC, via son propre moteur de base de données. Les classes basées sur DAO prennent également en charge les opérations de langage de définition de données (DDL), telles que l’ajout de tables via les classes, sans avoir à appeler DAO directement.  
  
## <a name="usage"></a>Utilisation  
 Vous pouvez créer des objets de base de données implicitement, lorsque vous créez des objets recordset. Mais vous pouvez également créer explicitement les objets de base de données. Pour utiliser une base de données explicitement avec `CDaoDatabase`, effectuez une des opérations suivantes :  
  
-   Construire un `CDaoDatabase` objet, en passant un pointeur vers une ouverture [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) objet.  
  
-   Ou que vous construisez un `CDaoDatabase` objet sans spécifier l’espace de travail (MFC crée un objet d’espace de travail temporaire).  
  
 Pour créer un nouveau Microsoft Jet (. Base de données MDB), construire un `CDaoDatabase` objet et appeler ses [créer](#create) fonction membre. Faire *pas* appeler **Open** après **créer**.  
  
 Pour ouvrir une base de données existante, vous devez construire un `CDaoDatabase` objet et appeler ses [ouvrir](#open) fonction membre.  
  
 Une de ces techniques ajoute l’objet de base de données DAO à la collection de bases de données de l’espace de travail et ouvre une connexion aux données. Lorsque vous construisez puis [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), ou [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) objets pour l’exploitation de la base de données connectée, passer les constructeurs pour ces objets en un pointeur vers votre `CDaoDatabase` objet. Lorsque vous avez terminé à l’aide de la connexion, appelez le [fermer](#close) membre de fonction et de détruire le `CDaoDatabase` objet. **Fermer** ferme les jeux d’enregistrements que vous n’avez pas fermé précédemment.  
  
## <a name="transactions"></a>Transactions  
 Traitement des transactions de base de données est fourni au niveau de l’espace de travail, consultez le [BeginTrans](../../mfc/reference/cdaoworkspace-class.md#begintrans), [CommitTrans](../../mfc/reference/cdaoworkspace-class.md#committrans), et [restauration](../../mfc/reference/cdaoworkspace-class.md#rollback) fonctions membres de classe `CDaoWorkspace`.  
  
## <a name="odbc-connections"></a>Connexions ODBC  
 La méthode recommandée pour utiliser des sources de données ODBC consiste à associer les tables externes à un Microsoft Jet (. Base de données MDB).  
  
## <a name="collections"></a>Collections  
 Chaque base de données gère ses propres collections de tabledef, querydef, recordset et les objets de relation. Classe `CDaoDatabase` fournit les fonctions membres permettant de manipuler ces objets.  
  
> [!NOTE]
>  Les objets sont stockés dans DAO, pas dans l’objet de base de données MFC. MFC fournit des classes pour les objets tabledef, querydef et jeu d’enregistrements, mais pas pour les objets de relation.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CDaoDatabase`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdao.h  
  
##  <a name="cantransact"></a>CDaoDatabase::CanTransact  
 Appelez cette fonction membre pour déterminer si la base de données autorise les transactions.  
  
```  
BOOL CanTransact();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la base de données prend en charge les transactions ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Les transactions sont gérées dans l’espace de travail de la base de données.  
  
##  <a name="canupdate"></a>CDaoDatabase::CanUpdate  
 Appelez cette fonction membre pour déterminer si le `CDaoDatabase` objet autorise les mises à jour.  
  
```  
BOOL CanUpdate();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le `CDaoDatabase` objet autorise les mises à jour ; sinon, 0, qui indique soit que vous avez passé **TRUE** dans `bReadOnly` lorsque vous avez ouvert le `CDaoDatabase` objet ou que la base de données est en lecture seule. Consultez le [Open](#open) fonction membre.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations sur la mise à jour de la base de données, consultez la rubrique « Propriété actualisable » dans l’aide de DAO.  
  
##  <a name="cdaodatabase"></a>CDaoDatabase::CDaoDatabase  
 Construit un objet `CDaoDatabase`.  
  
```  
CDaoDatabase(CDaoWorkspace* pWorkspace = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *pWorkspace*  
 Un pointeur vers le `CDaoWorkspace` objet qui contiendra le nouvel objet de base de données. Si vous acceptez la valeur par défaut **NULL**, le constructeur crée un objet temporaire `CDaoWorkspace` objet qui utilise l’espace de travail DAO par défaut. Vous pouvez obtenir un pointeur vers l’objet espace de travail via le [m_pWorkspace](#m_pworkspace) membre de données.  
  
### <a name="remarks"></a>Notes  
 Après avoir construit l’objet, si vous créez un nouveau Microsoft Jet (. MDB), appelez l’objet [créer](#create) fonction membre. Si vous êtes à la place, ouvrir une base de données, appelez l’objet [Open](#open) fonction membre.  
  
 Lorsque vous avez terminé avec l’objet, vous devez appeler sa [fermer](#close) membre de fonction, puis détruisez le `CDaoDatabase` objet.  
  
 Vous trouverez peut-être facile d’incorporer la `CDaoDatabase` objet dans votre classe de document.  
  
> [!NOTE]
>  A `CDaoDatabase` objet est également créé implicitement si vous ouvrez un [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) objet sans passant un pointeur vers un existant `CDaoDatabase` objet. Cet objet de base de données est fermé lorsque vous fermez l’objet recordset.  
  
##  <a name="close"></a>CDaoDatabase::Close  
 Appelez cette fonction membre pour déconnecter une base de données et fermer les jeux d’enregistrements ouverts, tabledefs, querydefs associés à la base de données.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Remarques  
 Il est recommandé de fermer ces objets vous-même avant d’appeler cette fonction membre. Fermeture d’un `CDaoDatabase` objet supprime de la collection de bases de données dans le type [espace de travail](../../mfc/reference/cdaoworkspace-class.md). Étant donné que **fermer** ne détruit pas le `CDaoDatabase` de l’objet, vous pouvez réutiliser l’objet en ouvrant la même base de données ou une autre base de données.  
  
> [!CAUTION]
>  Appelez le [mise à jour](../../mfc/reference/cdaorecordset-class.md#update) fonction membre (s’il y modifications en attente) et la **fermer** fonction membre sur tous les objets recordset ouverts avant de fermer une base de données. Si vous quittez une fonction qui déclare [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) ou `CDaoDatabase` des objets sur la pile, la base de données est fermée, les modifications non enregistrées sont perdues, toutes les transactions en attente sont annulées, et les modifications en attente à vos données sont perdues.  
  
> [!CAUTION]
>  Si vous tentez de fermer un objet de base de données des objets recordset sont ouverts, ou si vous tentez de fermer un objet de l’espace de travail des objets de base de données appartenant à cet espace de travail spécifique sont ouverts, ces objets recordset seront fermés et les mises à jour en attente ou les modifications seront annulées. Si vous essayez de fermer un objet de l’espace de travail des objets de base de données appartenant à celle-ci sont ouverts, l’opération de fermeture de tous les objets de base de données appartenant à cet objet d’espace de travail spécifique, ce qui peut entraîner des objets recordset non fermés en cours de fermeture. Si vous ne fermez pas l’objet de base de données, MFC signale un échec d’assertion dans les versions debug.  
  
 Si l’objet de base de données est défini en dehors de la portée d’une fonction, et que vous quittez la fonction sans le fermer, l’objet de base de données reste ouverte jusqu'à ce qu’explicitement fermée ou le module dans lequel elle est définie est hors de portée.  
  
##  <a name="create"></a>CDaoDatabase::Create  
 Pour créer un nouveau Microsoft Jet (. MDB), appelez cette fonction membre après avoir construit un `CDaoDatabase` objet.  
  
```  
virtual void Create(
    LPCTSTR lpszName,  
    LPCTSTR lpszLocale = dbLangGeneral,  
    int dwOptions = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Une expression de chaîne qui est le nom du fichier de base de données que vous créez. Il peut être le chemin d’accès complet et le nom de fichier, tel que « C:\\\MYDB. MDB ». Vous devez fournir un nom. Si vous ne fournissez pas une extension de nom de fichier. MDB est ajouté. Si votre réseau prend en charge la convention d’appellation uniforme (UNC), vous pouvez également spécifier un chemin d’accès réseau, tels que «\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB ». Uniquement Microsoft Jet (. Fichiers de base de données MDB) peuvent être créés à l’aide de cette fonction membre. (Deux barres obliques inverses sont nécessaires dans les littéraux de chaîne, car «\\» est le caractère d’échappement de C++.)  
  
 `lpszLocale`  
 Une expression de chaîne utilisée pour spécifier l’ordre de classement pour la création de la base de données. La valeur par défaut est **dbLangGeneral**. Les valeurs possibles sont :  
  
- **dbLangGeneral** anglais, allemand, Français, portugais, italien et Espagnol moderne  
  
- **dbLangArabic** arabe  
  
- **dbLangCyrillic** russe  
  
- **dbLangCzech** tchèque  
  
- **dbLangDutch** néerlandais  
  
- **dbLangGreek** grec  
  
- **dbLangHebrew** hébreu  
  
- **dbLangHungarian** hongrois  
  
- **dbLangIcelandic** islandais  
  
- **dbLangNordic** langues scandinaves (Microsoft base de données moteur Jet version 1.0 uniquement)  
  
- **dbLangNorwdan** norvégien et danois  
  
- **dbLangPolish** polonais  
  
- **dbLangSpanish** espagnol  
  
- **dbLangSwedfin** suédois et finnois  
  
- **dbLangTurkish** turc  
  
 `dwOptions`  
 Entier qui indique une ou plusieurs options. Les valeurs possibles sont :  
  
- **dbEncrypt** créer une base de données.  
  
- **dbVersion10** créer une base de données avec la version de base de données Microsoft Jet 1.0.  
  
- **dbVersion11** créer une base de données avec la version de base de données Microsoft Jet 1.1.  
  
- **dbVersion20** créer une base de données avec la version de base de données Microsoft Jet 2.0.  
  
- **dbVersion30** créer une base de données avec la version de base de données Microsoft Jet 3.0.  
  
 Si vous omettez la constante de chiffrement, une base de données est créé. Vous pouvez spécifier qu’une seule constante de version. Si vous l’omettez, une base de données qui utilise la version de base de données Microsoft Jet 3.0 est créé.  
  
> [!CAUTION]
>  Si une base de données n’est pas chiffré, il est possible, même si l’implémentation de la sécurité d’utilisateur/mot de passe, pour lire directement le fichier binaire sur disque qui constitue la base de données.  
  
### <a name="remarks"></a>Remarques  
 **Créer** crée le fichier de base de données et l’objet de base de données DAO sous-jacent et initialise l’objet C++. L’objet est ajouté à la collection de bases de données de l’espace de travail associé. L’objet de base de données est dans un état ouvert. n’appelez pas **Open** après **créer**.  
  
> [!NOTE]
>  Avec **créer**, vous pouvez créer uniquement Microsoft Jet (. Bases de données MDB). Impossible de créer les bases de données ISAM ou bases de données ODBC.  
  
##  <a name="createrelation"></a>CDaoDatabase::CreateRelation  
 Appelez cette fonction membre pour établir une relation entre un ou plusieurs champs dans une table primaire dans la base de données et un ou plusieurs champs dans une table étrangère (une autre table dans la base de données).  
  
```  
void CreateRelation(
    LPCTSTR lpszName,  
    LPCTSTR lpszTable,  
    LPCTSTR lpszForeignTable,  
    long lAttributes,  
    LPCTSTR lpszField,  
    LPCTSTR lpszForeignField);  
  
void CreateRelation(CDaoRelationInfo& relinfo);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Le nom unique de l’objet relation. Le nom doit commencer par une lettre et peut contenir un maximum de 40 caractères. Il peut inclure des nombres et caractères de trait de soulignement mais ne peut pas inclure de signes de ponctuation ou d’espaces.  
  
 `lpszTable`  
 Le nom de la table primaire dans la relation. Si la table n’existe pas, MFC lève une exception de type [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 `lpszForeignTable`  
 Le nom de la table étrangère dans la relation. Si la table n’existe pas, MFC lève une exception de type `CDaoException`.  
  
 `lAttributes`  
 Valeur de type long qui contient des informations sur le type de relation. Vous pouvez utiliser cette valeur pour appliquer l’intégrité référentielle, entre autres choses. Vous pouvez utiliser l’opérateur de bits OR ( **|**) pour combiner les valeurs suivantes (à condition que la combinaison de sens) :  
  
- **dbRelationUnique** relation est un à un.  
  
- **Pourriez** relation n’est pas appliquée (aucune intégrité référentielle).  
  
- **dbRelationInherited** relation existe dans une base de données non courante qui contient les deux tables attachées.  
  
- **dbRelationUpdateCascade** mises à jour sont mises en cascade (pour plus d’informations sur cascades, consultez la section Notes).  
  
- **dbRelationDeleteCascade** suppressions sont mises en cascade.  
  
 *lpszField*  
 Un pointeur vers une chaîne terminée par le caractère null qui contient le nom d’un champ dans la table primaire (nommée par `lpszTable`).  
  
 *lpszForeignField*  
 Un pointeur vers une chaîne terminée par le caractère null qui contient le nom d’un champ dans la table (nommée par `lpszForeignTable`).  
  
 *relinfo*  
 Une référence à un [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) objet qui contient des informations sur la relation que vous souhaitez créer.  
  
### <a name="remarks"></a>Remarques  
 La relation ne peut pas impliquer une requête ou une table attachée à partir d’une base de données externe.  
  
 Utilisez la première version de la fonction lorsque la relation implique un champ dans chacune des deux tables. Utilisez la deuxième version lorsque la relation implique plusieurs champs. Le nombre maximal de champs dans une relation est 14.  
  
 Cette action crée un objet de relation DAO sous-jacent, mais c’est un détail d’implémentation MFC, car l’encapsulation de MFC objets relation est contenue dans la classe `CDaoDatabase`. MFC ne fournit pas une classe de relations.  
  
 Si vous définissez la relation d’attributs d’objet pour activer les opérations en cascade, le moteur de base de données automatiquement mises à jour ou supprime des enregistrements dans une ou plusieurs tables lorsque des modifications sont apportées dans les tables connexes de la clé primaires.  
  
 Par exemple, supposons que vous établissez une relation de suppression en cascade entre une table Customers et une table commandes. Lorsque vous supprimez des enregistrements de la table Customers, les enregistrements de la table de commandes associées à ce client sont également supprimés. En outre, si vous établissez des relations de suppression en cascade entre la table Orders et d’autres tables, enregistrements dans ces tables sont automatiquement supprimés lorsque vous supprimez des enregistrements de la table Customers.  
  
 Pour plus d’informations, consultez la rubrique « Méthode CreateRelation » dans l’aide de DAO.  
  
##  <a name="deletequerydef"></a>CDaoDatabase::DeleteQueryDef  
 Appelez cette fonction membre pour supprimer l’objet querydef spécifié : requête enregistrée, à partir de la `CDaoDatabase` collection QueryDefs de l’objet.  
  
```  
void DeleteQueryDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Le nom de la requête enregistrée à supprimer.  
  
### <a name="remarks"></a>Remarques  
 Ensuite, cette requête n’est plus définie dans la base de données.  
  
 Pour plus d’informations sur la création d’objets querydef, consultez la classe [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Un objet querydef est associé à un rôle particulier `CDaoDatabase` de l’objet lorsque vous construisez le `CDaoQueryDef` objet, en lui passant un pointeur à l’objet de base de données.  
  
##  <a name="deleterelation"></a>CDaoDatabase::DeleteRelation  
 Appelez cette fonction membre pour supprimer une relation existante à partir de la collection de Relations de l’objet de base de données.  
  
```  
void DeleteRelation(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Le nom de la relation à supprimer.  
  
### <a name="remarks"></a>Remarques  
 Ensuite, la relation n’est plus existe.  
  
 Pour plus d’informations, consultez la rubrique « Supprimer de la méthode » dans l’aide de DAO.  
  
##  <a name="deletetabledef"></a>CDaoDatabase::DeleteTableDef  
 Appelez cette fonction membre pour supprimer la table spécifiée et toutes ses données à partir de la `CDaoDatabase` collection TableDefs de l’objet.  
  
```  
void DeleteTableDef(LPCTSTR lpszName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Le nom de l’objet tabledef à supprimer.  
  
### <a name="remarks"></a>Remarques  
 Ensuite, cette table n’est plus définie dans la base de données.  
  
> [!NOTE]
>  Être très attention à ne pas supprimer les tables système.  
  
 Pour plus d’informations sur la création d’objets tabledef, consultez la classe [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Un objet tabledef est associé à un rôle particulier `CDaoDatabase` de l’objet lorsque vous construisez le `CDaoTableDef` objet, en lui passant un pointeur à l’objet de base de données.  
  
 Pour plus d’informations, consultez la rubrique « Supprimer de la méthode » dans l’aide de DAO.  
  
##  <a name="execute"></a>CDaoDatabase::Execute  
 Appelez cette fonction membre pour exécuter une requête action ou d’exécuter une instruction SQL sur la base de données.  
  
```  
void Execute(
    LPCTSTR lpszSQL,  
    int nOptions = dbFailOnError);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszSQL`  
 Pointeur vers une chaîne terminée par le caractère null qui contient une commande SQL valide à exécuter.  
  
 `nOptions`  
 Entier qui spécifie les options relatives à l’intégrité de la requête. Vous pouvez utiliser l’opérateur de bits OR ( **|**) pour combiner les constantes suivantes (fournie par la combinaison de sens — par exemple, vous devez associer pas **dbInconsistent** avec **dbConsistent**) :  
  
- **dbDenyWrite** refuser une autorisation d’écriture à d’autres utilisateurs.  
  
- **dbInconsistent** mises à jour incohérentes (par défaut).  
  
- **dbConsistent** mises à jour cohérentes.  
  
- **dbSQLPassThrough** SQL directes. Génère l’instruction SQL à passer à une source de données ODBC pour traitement.  
  
- **dbFailOnError** annuler les mises à jour si une erreur se produit.  
  
- **dbSeeChanges** génère une erreur d’exécution si un autre utilisateur modifie les données que vous modifiez.  
  
> [!NOTE]
>  Si les deux **dbInconsistent** et **dbConsistent** sont inclus ou si aucun n’est fourni, le résultat est la valeur par défaut. Pour obtenir une explication de ces constantes, consultez la rubrique « Méthode Execute » dans l’aide de DAO.  
  
### <a name="remarks"></a>Remarques  
 **Exécutez** fonctionne uniquement pour les requêtes d’action ou des requêtes SQL directes qui ne retournent pas de résultats. Il ne fonctionne pas pour les requêtes select qui retournent des enregistrements.  
  
 Pour une définition et les informations sur les requêtes d’action, consultez les rubriques « Requête Action » et « Méthode Execute » dans l’aide de DAO.  
  
> [!TIP]
>  Fonction d’une instruction SQL correcte et les autorisations appropriées, le **Execute** fonction membre n’échouera pas même si ce n’est pas une seule ligne peut être modifiée ou supprimée. Par conséquent, utilisez toujours la **dbFailOnError** option lorsque vous utilisez la **Execute** fonction membre pour exécuter une mise à jour ou supprimer des requêtes. Cette option provoque MFC lever une exception de type [CDaoException](../../mfc/reference/cdaoexception-class.md) et restaure toutes les modifications réussites si les enregistrements affectés sont verrouillés et ne peuvent pas être mis à jour ou supprimés. Notez que vous pouvez toujours appeler `GetRecordsAffected` pour voir combien d’enregistrements ont été affectés.  
  
 Appelez le [GetRecordsAffected](#getrecordsaffected) fonction membre de l’objet de base de données pour déterminer le nombre d’enregistrements affectés par la plus récente **Execute** appeler. Par exemple, `GetRecordsAffected` renvoie des informations sur le nombre d’enregistrements supprimés, mis à jour ou insérés lors de l’exécution d’une requête d’action. Le nombre retourné ne reflète pas les modifications lorsque cascade met à jour ou supprime des tables associées sont en vigueur.  
  
 **Exécutez** ne renvoie pas un jeu d’enregistrements. À l’aide de **Execute** sur une requête qui sélectionne des enregistrements provoque MFC lever une exception de type `CDaoException`. (Il existe aucune `ExecuteSQL` fonction membre analogue à `CDatabase::ExecuteSQL`.)  
  
##  <a name="getconnect"></a>CDaoDatabase::GetConnect  
 Appelez cette fonction membre pour extraire la chaîne de connexion utilisée pour se connecter les `CDaoDatabase` objet à une base de données ODBC ou ISAM.  
  
```  
CString GetConnect();
```  
  
### <a name="return-value"></a>Valeur de retour  
 La chaîne de connexion si [Open](#open) a été appelé sur une source de données ODBC ; sinon, une chaîne vide. Pour un Microsoft Jet (. Base de données MDB), la chaîne est toujours vide sauf si vous le configurez pour une utilisation avec le **dbSQLPassThrough** option utilisée avec les [Execute](#execute) fonction membre ou utilisé lors de l’ouverture d’un jeu d’enregistrements.  
  
### <a name="remarks"></a>Remarques  
 La chaîne fournit des informations sur la source d’une base de données ou une base de données utilisée dans une requête directe. La chaîne de connexion est composée d’un spécificateur de type de base de données et de zéro ou plusieurs paramètres séparés par des points-virgules.  
  
> [!NOTE]
>  À l’aide des classes DAO de MFC pour se connecter à une source de données via ODBC est moins efficace que la connexion via une table attachée.  
  
> [!NOTE]
>  La chaîne de connexion est utilisée pour passer des informations supplémentaires à ODBC et certains pilotes ISAM si nécessaire. Il n’est pas utilisé pour. Bases de données MDB. Pour les tables de base de base de données Microsoft Jet, la chaîne de connexion est une chaîne vide (« »), sauf quand vous l’utilisez pour une requête SQL directe comme décrit sous la valeur de retour ci-dessus.  
  
 Consultez le [Open](#open) fonction membre pour obtenir une description du mode de création de la chaîne de connexion. Une fois que la chaîne de connexion a été définie dans le **Open** appel, vous pouvez ultérieurement utiliser pour vérifier le paramètre pour déterminer le type, le chemin d’accès, la source de données utilisateur ODBC, mot de passe ou ID de la base de données.  
  
##  <a name="getname"></a>CDaoDatabase::GetName  
 Appelez cette fonction membre pour récupérer le nom de la base de données actuellement ouverte, qui est le nom d’un fichier de base de données existant ou le nom d’une source de données ODBC enregistré.  
  
```  
CString GetName();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le chemin d’accès complet et le nom de la base de données en cas de réussite ; dans le cas contraire, vide [CString](../../atl-mfc-shared/reference/cstringt-class.md).  
  
### <a name="remarks"></a>Notes  
 Si votre réseau prend en charge la convention d’appellation uniforme (UNC), vous pouvez également spécifier un chemin d’accès réseau, par exemple, «\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB ». (Deux barres obliques inverses sont nécessaires dans les littéraux de chaîne, car «\\» est le caractère d’échappement de C++.)  
  
 Peut, par exemple, vouloir afficher ce nom dans un titre. Si une erreur se produit alors que le nom est récupéré, MFC lève une exception de type [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
> [!NOTE]
>  Pour de meilleures performances lorsque les bases de données externes sont ouverts, nous vous recommandons de lier les tables de base de données externe à une base de données Microsoft Jet (. MDB) au lieu de se connecter directement à la source de données.  
  
 Le type de base de données est indiqué par le fichier ou le répertoire que le chemin d’accès pointe, comme suit :  
  
|Chemin d’accès pointe vers...|Type de base de données|  
|--------------------------|-------------------|  
|. Fichier MDB|Base de données Microsoft Jet (Microsoft Access)|  
|Répertoire contenant. Fichiers DBF|base de données dBASE|  
|Répertoire contenant. Fichier XLS|Base de données Microsoft Excel|  
|Répertoire contenant. Fichiers PDX|Base de données Paradox|  
|Répertoire qui contient les fichiers de base de données de texte au format correct|Base de données de format de texte|  
  
 Pour les bases de données ODBC comme SQL Server et Oracle, chaîne de connexion de la base de données identifie un nom de source de données (DSN) qui est inscrit par ODBC.  
  
##  <a name="getquerydefcount"></a>CDaoDatabase::GetQueryDefCount  
 Appelez cette fonction membre pour récupérer le nombre de requêtes définies dans la collection QueryDefs de la base de données.  
  
```  
short GetQueryDefCount();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nombre de requêtes définies dans la base de données.  
  
### <a name="remarks"></a>Remarques  
 `GetQueryDefCount`est utile si vous devez effectuer une boucle sur toutes les querydefs dans la collection QueryDefs. Pour obtenir des informations sur une requête dans la collection, consultez [fonction membre GetQueryDefInfo](#getquerydefinfo).  
  
##  <a name="getquerydefinfo"></a>CDaoDatabase::GetQueryDefInfo  
 Appelez cette fonction membre pour obtenir différents types d’informations sur une requête définie dans la base de données.  
  
```  
void GetQueryDefInfo(
    int nIndex,  
    CDaoQueryDefInfo& querydefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetQueryDefInfo(
    LPCTSTR lpszName,  
    CDaoQueryDefInfo& querydefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de la requête prédéfinie dans la collection QueryDefs de la base de données, pour effectuer des recherches par index.  
  
 *querydefinfo*  
 Une référence à un [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) objet qui retourne les informations demandées.  
  
 `dwInfoOptions`  
 Options qui spécifient les informations sur le jeu d’enregistrements à récupérer. Les options disponibles sont répertoriées ici, ainsi que leur cause la fonction retourne le jeu d’enregistrements :  
  
- `AFX_DAO_PRIMARY_INFO`(Par défaut) Nom, Type  
  
- `AFX_DAO_SECONDARY_INFO`Plus les informations primaire : Date de création, Date de dernière mise à jour, renvoie les enregistrements, modifiable  
  
- `AFX_DAO_ALL_INFO`Informations primaires et secondaires plues : SQL, se connecter, ODBCTimeout  
  
 `lpszName`  
 Chaîne contenant le nom d’une requête définie dans la base de données pour effectuer des recherches par nom.  
  
### <a name="remarks"></a>Remarques  
 Deux versions de la fonction sont fournies afin de pouvoir sélectionner une requête par l’index dans la collection QueryDefs de la base de données ou par le nom de la requête.  
  
 Pour obtenir une description des informations renvoyées dans *querydefinfo*, consultez la [CDaoQueryDefInfo](../../mfc/reference/cdaoquerydefinfo-structure.md) structure. Cette structure possède des membres qui correspondent aux éléments d’information répertoriées ci-dessus dans la description de `dwInfoOptions`. Si vous demandez des informations d’un niveau, vous obtenez tous les niveaux d’informations préalables.  
  
##  <a name="getquerytimeout"></a>CDaoDatabase::GetQueryTimeout  
 Appelez cette fonction membre pour récupérer le nombre actuel de secondes avant expiration des opérations ultérieures sur la base de données connectée.  
  
```  
short GetQueryTimeout();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un entier court qui contient la valeur de délai d’expiration en secondes.  
  
### <a name="remarks"></a>Notes  
 Une opération peut expirer en raison de problèmes d’accès réseau, le temps de traitement de requête excessive et ainsi de suite. Lorsque le paramètre est en vigueur, il affecte toutes les ajouter de nouvelles, mettre à jour et supprimer des opérations sur les jeux d’enregistrements associé à ce `CDaoDatabase` objet. Vous pouvez modifier le paramètre de délai d’expiration en cours en appelant [SetQueryTimeout](#setquerytimeout). Modification de la valeur du délai de requête pour un jeu d’enregistrements après ouverture ne modifie pas la valeur de l’objet recordset. Par exemple, ultérieur [déplacer](../../mfc/reference/cdaorecordset-class.md#move) opérations n’utilisent pas la nouvelle valeur. La valeur par défaut est initialement définie lorsque le moteur de base de données est initialisé.  
  
 La valeur par défaut pour les délais d’expiration de la requête est effectuée à partir du Registre Windows. S’il n’existe aucun paramètre du Registre, la valeur par défaut est de 60 secondes. Pas de toutes les bases de données prennent en charge la possibilité de définir une valeur de délai d’attente de requête. Si vous définissez une valeur de délai d’expiration de requête de 0, aucun délai d’expiration se produit ; et la communication avec la base de données peut cesser de répondre. Ce comportement peut être utile lors du développement. Si l’appel échoue, MFC lève une exception de type [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Pour plus d’informations, consultez la rubrique « Propriété QueryTimeout » dans l’aide de DAO.  
  
##  <a name="getrecordsaffected"></a>CDaoDatabase::GetRecordsAffected  
 Appelez cette fonction membre pour déterminer le nombre d’enregistrements affectés par le dernier appel de la [Execute](#execute) fonction membre.  
  
```  
long GetRecordsAffected();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Entier long contenant le nombre d’enregistrements affectés.  
  
### <a name="remarks"></a>Remarques  
 La valeur retournée inclut le nombre d’enregistrements supprimés, mis à jour ou insérées par une requête d’action exécuter avec **Execute**. Le nombre retourné ne reflète pas les modifications lorsque cascade met à jour ou supprime des tables associées sont en vigueur.  
  
 Pour plus d’informations, consultez la rubrique « Propriété RecordsAffected » dans l’aide de DAO.  
  
##  <a name="getrelationcount"></a>CDaoDatabase::GetRelationCount  
 Appelez cette fonction membre pour obtenir le nombre de relations définies entre les tables dans la base de données.  
  
```  
short GetRelationCount();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de relations définies entre les tables dans la base de données.  
  
### <a name="remarks"></a>Remarques  
 **GetRelationCount** est utile si vous devez effectuer une boucle sur toutes les relations définies dans la collection de Relations de la base de données. Pour obtenir des informations sur une relation donnée dans la collection, consultez [GetRelationInfo](#getrelationinfo).  
  
 Pour illustrer le concept d’une relation, considérez une table fournisseurs et une table de produits, ce qui peut avoir une relation un-à-plusieurs. Dans cette relation, un fournisseur peut fournir plusieurs produits. Autres relations sont un à un et plusieurs-à-plusieurs.  
  
##  <a name="getrelationinfo"></a>CDaoDatabase::GetRelationInfo  
 Appelez cette fonction membre pour obtenir des informations sur une relation spécifiée dans la collection de Relations de la base de données.  
  
```  
void GetRelationInfo(
    int nIndex,  
    CDaoRelationInfo& relinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetRelationInfo(
    LPCTSTR lpszName,  
    CDaoRelationInfo& relinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 L’index de l’objet relation dans la collection de Relations de la base de données, pour effectuer des recherches par index.  
  
 *relinfo*  
 Une référence à un [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) objet qui retourne les informations demandées.  
  
 `dwInfoOptions`  
 Options qui spécifient les informations sur la relation à récupérer. Les options disponibles sont répertoriées ici, ainsi que leur cause la fonction retourne sur la relation :  
  
- `AFX_DAO_PRIMARY_INFO`(Par défaut) Table étrangère nom, Table,  
  
- `AFX_DAO_SECONDARY_INFO`Attributs, les informations de champ  
  
 Les informations de champ sont un [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) objet contenant les champs de la table primaire impliquée dans la relation.  
  
 `lpszName`  
 Chaîne contenant le nom de l’objet relation, pour effectuer des recherches par nom.  
  
### <a name="remarks"></a>Remarques  
 Deux versions de cette fonction fournissent l’accès par index ou par nom. Pour obtenir une description des informations renvoyées dans *relinfo*, consultez la [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) structure. Cette structure possède des membres qui correspondent aux éléments d’information répertoriées ci-dessus dans la description de `dwInfoOptions`. Si vous demandez des informations à un niveau, vous obtenez également des informations à des niveaux précédents ainsi.  
  
> [!NOTE]
>  Si vous définissez la relation d’attributs d’objet pour activer les opérations en cascade ( **dbRelationUpdateCascades** ou **dbRelationDeleteCascades**), le moteur de base de données Microsoft Jet automatiquement des mises à jour ou supprime des enregistrements dans une ou plusieurs autres tables lorsque des modifications sont apportées à associées des tables de clé primaire. Par exemple, supposons que vous établissez une relation de suppression en cascade entre une table Customers et une table commandes. Lorsque vous supprimez des enregistrements de la table Customers, les enregistrements de la table de commandes associées à ce client sont également supprimés. En outre, si vous établissez des relations de suppression en cascade entre la table Orders et d’autres tables, enregistrements dans ces tables sont automatiquement supprimés lorsque vous supprimez des enregistrements de la table Customers.  
  
##  <a name="gettabledefcount"></a>CDaoDatabase::GetTableDefCount  
 Appelez cette fonction membre pour récupérer le nombre de tables définies dans la base de données.  
  
```  
short GetTableDefCount();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de tabledefs définis dans la base de données.  
  
### <a name="remarks"></a>Remarques  
 `GetTableDefCount`est utile si vous devez effectuer une boucle sur tous les objets TableDef dans la collection TableDefs de la base de données. Pour obtenir des informations sur une table de la collection, consultez [GetTableDefInfo](#gettabledefinfo).  
  
##  <a name="gettabledefinfo"></a>CDaoDatabase::GetTableDefInfo  
 Appelez cette fonction membre pour obtenir différents types d’informations sur une table définie dans la base de données.  
  
```  
void GetTableDefInfo(
    int nIndex,  
    CDaoTableDefInfo& tabledefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);

 
void GetTableDefInfo(
    LPCTSTR lpszName,  
    CDaoTableDefInfo& tabledefinfo,  
    DWORD dwInfoOptions = AFX_DAO_PRIMARY_INFO);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 L’index de l’objet tabledef dans la collection TableDefs de la base de données, pour effectuer des recherches par index.  
  
 `tabledefinfo`  
 Une référence à un [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) objet qui retourne les informations demandées.  
  
 `dwInfoOptions`  
 Options qui spécifient les informations sur la table à récupérer. Les options disponibles sont répertoriées ici, ainsi que leur cause la fonction retourne sur la relation :  
  
- `AFX_DAO_PRIMARY_INFO`(Par défaut) Nom mis à jour, attributs  
  
- `AFX_DAO_SECONDARY_INFO`Plus les informations primaire : Date de création, Date dernière mise à jour, nom de la Table Source, de se connecter  
  
- `AFX_DAO_ALL_INFO`Informations primaires et secondaires plues : nombre d’enregistrements de règle de Validation, le texte de Validation,  
  
 `lpszName`  
 Le nom de l’objet tabledef, pour effectuer des recherches par nom.  
  
### <a name="remarks"></a>Remarques  
 Deux versions de la fonction sont fournies afin de pouvoir sélectionner une table par l’index dans la collection TableDefs de la base de données ou par le nom de la table.  
  
 Pour obtenir une description des informations renvoyées dans `tabledefinfo`, consultez la [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) structure. Cette structure possède des membres qui correspondent aux éléments d’information répertoriées ci-dessus dans la description de `dwInfoOptions`. Si vous demandez des informations à un niveau, vous obtenez des informations pour les niveaux de préalables.  
  
> [!NOTE]
>  La `AFX_DAO_ALL_INFO` option fournit des informations qui peuvent être lentes à obtenir. Dans ce cas, les enregistrements dans la table d’inventaire peut être beaucoup de temps si de nombreux enregistrements.  
  
##  <a name="getversion"></a>CDaoDatabase::GetVersion  
 Appelez cette fonction membre pour déterminer la version du fichier de base de données Microsoft Jet.  
  
```  
CString GetVersion();
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) qui indique la version du fichier de base de données associé à l’objet.  
  
### <a name="remarks"></a>Remarques  
 La valeur renvoyée représente le numéro de version sous la forme « major.minor » ; par exemple, « 3.0 ». Le numéro de version du produit (par exemple, version 3.0) comprend le numéro de version (3), une période et le numéro de version (0). Les versions de date sont 1.0, 1.1, 2.0 et 3.0.  
  
 Pour plus d’informations, consultez la rubrique « Propriété de Version » dans l’aide de DAO.  
  
##  <a name="isopen"></a>CDaoDatabase::IsOpen  
 Appelez cette fonction membre pour déterminer si le `CDaoDatabase` objet est actuellement ouverte sur une base de données.  
  
```  
BOOL IsOpen() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le `CDaoDatabase` objet est actuellement ouvert ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="m_pdaodatabase"></a>CDaoDatabase::m_pDAODatabase  
 Contient un pointeur vers l’interface OLE de l’objet de base de données DAO sous-jacent le `CDaoDatabase` objet.  
  
### <a name="remarks"></a>Remarques  
 Utilisez ce pointeur si vous avez besoin d’accéder à l’interface DAO directement.  
  
 Pour plus d’informations sur l’appel de DAO directement, consultez [Note technique 54](../../mfc/tn054-calling-dao-directly-while-using-mfc-dao-classes.md).  
  
##  <a name="m_pworkspace"></a>CDaoDatabase::m_pWorkspace  
 Contient un pointeur vers le [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md) objet qui contient l’objet de base de données.  
  
### <a name="remarks"></a>Remarques  
 Utilisez ce pointeur si vous avez besoin d’accéder directement à l’espace de travail, par exemple, pour obtenir des pointeurs sur les autres objets de base de données de collection de bases de données de l’espace de travail.  
  
##  <a name="open"></a>CDaoDatabase::Open  
 Vous devez appeler cette fonction membre pour initialiser un nouvellement construit `CDaoDatabase` objet qui représente une base de données.  
  
```  
virtual void Open(
    LPCTSTR lpszName,  
    BOOL bExclusive = FALSE,  
    BOOL bReadOnly = FALSE,  
    LPCTSTR lpszConnect = _T(""));
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Une expression de chaîne qui est le nom d’un Microsoft Jet existantes (. Fichier de base de données MDB). Si le nom de fichier a une extension, il est nécessaire. Si votre réseau prend en charge la convention d’appellation uniforme (UNC), vous pouvez également spécifier un chemin d’accès réseau, tels que «\\\\\\\MYSERVER\\\MYSHARE\\\MYDIR\\\MYDB. MDB ». (Deux barres obliques inverses sont nécessaires dans les littéraux de chaîne, car «\\» est le caractère d’échappement de C++.)  
  
 Certaines considérations s’appliquent lorsque vous utilisez `lpszName`. Si elle :  
  
-   Fait référence à une base de données est déjà ouverte pour un accès exclusif par un autre utilisateur, MFC les lève une exception de type [CDaoException](../../mfc/reference/cdaoexception-class.md). Intercepter cette exception pour informer vos utilisateurs que la base de données n’est pas disponible.  
  
-   Est une chaîne vide (« ») et *lpszConnect* est « ODBC », une boîte de dialogue répertoriant inscrits tous les noms de source de données ODBC s’affiche afin que l’utilisateur peut sélectionner une base de données. Vous devez éviter les connexions directes à des sources de données ODBC ; Utilisez une table attachée à la place.  
  
-   Dans le cas contraire, ne fait pas référence à une base de données existante ou une valide nom de la source de données ODBC, MFC les lève une exception de type `CDaoException`.  
  
> [!NOTE]
>  Pour plus d’informations sur les codes d’erreur DAO, consultez la DAOERR. Fichier H. Pour plus d’informations, consultez la rubrique « Erreurs d’accès aux données récupérable » dans l’aide de DAO.  
  
 `bExclusive`  
 Valeur booléenne qui est **TRUE** si la base de données doit être ouverte pour un accès exclusif (non partagé) et **FALSE** si la base de données doit être ouvert pour l’accès partagé. Si vous omettez cet argument, la base de données est ouverte pour un accès partagé.  
  
 `bReadOnly`  
 Valeur booléenne qui est **TRUE** si la base de données doit être ouverte pour un accès en lecture seule et **FALSE** si la base de données doit être ouvert pour un accès en lecture/écriture. Si vous omettez cet argument, la base de données est ouverte pour un accès en lecture/écriture. Tous les jeux d’enregistrements dépendants hérite de cet attribut.  
  
 `lpszConnect`  
 Une expression de chaîne utilisée pour l’ouverture de la base de données. Cette chaîne constitue ODBC connecter des arguments. Vous devez fournir les arguments exclusifs et en lecture seule pour fournir une chaîne source. Si la base de données est une base de données Microsoft Jet (. (MDB), cette chaîne est vide (« »). La syntaxe de la valeur par défaut : **_T**(« »), fournit la portabilité pour Unicode comme ANSI pour les builds de votre application.  
  
### <a name="remarks"></a>Remarques  
 **Ouvrez** associe la base de données à l’objet DAO sous-jacent. Vous ne pouvez pas utiliser l’objet de base de données pour construire le jeu d’enregistrements, tabledef ou querydef (objets) jusqu'à ce qu’il est initialisé. **Ouvrez** ajoute l’objet de base de données à la collection de bases de données de l’espace de travail associé.  
  
 Utiliser les paramètres comme suit :  
  
-   Si vous ouvrez un Microsoft Jet (. Base de données MDB), utilisez la `lpszName` paramètre et passez une chaîne vide pour le `lpszConnect` paramètre ou passez une chaîne de mot de passe sous la forme « ; PWD = mot de passe » si la base de données est protégé par mot de passe (. MDB bases de données uniquement).  
  
-   Si vous ouvrez une source de données ODBC, passez une chaîne de connexion ODBC valide dans `lpszConnect` et une chaîne vide dans `lpszName`.  
  
 Pour plus d’informations, consultez la rubrique « Méthode OpenDatabase » dans l’aide de DAO.  
  
> [!NOTE]
>  Pour de meilleures performances lorsqu’ils accèdent à des bases de données externes, y compris les bases de données ISAM et sources de données ODBC, il est recommandé de lier les tables de base de données externe à une base de données de moteur Microsoft Jet (. MDB) au lieu de se connecter directement à la source de données.  
  
 Il est possible qu’une tentative de connexion à expirer si, par exemple, l’hôte de SGBD n’est pas disponible. Si la tentative de connexion échoue, **Open** lève une exception de type [CDaoException](../../mfc/reference/cdaoexception-class.md).  
  
 Les autres notes s’appliquent uniquement aux bases de données ODBC :  
  
 Si la base de données est une base de données ODBC et les paramètres dans votre **Open** appel ne contiennent pas suffisamment d’informations pour établir la connexion, le pilote ODBC ouvre une boîte de dialogue pour obtenir les informations nécessaires auprès de l’utilisateur. Lorsque vous appelez **Open**, votre chaîne de connexion, `lpszConnect`, est stocké en privé et est disponible en appelant le [GetConnect](#getconnect) fonction membre.  
  
 Si vous le souhaitez, vous pouvez ouvrir votre propre boîte de dialogue avant d’appeler **ouvrir** pour obtenir des informations à partir de l’utilisateur, comme un mot de passe, puis ajouter ces informations à la chaîne de connexion que vous passez à **ouvrir**. Vous pouvez également enregistrer la chaîne de connexion que vous passez (dans le Registre Windows) afin de pouvoir les réutiliser la prochaine fois que votre application appelle **Open** sur une `CDaoDatabase` objet.  
  
 Vous pouvez également utiliser la chaîne de connexion pour plusieurs niveaux d’autorisation de connexion (chacun correspondant à un autre `CDaoDatabase` objet) ou avec d’autres informations spécifiques à la base de données.  
  
##  <a name="setquerytimeout"></a>CDaoDatabase::SetQueryTimeout  
 Appelez cette fonction membre pour remplacer le nombre de secondes avant les opérations suivantes sur le délai d’attente de base de données connectée.  
  
```  
void SetQueryTimeout(short nSeconds);
```  
  
### <a name="parameters"></a>Paramètres  
 `nSeconds`  
 Le nombre de secondes avant une tentative de requête arrive à expiration.  
  
### <a name="remarks"></a>Notes  
 Une opération peut expirer en raison de problèmes d’accès réseau, le temps de traitement de requête excessive et ainsi de suite. Appelez `SetQueryTimeout` avant d’ouvrir le jeu d’enregistrements ou avant d’appeler le jeu d’enregistrements [AddNew](../../mfc/reference/cdaorecordset-class.md#addnew), [mise à jour](../../mfc/reference/cdaorecordset-class.md#update), ou [supprimer](../../mfc/reference/cdaorecordset-class.md#delete) fonctions membres si vous souhaitez modifier la valeur du délai de requête. Le paramètre affecte toutes les [Open](../../mfc/reference/cdaorecordset-class.md#open), `AddNew`, **mise à jour**, et **supprimer** les appels à des jeux d’enregistrements associé à ce `CDaoDatabase` objet. Modification de la valeur du délai de requête pour un jeu d’enregistrements après ouverture ne modifie pas la valeur de l’objet recordset. Par exemple, ultérieur [déplacer](../../mfc/reference/cdaorecordset-class.md#move) opérations n’utilisent pas la nouvelle valeur.  
  
 La valeur par défaut pour les délais d’expiration est de 60 secondes. Pas de toutes les bases de données prennent en charge la possibilité de définir une valeur de délai d’attente de requête. Si vous définissez une valeur de délai d’expiration de requête de 0, aucun délai d’expiration se produit ; la communication avec la base de données peut cesser de répondre. Ce comportement peut être utile lors du développement.  
  
 Pour plus d’informations, consultez la rubrique « Propriété QueryTimeout » dans l’aide de DAO.  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CDaoWorkspace (classe)](../../mfc/reference/cdaoworkspace-class.md)   
 [CDaoRecordset (classe)](../../mfc/reference/cdaorecordset-class.md)   
 [Classe d’objet CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoQueryDef (classe)](../../mfc/reference/cdaoquerydef-class.md)   
 [CDatabase (classe)](../../mfc/reference/cdatabase-class.md)   
 [CDaoException (classe)](../../mfc/reference/cdaoexception-class.md)

