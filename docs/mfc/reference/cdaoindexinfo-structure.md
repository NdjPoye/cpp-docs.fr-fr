---
title: CDaoIndexInfo (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoIndexInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Indexes collection
- CDaoIndexInfo structure
ms.assetid: 251d8285-78ce-4716-a0b3-ccc3395fc437
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
ms.openlocfilehash: 92206d8d8f9b2315fb859e2712a83d32a4c293ad
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoindexinfo-structure"></a>CDaoIndexInfo, structure
Le `CDaoIndexInfo` structure contient des informations sur un objet index défini pour les objets d’accès aux données (DAO).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CDaoIndexInfo {  
    CDaoIndexInfo();
*// Constructor  
    CString m_strName;  // Primary  
    CDaoIndexFieldInfo* m_pFieldInfos;  // Primary  
    short m_nFields;    // Primary  
    BOOL m_bPrimary;    // Secondary  
    BOOL m_bUnique;     // Secondary  
    BOOL m_bClustered;  // Secondary  
    BOOL m_bIgnoreNulls;                // Secondary  
    BOOL m_bRequired;   // Secondary  
    BOOL m_bForeign;    // Secondary  
    long m_lDistinctCount;              // All  
 *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};   
```  
  
#### <a name="parameters"></a>Paramètres  
 `m_strName`  
 Identifie l’objet de champ. Pour plus d’informations, consultez la rubrique « Nom de propriété » dans l’aide de DAO.  
  
 `m_pFieldInfos`  
 Un pointeur vers un tableau de [CDaoIndexFieldInfo](../../mfc/reference/cdaoindexfieldinfo-structure.md) objets indiquant quels champs tabledef ou recordset sont des champs clés dans un index. Chaque objet identifie un champ dans l’index. L’ordre d’index par défaut est croissant. Un objet index peut avoir un ou plusieurs champs représentant les clés d’index pour chaque enregistrement. Il peuvent être dans l’ordre croissant, décroissant, ou une combinaison.  
  
 `m_nFields`  
 Le nombre de champs stockés dans `m_pFieldInfos`.  
  
 *m_bPrimary*  
 Si la propriété principale **TRUE**, l’objet index représente un index primaire. Un index primaire se compose d’un ou plusieurs champs qui identifient de manière unique tous les enregistrements dans une table dans un ordre prédéfini. Étant donné que le champ d’index doit être unique, la propriété de l’objet Index Unique est également définie **TRUE** dans DAO. Si l’index primaire est composée de plusieurs champs, chaque champ peut contenir des valeurs dupliquées, mais chaque combinaison de valeurs de tous les champs indexés doit être unique. Un index primaire est constitué d’une clé pour la table et contient généralement les mêmes champs que la clé primaire.  
  
 Lorsque vous définissez une clé primaire pour une table, la clé primaire est automatiquement définie en tant que l’index primaire de la table. Pour plus d’informations, consultez les rubriques « Propriété principal » et « Propriété Unique » dans l’aide de DAO.  
  
> [!NOTE]
>  Il peut être, au plus, un seul index primaire d’une table.  
  
 *m_bUnique*  
 Indique si un objet index représente un index unique pour une table. Si cette propriété est **TRUE**, l’objet index représente un index unique. Un index unique se compose d’un ou plusieurs champs qui organisent de manière logique tous les enregistrements dans une table dans un ordre prédéfini unique. Si l’index se compose d’un seul champ, les valeurs de ce champ doivent être uniques pour la table entière. Si l’index se compose de plusieurs champs, chaque champ peut contenir des valeurs dupliquées, mais chaque combinaison de valeurs de tous les champs indexés doit être unique.  
  
 Si les propriétés de l’Unique et principal d’un objet index sont définies sur **TRUE**, l’index est unique et primaire : il identifie de manière unique tous les enregistrements de la table dans un ordre logique prédéfini. Si la propriété primaire est définie sur **FALSE**, l’index est un index secondaire. Les index secondaires (clés et non clés) organisent de manière logique les enregistrements dans un ordre prédéfini sans servant d’identificateur pour les enregistrements dans la table.  
  
 Pour plus d’informations, consultez les rubriques « Propriété principal » et « Propriété Unique » dans l’aide de DAO.  
  
 *m_bClustered*  
 Indique si un objet index représente un index cluster pour une table. Si cette propriété est **TRUE**, l’objet index représente un index cluster ; sinon, il n’existe pas. Un index ordonné en clusters se compose d’un ou plusieurs champs qui, ensemble, réorganisez tous les enregistrements dans une table dans un ordre prédéfini. Avec un index ordonné en clusters, les données de la table sont littéralement stockées dans l’ordre spécifié par l’index cluster. Un index ordonné en clusters fournit un accès efficace aux enregistrements dans une table. Pour plus d’informations, consultez la rubrique « Propriété en cluster » dans l’aide de DAO.  
  
> [!NOTE]
>  La propriété Clustered est ignorée pour les bases de données qui utilisent le moteur de base de données Microsoft Jet, car le moteur de base de données Jet ne prend pas en charge les index cluster.  
  
 *m_bIgnoreNulls*  
 Indique s’il existe des entrées d’index pour les enregistrements qui ont des valeurs Null dans les champs d’index. Si cette propriété est **TRUE**, champs avec des valeurs Null n’ont pas une entrée d’index. Pour accélérer la recherche des enregistrements à l’aide d’un champ plus rapidement, vous pouvez définir un index pour le champ. Si vous autorisez les entrées Null dans un champ indexé et prévoyez d’avoir beaucoup d’entrées Null, vous pouvez définir la propriété Ignorer Nulls l’objet index **TRUE** pour réduire la quantité d’espace de stockage qui utilise l’index. Le paramètre de propriété Ignorer Nulls et le paramètre de propriété requis déterminent ensemble si un enregistrement avec une valeur d’index Null a une entrée d’index, comme le tableau suivant.  
  
|Ignorer Nulls|Obligatoire|Valeur NULL dans le champ d’index|  
|-----------------|--------------|-------------------------|  
|True|False|Valeur NULL autorisée ; Aucune entrée d’index ajoutée.|  
|False|False|Valeur NULL autorisée ; entrée d’index ajoutée.|  
|True ou False|True|Valeur NULL non autorisée ; Aucune entrée d’index ajoutée.|  
  
 Pour plus d’informations, consultez la rubrique « Propriété Ignorer Nulls » dans l’aide de DAO.  
  
 `m_bRequired`  
 Indique si un objet d’index DAO requiert une valeur non Null. Si cette propriété est **TRUE**, l’objet index n’autorise pas une valeur Null. Pour plus d’informations, consultez la rubrique « Propriété Required » dans l’aide de DAO.  
  
> [!TIP]
>  Lorsque vous pouvez définir cette propriété pour un objet d’index DAO ou un objet de champ (contenu dans un objet tabledef, recordset ou objet querydef), la valeur de l’objet de champ. La validité du paramètre de propriété pour un objet field est vérifiée avant celle d’un objet index.  
  
 *m_bForeign*  
 Indique si un objet index représente une clé étrangère dans une table. Si cette propriété est **TRUE**, l’index représente une clé étrangère dans une table. Une clé étrangère consiste en un ou plusieurs champs dans une table étrangère qui identifient de manière unique une ligne dans une table primaire. Le moteur de base de données Microsoft Jet crée un objet d’index pour la table étrangère et définit la propriété Foreign lorsque vous créez une relation qui applique l’intégrité référentielle. Pour plus d’informations, consultez la rubrique « Propriété étrangère » dans l’aide de DAO.  
  
 *m_lDistinctCount*  
 Indique le nombre de valeurs uniques pour l’objet index inclus dans la table associée. Vérifiez la propriété DistinctCount pour déterminer le nombre de valeurs uniques, ou clés, d’un index. Chaque clé est comptée une seule fois, même s’il peut y avoir plusieurs occurrences de cette valeur si l’index autorise les doublons. Ces informations sont utiles dans les applications qui tentent d’optimiser l’accès aux données en évaluant les informations d’index. Le nombre de valeurs uniques est également appelé la cardinalité d’un objet index. La propriété DistinctCount pas toujours reflète le nombre réel de clés à un moment donné. Par exemple, une modification entraînée par la restauration d’une transaction est répercutée immédiatement dans la propriété DistinctCount. Pour plus d’informations, consultez la rubrique « Propriété DistinctCount » dans l’aide de DAO.  
  
## <a name="remarks"></a>Notes  
 Les références au principal, secondaire et toutes les ci-dessus indiquent comment les informations sont renvoyées par le `GetIndexInfo` fonction membre dans les classes [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) et [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Objets index ne sont pas représentées par une classe MFC. DAO d’objets au lieu de cela, les objets MFC sous-jacente de la classe [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) ou [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) contient une collection d’objets index, appelée la collection d’index. Ces classes fournissent des fonctions membres pour accéder aux différents éléments des informations d’index, ou vous pouvez y accéder à la fois avec un `CDaoIndexInfo` objet en appelant le `GetIndexInfo` fonction membre de l’objet conteneur.  
  
 `CDaoIndexInfo`possède un constructeur et un destructeur pour allouer et libérer les informations de champ d’index dans correctement `m_pFieldInfos`.  
  
 Les informations récupérées par le `GetIndexInfo` fonction membre d’un objet tabledef est stockée dans un `CDaoIndexInfo` structure. Appelez le `GetIndexInfo` fonction membre de l’objet conteneur tabledef dans la collection d’index dont l’objet index est stocké. `CDaoIndexInfo`définit également un `Dump` builds de la fonction membre en mode de débogage. Vous pouvez utiliser `Dump` pour vider le contenu d’un `CDaoIndexInfo` objet.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdao.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)


