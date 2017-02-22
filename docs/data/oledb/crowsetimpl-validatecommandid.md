---
title: "CRowsetImpl::ValidateCommandID | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowsetImpl.ValidateCommandID"
  - "CRowsetImpl::ValidateCommandID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ValidateCommandID (méthode)"
ms.assetid: cdde6088-41bc-4b8f-a32b-f36f7d9b5ec0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowsetImpl::ValidateCommandID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vérifie si l'un ou l'autre ou les deux **DBID**contiennent des valeurs de chaîne et, si tel est le cas, les copie dans ses membres de données [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) et [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## Syntaxe  
  
```  
  
      HRESULT CRowsetBaseImpl::ValidateCommandID(  
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
 Cette méthode est appelée à travers un upcast statique par `CRowsetImpl` pour remplir les membres de données [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) et [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  Par défaut, cette méthode vérifie si l'un ou l'autre ou les deux **DBID**contiennent des valeurs de chaîne et, si tel est le cas, les copie dans ses membres de données.  En plaçant une méthode avec cette signature dans votre classe dérivée `CRowsetImpl`\-, la méthode est appelée au lieu de l'implémentation de base.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [CRowsetImpl, classe](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)