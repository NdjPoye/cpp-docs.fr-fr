---
title: "IRowsetImpl::SetDBStatus | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetImpl.SetDBStatus"
  - "IRowsetImpl::SetDBStatus"
  - "SetDBStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetDBStatus (méthode)"
ms.assetid: b73f526a-4fc6-4adb-9611-c3cca2cddb23
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::SetDBStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fixe les indicateurs d'état de `DBSTATUS` du champ spécifié.  
  
## Syntaxe  
  
```  
  
      virtual HRESULT SetDBStatus(  
   DBSTATUS* statusFlags,  
   RowClass* currentRow,  
   ATLCOLUMNINFO* columnInfo   
);  
```  
  
#### Paramètres  
 `statusFlags`  
 Les indicateurs de [DBSTATUS](https://msdn.microsoft.com/en-us/library/ms722617.aspx) à définir pour la colonne.  
  
 `currentRow`  
 La ligne actuelle.  
  
 *columnInfo*  
 La colonne dont l'état est en train d'être fixé.  
  
## Valeur de retour  
 Une valeur standard `HRESULT`.  
  
## Notes  
 Le fournisseur remplace cette fonction pour fournir un traitement spécial de **DBSTATUS\_S\_ISNULL** et **DBSTATUS\_S\_DEFAULT**.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)