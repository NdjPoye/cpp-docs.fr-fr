---
title: Cdaoworkspaceinfo, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDaoWorkspaceInfo
dev_langs:
- C++
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 7e154e2672a9410af979c2e5aa0f6fb0aba7a50f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo, structure
Le `CDaoWorkspaceInfo` structure contient des informations sur un espace de travail défini pour l’accès de données access (DAO) d’objets de base de données.  
  
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
 Identifie l’objet de l’espace de travail. Pour récupérer la valeur de cette propriété directement, appelez l’objet querydef [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) fonction membre. Pour plus d’informations, consultez la rubrique « Nom de propriété » dans l’aide de DAO.  
  
 *m_strUserName*  
 Une valeur qui représente le propriétaire d’un objet de l’espace de travail. Pour plus d’informations, consultez la rubrique « Propriété de nom d’utilisateur » dans l’aide de DAO.  
  
 *m_bIsolateODBCTrans*  
 Une valeur qui indique si plusieurs transactions qui impliquent la même base de données ODBC sont isolées. Pour plus d’informations, consultez [CDaoWorkspace::SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans). Pour plus d’informations, consultez la rubrique « Propriété IsolateODBCTrans » dans l’aide de DAO.  
  
## <a name="remarks"></a>Notes  
 L’espace de travail est un objet de classe [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md). Les références au principal, secondaire et tous les ci-dessus indiquent comment les informations sont retournées par la [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) fonction membre dans la classe `CDaoWorkspace`.  
  
 Les informations extraites par le [CDaoWorkspace::GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) fonction membre est stockée dans un `CDaoWorkspaceInfo` structure. `CDaoWorkspaceInfo`définit également un `Dump` builds de la fonction membre en mode débogage. Vous pouvez utiliser `Dump` pour vider le contenu d’un `CDaoWorkspaceInfo` objet.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** afxdao.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace, classe](../../mfc/reference/cdaoworkspace-class.md)
