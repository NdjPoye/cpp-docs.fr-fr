---
title: CDaoRelationInfo (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoRelationInfo
dev_langs:
- C++
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
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
ms.openlocfilehash: 7c3a8195aed2c3b3fe5c78c98afcc6e72a83cc21
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo, structure
Le `CDaoRelationInfo` structure contient des informations sur une relation définie entre les champs de deux tables dans un [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CDaoRelationInfo  
{  
    CDaoRelationInfo();
*// Constructor  
    CString m_strName;      // Primary  
    CString m_strTable;     // Primary  
    CString m_strForeignTable;              // Primary  
    long m_lAttributes;     // Secondary  
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary  
    short m_nFields;        // Secondary *// Below the // Implementation comment: *// Destructor, not otherwise documented  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 `m_strName`  
 Identifiant de manière unique l’objet relation. Pour plus d’informations, consultez la rubrique « Nom de propriété » dans l’aide de DAO.  
  
 *m_strTable*  
 Nom de la table primaire dans la relation.  
  
 *m_strForeignTable*  
 Nom de la table étrangère dans la relation. Une table étrangère est une table utilisée pour contenir des clés étrangères. En règle générale, vous utilisez une table étrangère pour établir ou appliquer l’intégrité référentielle. La table externe est généralement sur le côté « plusieurs » d’une relation un-à-plusieurs. Exemples de tables externes contiennent des tables contenant des codes d’États américains ou de provinces du Canada ou de commandes client.  
  
 `m_lAttributes`  
 Contient des informations sur le type de relation. La valeur de ce membre peut être une des opérations suivantes :  
  
- **dbRelationUnique** relation est un à un.  
  
- **Pourriez** relation n’est pas appliquée (aucune intégrité référentielle).  
  
- **dbRelationInherited** relation existe dans une base de données non courante qui contient les deux tables attachées.  
  
- **dbRelationLeft** la relation est une jointure gauche. Une jointure externe gauche comprend tous les enregistrements de la première (gauche) de deux tables, même si aucune valeur correspondante pour les enregistrements de la seconde table (à droite).  
  
- **dbRelationRight** la relation est une jointure droite. Une jointure externe droite comprend tous les enregistrements de la deuxième (à droite) de deux tables, même si aucune valeur correspondante pour les enregistrements de la première table (gauche).  
  
- **dbRelationUpdateCascade** mises à jour sont mises en cascade.  
  
- **dbRelationDeleteCascade** suppressions sont mises en cascade.  
  
 `m_pFieldInfos`  
 Un pointeur vers un tableau de [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) structures. Le tableau contient un objet pour chaque champ dans la relation. Le `m_nFields` membre de données offre un nombre d’éléments du tableau.  
  
 `m_nFields`  
 Le nombre de `CDaoRelationFieldInfo` des objets dans le `m_pFieldInfos` membre de données.  
  
## <a name="remarks"></a>Notes  
 Les références aux principaux et secondaires ci-dessus indiquent comment les informations sont renvoyées par le [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) fonction membre dans la classe `CDaoDatabase`.  
  
 Les objets de relation ne sont pas représentés par une classe MFC. Au lieu de cela, l’objet DAO sous-jacent d’un objet MFC de la `CDaoDatabase` classe maintient une collection d’objets relation : `CDaoDatabase` fournit les fonctions membres pour accéder à certains des éléments individuels d’informations sur la relation, ou vous peuvent y accéder tous à la fois avec un `CDaoRelationInfo` objet en appelant le `GetRelationInfo` fonction membre de l’objet conteneur de la base de données.  
  
 Les informations récupérées par le [CDaoDatabase::GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) fonction membre est stockée dans un `CDaoRelationInfo` structure. `CDaoRelationInfo`définit également un `Dump` builds de la fonction membre en mode de débogage. Vous pouvez utiliser `Dump` pour vider le contenu d’un `CDaoRelationInfo` objet.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdao.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDaoRelationFieldInfo (Structure)](../../mfc/reference/cdaorelationfieldinfo-structure.md)

