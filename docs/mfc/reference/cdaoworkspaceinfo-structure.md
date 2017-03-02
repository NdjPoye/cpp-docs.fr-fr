---
title: CDaoWorkspaceInfo (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoWorkspaceInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoWorkspaceInfo structure
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
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
ms.openlocfilehash: 44c1ce365a1eecdb2a500998c082c6a9245dffb2
ms.lasthandoff: 02/24/2017

---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo, structure
Le `CDaoWorkspaceInfo` structure contient des informations sur un espace de travail défini pour les données de base de données (DAO) d’objets accès.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct CDaoWorkspaceInfo  
{  
    CString m_strName;           // Primary  
    CString m_strUserName;       // Secondary  
    BOOL m_bIsolateODBCTrans;    // All  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 `m_strName`  
 Identifiant de manière unique l’objet espace de travail. Pour récupérer la valeur de cette propriété directement, appelez l’objet querydef [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) fonction membre. Pour plus d’informations, consultez la rubrique « Nom de propriété » dans l’aide de DAO.  
  
 *m_strUserName*  
 Valeur qui représente le propriétaire d’un objet d’espace de travail. Pour plus d’informations, consultez la rubrique « Propriété de nom d’utilisateur » dans l’aide de DAO.  
  
 *m_bIsolateODBCTrans*  
 Une valeur qui indique si plusieurs transactions impliquant la même base de données ODBC sont isolées. Pour plus d’informations, consultez [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans). Pour plus d’informations, consultez la rubrique « Propriété IsolateODBCTrans » dans l’aide de DAO.  
  
## <a name="remarks"></a>Remarques  
 L’espace de travail est un objet de classe [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Les références au principal, secondaire et toutes les ci-dessus indiquent comment les informations sont renvoyées par le [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) fonction membre dans la classe `CDaoWorkspace`.  
  
 Les informations récupérées par le [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) fonction membre est stockée dans un `CDaoWorkspaceInfo` structure. `CDaoWorkspaceInfo`définit également un `Dump` builds de la fonction membre en mode de débogage. Vous pouvez utiliser `Dump` pour vider le contenu d’un `CDaoWorkspaceInfo` objet.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdao.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace (classe)](../../mfc/reference/cdaoworkspace-class.md)

