---
title: "IRowsetNotifyCP::Fire_OnFieldChange | Microsoft Docs"
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
  - "Fire_OnFieldChange"
  - "ATL::IRowsetNotifyCP::Fire_OnFieldChange"
  - "ATL.IRowsetNotifyCP.Fire_OnFieldChange"
  - "IRowsetNotifyCP.Fire_OnFieldChange"
  - "IRowsetNotifyCP::Fire_OnFieldChange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Fire_OnFieldChange (méthode)"
ms.assetid: 03dad058-8d4f-4113-aea4-ef7764eab9ec
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetNotifyCP::Fire_OnFieldChange
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Distribue un événement [OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) pour avertir les consommateurs de la modification de la valeur d'une colonne.  
  
## Syntaxe  
  
```  
  
      HRESULT Fire_OnFieldChange(  
   IRowset* pRowset,  
   HROW hRow,  
   DBORDINAL cColumns,  
   DBORDINAL* rgColumns,  
   DBREASON eReason,  
   DBEVENTPHASE ePhase,  
   BOOL fCantDeny   
);  
```  
  
#### Paramètres  
 Consultez [IRowsetNotify::OnFieldChange](https://msdn.microsoft.com/en-us/library/ms715961.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetNotifyCP, classe](../../data/oledb/irowsetnotifycp-class.md)