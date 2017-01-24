---
title: "CDaoRelationFieldInfo, structure | Microsoft Docs"
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
  - "CDaoRelationFieldInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDaoRelationFieldInfo (structure)"
  - "DAO (Data Access Objects), Relations (collection)"
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDaoRelationFieldInfo, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `CDaoRelationFieldInfo` contient des informations sur un champ dans une relation défini pour les objets d'accès aux données \(DAO\).  
  
## Syntaxe  
  
```  
  
      struct CDaoRelationFieldInfo  
{  
   CString m_strName;           // Primary  
   CString m_strForeignName;    // Primary  
};  
```  
  
#### Paramètres  
 `m_strName`  
 Nom du champ dans la table primaire de la relation.  
  
 `m_strForeignName`  
 Nom du champ dans la table étrangère de la relation.  
  
## Notes  
 Un objet de relation DAO spécifie les champs dans la table primaire et les champs dans la table étrangère qui définissent la relation.  Les références à Primary dans la définition de la structure ci\-dessus montrent comment les informations sont retournées dans le membre `m_pFieldInfos` d'un objet [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) obtenu en appelant la méthode [GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md) de la classe `CDaoDatabase`.  
  
 Les objets relation et les champs de relations ne sont pas représentés par une classe MFC.  En revanche, les objets DAO sous\-jacents des objets MFC de la classe [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) contiennent une collection d'objets relation, appelée la collection de relations.  Chaque objet relation, à son tour, contient une collection de champs de relation.  Chaque objet champ de relation corrèle un champ dans la table primaire avec un champ dans la table étrangère.  Pris ensemble, les champs de relation définissent un groupe de champs dans chaque table, qui définissent définir la relation.  `CDaoDatabase` vous permet d'accéder aux objets relation avec un objet `CDaoRelationInfo` en appelant la méthode `GetRelationInfo`.  L'objet `CDaoRelationInfo` possède alors un membre de données, `m_pFieldInfos`, qui pointe vers un tableau d'objets `CDaoRelationFieldInfo`.  
  
 Appelez la méthode [GetRelationInfo](../Topic/CDaoDatabase::GetRelationInfo.md) de l'objet conteneur `CDaoDatabase` dont la	collection de relations contient l'objet relation qui vous intéresse.  Accédez ensuite au membre `m_pFieldInfos` de l'objet [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md).  `CDaoRelationFieldInfo` définit également une méthode `Dump` dans les versions de débogage.  Vous pouvez utiliser `Dump` pour vider le contenu d'un objet `CDaoRelationFieldInfo`.  
  
## Configuration requise  
 **En\-tête :** afxdao.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDaoRelationInfo, structure](../../mfc/reference/cdaorelationinfo-structure.md)