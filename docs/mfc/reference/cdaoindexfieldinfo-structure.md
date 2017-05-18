---
title: CDaoIndexFieldInfo (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoIndexFieldInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoIndexFieldInfo structure
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
caps.latest.revision: 12
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
ms.openlocfilehash: 975b3a704936adc9d4205938bb2c757ab650f0d9
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo, structure
Le `CDaoIndexFieldInfo` structure contient des informations sur un objet de champ index défini pour les objets d’accès aux données (DAO).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CDaoIndexFieldInfo  
{  
    CString m_strName;          // Primary  
    BOOL m_bDescending;         // Primary  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 `m_strName`  
 Identifie l’objet de champ d’index. Pour plus d’informations, consultez la rubrique « Nom de propriété » dans l’aide de DAO.  
  
 *m_bDescending*  
 Indique l’ordre d’index défini par l’objet index. **TRUE** si l’ordre est décroissant.  
  
## <a name="remarks"></a>Notes  
 Un objet index peut avoir un nombre de champs, qui indique les champs d’un objet tabledef (ou un jeu d’enregistrements basé sur une table) est indexé sur. Les références au principal ci-dessus indiquent comment les informations sont retournées dans le `m_pFieldInfos` membre d’un [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) objet obtenu en appelant le `GetIndexInfo` fonction membre de classe [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo) ou [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo).  
  
 Objets index et objets de champ d’index ne sont pas représentées par une classe MFC. Au lieu de cela, le DAO des objets MFC sous-jacente de la classe d’objets [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) ou [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) contient une collection d’objets index, appelée la collection d’index. Chaque objet d’index contient une collection d’objets de champ. Ces classes fournissent des fonctions membres pour accéder aux différents éléments des informations d’index, ou vous pouvez y accéder à la fois avec un `CDaoIndexInfo` objet en appelant le `GetIndexInfo` fonction membre de l’objet conteneur. Le `CDaoIndexInfo` objet, ensuite, a un membre de données, `m_pFieldInfos`, qui pointe vers un tableau de `CDaoIndexFieldInfo` objets.  
  
 Appelez le `GetIndexInfo` fonction membre de l’objet tabledef ou recordset contenant dans les index dont la collection est stocké l’objet index vous intéresse. Ensuite accéder à la `m_pFieldInfos` membre de la [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) objet. La longueur de la `m_pFieldInfos` tableau est stocké dans `m_nFields`. `CDaoIndexFieldInfo`définit également un `Dump` builds de la fonction membre en mode de débogage. Vous pouvez utiliser `Dump` pour vider le contenu d’un `CDaoIndexFieldInfo` objet.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdao.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)   
 [CDaoRecordset::GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)


