---
title: "CDaoIndexFieldInfo, structure | Microsoft Docs"
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
  - "CDaoIndexFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoIndexFieldInfo (structure)"
  - "DAO (Data Access Objects), champs d'index (collection)"
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoIndexFieldInfo, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `CDaoIndexFieldInfo` contient des informations sur un objet de champ d'index défini pour les objets \(DAO\) d'accès aux données.  
  
## Syntaxe  
  
```  
  
      struct CDaoIndexFieldInfo  
{  
   CString m_strName;          // Primary  
   BOOL m_bDescending;         // Primary  
};  
```  
  
#### Paramètres  
 `m_strName`  
 Nomme de manière unique l'objet de champ d'index.  Pour plus d'informations, consultez la rubrique « propriété » dans l'aide du DAO.  
  
 *m\_bDescending*  
 Indique l'ordre des index défini par l'objet index.  **VRAI** si la commande est décroissante.  
  
## Notes  
 L'objet index peut avoir plusieurs champs, indiquant sur quels champs un tabledef \(ou un recordset basée sur une table\) est indexé.  Des références au primaire ci\-dessus montrent comment les informations sont retournées dans le membre `m_pFieldInfos` d'un objet [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) obtenu en appelant la fonction membre `GetIndexInfo` de la classe [CDaoTableDef](../Topic/CDaoTableDef::GetIndexInfo.md) ou [CDaoRecordset](../Topic/CDaoRecordset::GetIndexInfo.md).  
  
 Les objets index et les objets de champ d'index ne sont pas représentés par une classe MFC.  En revanche, les objets DAO sous\-jacents des objets MFC de la classe [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) ou [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) contiennent une collection d'objets index, appelée la collection d'index.  Chaque objet index, à son tour, contient une collection d'objets.  Ces classes fournissent les fonctions membres pour accéder à des éléments individuels des informations d'index, ou vous pouvez y accéder tous en même temps avec un objet d' `CDaoIndexInfo` en appelant la fonction membre d' `GetIndexInfo` de l'objet conteneur.  L'objet `CDaoIndexInfo`, alors, possède un membre de données, `m_pFieldInfos`, qui pointe vers un tableau d'objets `CDaoIndexFieldInfo`.  
  
 Appelez la fonction membre `GetIndexInfo` du tabledef ou de l'objet recordset conteneur dans la collection d'index duquel est enregistrée l'objet index qui vous intéresse.  Accédez ensuite au membre `m_pFieldInfos` de l'objet [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md).  La longueur du tableau `m_pFieldInfos` est stockée dans `m_nFields`.  `CDaoIndexFieldInfo` définit également une fonction membre `Dump` dans les versions de débogage.  Utilisez `Dump` pour vider le contenu d'un objet `CDaoIndexFieldInfo`.  
  
## Configuration requise  
 **En\-tête :** afxdao.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoTableDef::GetIndexInfo](../Topic/CDaoTableDef::GetIndexInfo.md)   
 [CDaoRecordset::GetIndexInfo](../Topic/CDaoRecordset::GetIndexInfo.md)