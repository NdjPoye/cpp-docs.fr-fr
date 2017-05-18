---
title: CDaoFieldInfo (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Fields collection
- CDaoFieldInfo structure
ms.assetid: 91b13e3f-bdb8-440c-86fc-ba4181ea0182
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 15db0c56480dfefb9fc8806c08596e37c7d38eb2
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cdaofieldinfo-structure"></a>CDaoFieldInfo, structure
Le `CDaoFieldInfo` structure contient des informations sur un objet de champ définie pour les objets d’accès aux données (DAO).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CDaoFieldInfo  
{  
    CString m_strName;           // Primary  
    short m_nType;               // Primary  
    long m_lSize;                // Primary  
    long m_lAttributes;          // Primary  
    short m_nOrdinalPosition;    // Secondary  
    BOOL m_bRequired;            // Secondary  
    BOOL m_bAllowZeroLength;     // Secondary  
    long m_lCollatingOrder;      // Secondary  
    CString m_strForeignName;    // Secondary  
    CString m_strSourceField;    // Secondary  
    CString m_strSourceTable;    // Secondary  
    CString m_strValidationRule; // All  
    CString m_strValidationText; // All  
    CString m_strDefaultValue;   // All  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 `m_strName`  
 Identifie l’objet de champ. Pour plus d’informations, consultez la rubrique « Nom de propriété » dans l’aide de DAO.  
  
 `m_nType`  
 Une valeur qui indique le type de données du champ. Pour plus d’informations, consultez la rubrique « Type Property » dans l’aide de DAO. La valeur de cette propriété peut être une des opérations suivantes :  
  
- **dbBoolean** Oui/Non, même en tant que **TRUE**/**FALSE**  
  
- **dbByte** octets  
  
- **dbInteger** court  
  
- **dbLong** Long  
  
- **dbCurrency** devise ; consultez MFC classe [COleCurrency](../../mfc/reference/colecurrency-class.md)  
  
- **dbSingle** unique  
  
- **dbDouble** Double  
  
- **dbDate** Date/heure ; voir MFC classe [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md)  
  
- **dbText** texte ; consultez MFC classe [CString](../../atl-mfc-shared/reference/cstringt-class.md)  
  
- **dbLongBinary** binaire longue (objet OLE), vous souhaiterez peut-être utiliser la classe MFC [CByteArray](../../mfc/reference/cbytearray-class.md) au lieu de la classe `CLongBinary` en tant que `CByteArray` est plus riche et plus facile à utiliser.  
  
- **dbMemo** avoir ; voir MFC, classe`CString`  
  
- **dbGUID** un identificateur global Unique identificateur/universellement Unique utilisée avec les appels de procédure distante. Pour plus d’informations, consultez la rubrique « Type Property » dans l’aide de DAO.  
  
> [!NOTE]
>  N’utilisez pas de types de données de chaîne pour les données binaires. Ainsi, vos données à passer à la couche de traduction Unicode/ANSI, ce qui entraîne une charge accrue et inattendue éventuellement la traduction.  
  
 *m_lSize*  
 Une valeur qui indique la taille maximale, en octets, d’un objet DAO champ qui contient le texte ou la taille fixe d’un objet de champ qui contient du texte ou des valeurs numériques. Pour plus d’informations, consultez la rubrique « Propriété Size » dans l’aide de DAO. Taille peut être une des valeurs suivantes :  
  
|Type|Taille (octets)|Description|  
|----------|--------------------|-----------------|  
|**dbBoolean**|1 octet|Oui/non (identique à la valeur True/False)|  
|**dbByte**|1|Byte|  
|**dbInteger**|2|Entier|  
|**dbLong**|4|Longue|  
|**dbCurrency**|8|Devise ([COleCurrency](../../mfc/reference/colecurrency-class.md))|  
|**dbSingle**|4|Single|  
|**dbDouble**|8|Double|  
|**dbDate**|8|Date/heure ([COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md))|  
|**dbText**|1 - 255|Texte ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbLongBinary**|0|Binaire long (objet OLE ; [CByteArray](../../mfc/reference/cbytearray-class.md); utilisez à la place de `CLongBinary`)|  
|**dbMemo**|0|Mémo ([CString](../../atl-mfc-shared/reference/cstringt-class.md))|  
|**dbGUID**|16|Un identificateur global Unique identificateur/universellement Unique utilisée avec les appels de procédure distante.|  
  
 `m_lAttributes`  
 Spécifie les caractéristiques d’un objet de champ contenus dans un objet tabledef, recordset, querydef ou objet index. La valeur retournée peut être une somme de ces constantes, créés avec le C++ au niveau du bit OR (**|**) opérateur :  
  
- **dbFixedField** la taille du champ est fixe (valeur par défaut pour les champs numériques).  
  
- **dbVariableField** la taille du champ est variable (champs texte uniquement).  
  
- **dbAutoIncrField** la valeur du champ pour les nouveaux enregistrements est automatiquement incrémentée d’un entier long unique qui ne peut pas être modifié. Prise en charge uniquement pour les tables de base de données Microsoft Jet.  
  
- **dbUpdatableField** la valeur du champ peut être modifiée.  
  
- **dbDescending** le champ est trié dans l’ordre décroissant (Z - A ou 0-100) order (s’applique uniquement à un objet de champ dans une collection de champs d’un objet index ; dans MFC, les objets eux-mêmes contenus dans les objets tabledef des index). Si vous omettez cette constante, le champ est trié dans l’ordre croissant (A - Z ou 0 - 100) ordre (par défaut).  
  
 Lors de la vérification de la définition de cette propriété, vous pouvez utiliser le C++ au niveau du bit- et opérateur (**&**) pour tester un attribut spécifique. Lorsque vous définissez plusieurs attributs, vous pouvez les combiner en combinant les constantes appropriées avec l’opérateur de bits OR (**|**) opérateur. Pour plus d’informations, consultez la rubrique « Attributs de propriété » dans l’aide de DAO.  
  
 *m_nOrdinalPosition*  
 Une valeur qui indique l’ordre numérique dans lequel vous souhaitez un champ représenté par un objet de champ DAO à afficher par rapport à d’autres champs. Vous pouvez définir cette propriété avec [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield). Pour plus d’informations, consultez la rubrique « Propriété OrdinalPosition » dans l’aide de DAO.  
  
 `m_bRequired`  
 Indique si un objet de champ DAO requiert une valeur non Null. Si cette propriété est **TRUE**, le champ n’autorise pas une valeur Null. Si besoin est définie sur **FALSE**, le champ peut contenir des valeurs Null ainsi que des valeurs répondant aux conditions spécifiées par les paramètres de propriété AllowZeroLength et ValidationRule. Pour plus d’informations, consultez la rubrique « Propriété Required » dans l’aide de DAO. Vous pouvez définir cette propriété pour un objet tabledef avec [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_bAllowZeroLength*  
 Indique si une chaîne vide (« ») est une valeur valide d’un objet de champ DAO avec un type de données texte ou Mémo. Si cette propriété est **TRUE**, une chaîne vide est une valeur valide. Vous pouvez définir cette propriété **FALSE** pour vous assurer que vous ne pouvez pas utiliser une chaîne vide pour définir la valeur d’un champ. Pour plus d’informations, consultez la rubrique « Propriété AllowZeroLength » dans l’aide de DAO. Vous pouvez définir cette propriété pour un objet tabledef avec [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_lCollatingOrder`  
 Spécifie la séquence de l’ordre de tri du texte pour la comparaison de chaînes ou de tri. Pour plus d’informations, consultez la rubrique « Personnalisation Windows Registre paramètres d’accès aux données » dans l’aide de DAO. Pour obtenir la liste des valeurs retournées, consultez la **m_lCollatingOrder** membre de la [CDaoDatabaseInfo](../../mfc/reference/cdaodatabaseinfo-structure.md) structure. Vous pouvez définir cette propriété pour un objet tabledef avec [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strForeignName`  
 Valeur qui, dans une relation, spécifie le nom de l’objet DAO du champ dans une table étrangère qui correspond à un champ dans une table primaire. Pour plus d’informations, consultez la rubrique « Propriété ForeignName » dans l’aide de DAO.  
  
 *m_strSourceField*  
 Indique le nom du champ qui est la source d’origine des données d’un objet de champ DAO contenu par un objet tabledef, recordset ou objet querydef. Cette propriété indique le nom du champ d’origine associé à un objet de champ. Par exemple, vous pouvez utiliser cette propriété pour déterminer la source d’origine des données dans un champ de requête dont le nom n’est pas lié au nom du champ dans la table sous-jacente. Pour plus d’informations, consultez la rubrique « SourceField, SourceTable propriétés » dans l’aide de DAO. Vous pouvez définir cette propriété pour un objet tabledef avec [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strSourceTable*  
 Indique le nom de la table qui est la source d’origine des données d’un objet de champ DAO contenu par un objet tabledef, recordset ou objet querydef. Cette propriété indique le nom de la table d’origine associé à un objet de champ. Par exemple, vous pouvez utiliser cette propriété pour déterminer la source d’origine des données dans un champ de requête dont le nom n’est pas lié au nom du champ dans la table sous-jacente. Pour plus d’informations, consultez la rubrique « SourceField, SourceTable propriétés » dans l’aide de DAO. Vous pouvez définir cette propriété pour un objet tabledef avec [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 `m_strValidationRule`  
 Une valeur qui valide les données dans un champ en tant qu’il est modifiée ou ajoutée à une table. Pour plus d’informations, consultez la rubrique « Propriété ValidationRule » dans l’aide de DAO. Vous pouvez définir cette propriété pour un objet tabledef avec [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 Pour plus d’informations sur les objets TableDef, consultez la **m_strValidationRule** membre de la [CDaoTableDefInfo](../../mfc/reference/cdaotabledefinfo-structure.md) structure.  
  
 `m_strValidationText`  
 Une valeur qui spécifie le texte du message que votre application affiche si la valeur d’un objet de champ DAO ne respecte pas la règle de validation spécifiée par le paramètre de propriété ValidationRule. Pour plus d’informations, consultez la rubrique « Propriété ValidationRule » dans l’aide de DAO. Vous pouvez définir cette propriété pour un objet tabledef avec [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
 *m_strDefaultValue*  
 La valeur par défaut d’un objet de champ DAO. Lorsqu’un nouvel enregistrement est créé, le paramètre de propriété DefaultValue est automatiquement entré comme valeur pour le champ. Pour plus d’informations, consultez la rubrique « Propriété DefaultValue » dans l’aide de DAO. Vous pouvez définir cette propriété pour un objet tabledef avec [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield).  
  
## <a name="remarks"></a>Remarques  
 Les références au principal, secondaire et toutes les ci-dessus indiquent comment les informations sont renvoyées par le `GetFieldInfo` fonction membre dans les classes [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getfieldinfo), [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo), et [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getfieldinfo).  
  
 Objets de champ ne sont pas représentées par une classe MFC. Au lieu de cela, les objets DAO sous-jacent d’objets MFC des classes suivantes contiennent des collections d’objets field : [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md), [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md), et [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md). Ces classes fournissent des fonctions membres pour accéder à certains des éléments individuels d’informations sur les champs, ou vous pouvez y accéder à la fois avec un `CDaoFieldInfo` objet en appelant le `GetFieldInfo` fonction membre de l’objet conteneur.  
  
 Outre son utilisation pour examiner les propriétés de l’objet, vous pouvez utiliser `CDaoFieldInfo` pour construire un paramètre d’entrée pour la création de nouveaux champs dans un objet tabledef. Options plus simples sont disponibles pour cette tâche, mais si vous souhaitez un contrôle plus précis, vous pouvez utiliser la version de [CDaoTableDef::CreateField](../../mfc/reference/cdaotabledef-class.md#createfield) qui accepte un `CDaoFieldInfo` paramètre.  
  
 Les informations récupérées par le `GetFieldInfo` fonction membre (de la classe qui contient le champ) est stockée dans un `CDaoFieldInfo` structure. Appelez le `GetFieldInfo` fonction membre de l’objet conteneur dans la collection des champs dont l’objet de champ est stocké. `CDaoFieldInfo`définit également un `Dump` builds de la fonction membre en mode de débogage. Vous pouvez utiliser `Dump` pour vider le contenu d’un `CDaoFieldInfo` objet.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdao.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetFieldInfo](../../mfc/reference/cdaotabledef-class.md#getfieldinfo)   
 [CDaoRecordset::GetFieldInfo](../../mfc/reference/cdaorecordset-class.md#getfieldinfo)   
 [CDaoQueryDef::GetFieldInfo](../../mfc/reference/cdaoquerydef-class.md#getfieldinfo)


