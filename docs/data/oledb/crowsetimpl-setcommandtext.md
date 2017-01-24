---
title: "CRowsetImpl::SetCommandText | Microsoft Docs"
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
  - "CRowsetImpl.SetCommandText"
  - "CRowsetImpl::SetCommandText"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetCommandText (méthode)"
ms.assetid: e016d7df-c1a0-4dee-b19b-c876680221fd
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::SetCommandText
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Valide et stocke les **DBID**dans les deux chaînes \([m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) et [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md)\).  
  
## Syntaxe  
  
```  
  
      HRESULT CRowsetBaseImpl::SetCommandText(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### Paramètres  
 `pTableID`  
 \[in\] Un pointeur à **DBID** qui représente l'ID de table.  
  
 `pIndexID`  
 \[in\] Un pointeur à **DBID** qui représente l'ID de l'Index.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 La méthode de **SetCommentText** est appelée par `CreateRowset`, une méthode de mise au modèle de `IOpenRowsetImpl`statique.  
  
 Cette méthode délègue son travail en appelant [ValidateCommandID](../../data/oledb/crowsetimpl-validatecommandid.md) et [GetCommandFromID](../../data/oledb/crowsetimpl-getcommandfromid.md) via un pointeur upcasted.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [CRowsetImpl, classe](../../data/oledb/crowsetimpl-class.md)