---
title: "CRowsetImpl::GetCommandFromID | Microsoft Docs"
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
  - "CRowsetImpl::GetCommandFromID"
  - "GetCommandFromID"
  - "CRowsetImpl.GetCommandFromID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetCommandFromID (méthode)"
ms.assetid: 9f39cb07-1c40-486f-ba5b-cb4a65fab8a7
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowsetImpl::GetCommandFromID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vérifie si l'un ou l'autre ou les deux paramètres contiennent des valeurs de chaîne et, le cas échéant, copie les valeurs de chaîne aux membres de données [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) et [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  
  
## Syntaxe  
  
```  
  
      HRESULT CRowsetBaseImpl::GetCommandFromID(  
   DBID* pTableID,  
   DBID* pIndexID   
);  
```  
  
#### Paramètres  
 `pTableID`  
 \[in\] pointeur à **DBID** qui représente l'ID de table  
  
 `pIndexID`  
 \[in\] pointeur à **DBID** qui représente l'ID de l'Index.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Cette méthode est appelée par un upcast statique par `CRowsetImpl` pour remplir les membres de données [m\_strCommandText](../../data/oledb/crowsetimpl-m-strcommandtext.md) et [m\_strIndexText](../../data/oledb/crowsetimpl-m-strindextext.md).  Par défaut, cette méthode vérifie si l'un ou l'autre ou les deux paramètres contiennent des valeurs de chaîne.  Si elles contiennent des valeurs de chaîne, cette méthode copie les valeurs de chaîne aux membres de données.  En plaçant une méthode à cette signature dans votre `CRowsetImpl`\- la classe dérivée, la méthode est appelée au lieu de l'implémentation de base.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [CRowsetImpl, classe](../../data/oledb/crowsetimpl-class.md)   
 [CRowsetImpl::SetCommandText](../../data/oledb/crowsetimpl-setcommandtext.md)