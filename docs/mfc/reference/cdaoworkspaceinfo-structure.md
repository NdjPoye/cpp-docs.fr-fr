---
title: "CDaoWorkspaceInfo, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDaoWorkspaceInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoWorkspaceInfo (structure)"
  - "DAO (Data Access Objects), Workspaces (collection)"
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoWorkspaceInfo, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure de `CDaoWorkspaceInfo` contient des informations sur un espace de travail défini pour l'accès aux bases de données \(DAO\) des objets d'accès aux données.  
  
## Syntaxe  
  
```  
  
      struct CDaoWorkspaceInfo  
{  
   CString m_strName;           // Primary  
   CString m_strUserName;       // Secondary  
   BOOL m_bIsolateODBCTrans;    // All  
};  
```  
  
#### Paramètres  
 `m_strName`  
 Donne uniquement un nom à l'objet espace de travail.  Pour récupérer la valeur de cette propriété directement, appelez la fonction membre de [GetName](../Topic/CDaoQueryDef::GetName.md) de l'objet de querydef.  Pour plus d'informations, consultez le sujet "Propriété du nom" dans l'aide DAO.  
  
 *m\_strUserName*  
 Valeur qui représente le propriétaire d'un objet espace de travail.  Pour plus d'informations, consultez la rubrique « propriété de nom d'utilisateur » dans l'aide du DAO.  
  
 *m\_bIsolateODBCTrans*  
 Valeur qui indique si plusieurs transactions impliquant la même base de données ODBC sont isolées.  Pour plus d'informations, consultez [CDaoWorkspace::SetIsolateODBCTrans](../Topic/CDaoWorkspace::SetIsolateODBCTrans.md).  Pour plus d'informations, consultez la rubrique « Propriétés IsolateODBCTrans» dans l'aide du DAO.  
  
## Notes  
 L'espace de travail est un objet de la classe [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md).  Des références au primaire, au secondaire, et tous les supérieures indiquent comment les informations sont retournées par la fonction membre de [GetWorkspaceInfo](../Topic/CDaoWorkspace::GetWorkspaceInfo.md) de la classe `CDaoWorkspace`.  
  
 Les informations récupérées par la fonction membre de [CDaoWorkspace::GetWorkspaceInfo](../Topic/CDaoWorkspace::GetWorkspaceInfo.md) sont stockées dans une structure de `CDaoWorkspaceInfo`.  `CDaoWorkspaceInfo` définit également une fonction membre `Dump` dans les versions de débogage.  Vous pouvez utiliser `Dump` pour vider le contenu d'un objet `CDaoWorkspaceInfo`.  
  
## Configuration requise  
 **En\-tête :** afxdao.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoWorkspace Class](../../mfc/reference/cdaoworkspace-class.md)