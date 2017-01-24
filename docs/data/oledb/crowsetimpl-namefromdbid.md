---
title: "CRowsetImpl::NameFromDBID | Microsoft Docs"
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
  - "CRowsetImpl.NameFromDBID"
  - "CRowsetImpl::NameFromDBID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NameFromDBID (méthode)"
ms.assetid: 6aa5b074-90c7-4434-adfd-c64c13e76c78
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::NameFromDBID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Extrait une chaîne de **DBID** et la copie sur `bstr` transmis.  
  
## Syntaxe  
  
```  
  
      HRESULT CRowsetBaseImpl::NameFromDBID(  
   DBID* pDBID,  
   CComBSTR& bstr,  
   bool bIndex   
);  
```  
  
#### Paramètres  
 *pDBID*  
 \[in\] pointeur à **DBID** à partir duquel extraire une chaîne.  
  
 `bstr`  
 \[in\] référence d'Une [CComBSTR](../../atl/reference/ccombstr-class.md) pour placer une copie de **DBID**.  
  
 `bIndex`  
 \[in\] **true** si un index **DBID**; **false** si une table **DBID**.  
  
## Valeur de retour  
 Un `HRESULT` standard.  Selon que **DBID** est une table ou un index \(illustré par `bIndex`\), la méthode retourne **DB\_E\_NOINDEX** ou **DB\_E\_NOTABLE**.  
  
## Notes  
 Cette méthode est appelée par les implémentations `CRowsetImpl` de [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) et de [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [CRowsetImpl, classe](../../data/oledb/crowsetimpl-class.md)