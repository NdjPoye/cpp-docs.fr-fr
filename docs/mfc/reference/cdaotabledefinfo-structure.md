---
title: Structure CDaoTableDefInfo | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoTableDefInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoTableDefInfo structure
- DAO (Data Access Objects), TableDefs collection
ms.assetid: c01ccebb-5615-434e-883c-4f60eac943dd
caps.latest.revision: 13
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
ms.openlocfilehash: 4d1ac5ca00f98f8c34332ce2eb1a180ab715e6ba
ms.lasthandoff: 02/24/2017

---
# <a name="cdaotabledefinfo-structure"></a>CDaoTableDefInfo, structure
Le `CDaoTableDefInfo` structure contient des informations sur un objet tabledef défini pour les objets d’accès aux données (DAO).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CDaoTableDefInfo  
{  
    CString m_strName;               // Primary  
    BOOL m_bUpdatable;               // Primary  
    long m_lAttributes;              // Primary  
    COleDateTime m_dateCreated;      // Secondary  
    COleDateTime m_dateLastUpdated;  // Secondary  
    CString m_strSrcTableName;       // Secondary  
    CString m_strConnect;            // Secondary  
    CString m_strValidationRule;     // All  
    CString m_strValidationText;     // All  
    long m_lRecordCount;             // All  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 `m_strName`  
 Identifiant de manière unique l’objet tabledef. Pour récupérer la valeur de cette propriété directement, appelez l’objet tabledef [GetName](../../mfc/reference/cdaotabledef-class.md#getname) fonction membre. Pour plus d’informations, consultez la rubrique « Nom de propriété » dans l’aide de DAO.  
  
 `m_bUpdatable`  
 Indique si des modifications peuvent être apportées à la table. La méthode rapide pour déterminer si une table est modifiable est d’ouvrir un `CDaoTableDef` pour la table et appeler l’objet [CanUpdate](../../mfc/reference/cdaotabledef-class.md#canupdate) fonction membre. `CanUpdate`Retourne toujours la valeur zéro (**TRUE**) pour un objet tabledef nouvellement créé et 0 (**FALSE**) pour un objet tabledef attaché. Un nouvel objet tabledef peut être ajouté uniquement à une base de données pour laquelle l’utilisateur actuel a accès en écriture. Si le tableau contient uniquement des champs assimilables, `CanUpdate` renvoie la valeur 0. Lorsqu’un ou plusieurs champs sont modifiables, `CanUpdate` retourne zéro. Vous pouvez modifier uniquement les champs modifiables. Pour plus d’informations, consultez la rubrique « Propriété actualisable » dans l’aide de DAO.  
  
 `m_lAttributes`  
 Spécifie les caractéristiques de la table représentée par l’objet tabledef. Pour récupérer les attributs en cours d’un objet tabledef, appelez sa [GetAttributes](../../mfc/reference/cdaotabledef-class.md#getattributes) fonction membre. La valeur retournée peut être une combinaison de ces constantes long (à l’aide de l’opérateur de bits OR (**|**) opérateur) :  
  
- **dbAttachExclusive** pour les bases de données qui utilisent le moteur de base de données Microsoft Jet, indique la table est une table attachée ouverte pour un usage exclusif.  
  
- **dbAttachSavePWD** pour les bases de données qui utilisent le moteur de base de données Microsoft Jet, indique que l’ID utilisateur et le mot de passe pour la table jointe sont enregistrés avec les informations de connexion.  
  
- **dbSystemObject** indique que la table est une table système fournie par le moteur de base de données Microsoft Jet. (En lecture seule.)  
  
- **dbHiddenObject** indique la table est une table masquée fournie par le moteur de base de données Microsoft Jet (pour une utilisation temporaire). (En lecture seule.)  
  
- **dbAttachedTable** indique que la table est une table attachée à partir d’une base de données non-ODBC, comme une base de données Paradox.  
  
- **dbAttachedODBC** indique que la table est une table attachée à partir d’une base de données ODBC, telles que Microsoft SQL Server.  
  
 `m_dateCreated`  
 Date et heure de que création de la table. Pour récupérer directement la date de création de la table, appelez la [GetDateCreated](../../mfc/reference/cdaotabledef-class.md#getdatecreated) fonction membre de la `CDaoTableDef` objet associé à la table. Pour plus d’informations, consultez les commentaires ci-dessous. Pour plus d’informations, consultez la rubrique « DateCreated, LastUpdated propriétés » dans l’aide de DAO.  
  
 `m_dateLastUpdated`  
 La date et l’heure de la dernière modification apportée à la conception de la table. Pour récupérer directement la date de dernière mise à jour de la table, appelez la [GetDateLastUpdated](../../mfc/reference/cdaotabledef-class.md#getdatelastupdated) fonction membre de la `CDaoTableDef` objet associé à la table. Pour plus d’informations, consultez les commentaires ci-dessous. Pour plus d’informations, consultez la rubrique « DateCreated, LastUpdated propriétés » dans l’aide de DAO.  
  
 *m_strSrcTableName*  
 Spécifie le nom d’une table attachée, le cas échéant. Pour extraire directement le nom de la table source, appelez le [GetSourceTableName](../../mfc/reference/cdaotabledef-class.md#getsourcetablename) fonction membre de la `CDaoTableDef` objet associé à la table.  
  
 `m_strConnect`  
 Fournit des informations sur la source d’une base de données ouverte. Vous pouvez vérifier cette propriété en appelant le [GetConnect](../../mfc/reference/cdaotabledef-class.md#getconnect) fonction membre de votre `CDaoTableDef` objet. Pour plus d’informations sur les chaînes de connexion, consultez la page `GetConnect`.  
  
 `m_strValidationRule`  
 Une valeur qui valide les données dans les champs tabledef lorsqu’ils sont modifiées ou ajoutées à une table. La validation est pris en charge uniquement pour les bases de données qui utilisent le moteur de base de données Microsoft Jet. Pour récupérer directement la règle de validation, appelez le [GetValidationRule](../../mfc/reference/cdaotabledef-class.md#getvalidationrule) fonction membre de la `CDaoTableDef` objet associé à la table. Pour plus d’informations, consultez la rubrique « Propriété ValidationRule » dans l’aide de DAO.  
  
 `m_strValidationText`  
 Une valeur qui spécifie le texte du message que votre application doit s’afficher si la règle de validation spécifiée par cette propriété n’est pas satisfaite. Pour plus d’informations, consultez la rubrique « Propriété ValidationRule » dans l’aide de DAO.  
  
 *m_lRecordCount*  
 Le nombre d’enregistrements accédés dans un objet tabledef. Cette propriété est en lecture seule. Pour extraire directement le nombre d’enregistrements, appelez le [GetRecordCount](../../mfc/reference/cdaotabledef-class.md#getrecordcount) fonction membre de la `CDaoTableDef` objet. La documentation de `GetRecordCount` décrit le nombre d’enregistrements supplémentaires. Notez que la récupération de ce nombre peut être une opération longue si la table contient de nombreux enregistrements.  
  
## <a name="remarks"></a>Notes  
 Cet objet est un objet de classe [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md). Les références au principal, secondaire et toutes les ci-dessus indiquent comment les informations sont renvoyées par le [GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) fonction membre dans la classe `CDaoDatabase`.  
  
 Les informations récupérées par le [CDaoDatabase::GetTableDefInfo](../../mfc/reference/cdaodatabase-class.md#gettabledefinfo) fonction membre est stockée dans un `CDaoTableDefInfo` structure. Appelez le `GetTableDefInfo` fonction membre de la `CDaoDatabase` objet dans dont la collection TableDefs de l’objet tabledef est stocké. `CDaoTableDefInfo`définit également un `Dump` builds de la fonction membre en mode de débogage. Vous pouvez utiliser `Dump` pour vider le contenu d’un `CDaoTableDefInfo` objet.  
  
 Les paramètres de date et d’heure sont dérivés de l’ordinateur sur lequel la table de base a été créée ou mises à jour. Dans un environnement multi-utilisateur, les utilisateurs doivent obtenir ces paramètres directement à partir du serveur de fichiers afin d’éviter des incohérences dans le DateCreated et les paramètres de propriété LastUpdated.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdao.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Classe d’objet CDaoTableDef](../../mfc/reference/cdaotabledef-class.md)   
 [CDaoDatabase (classe)](../../mfc/reference/cdaodatabase-class.md)

