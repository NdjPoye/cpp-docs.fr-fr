---
title: "CTable::Open | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.CTable.Open"
  - "ATL::CTable::Open"
  - "CTable::Open"
  - "CTable.Open"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Open (méthode)"
ms.assetid: 5d006d95-74d7-4e2b-b243-a33bc53b5455
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTable::Open
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ouvre la table.  
  
## Syntaxe  
  
```  
  
      HRESULT Open(  
   const CSession& session,  
   LPCWSTR wszTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   LPCSTR szTableName,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
HRESULT Open(  
   const CSession& session,  
   DBID& dbid,  
   DBPROPSET* pPropSet = NULL,  
   ULONG ulPropSets = 0  
) throw ( );  
```  
  
#### Paramètres  
 `session`  
 \[in\] la session pour laquelle la table est ouverte.  
  
 *wszTableName*  
 \[in\] nom de la table à ouvrir, passé comme chaîne Unicode.  
  
 *szTableName*  
 \[in\] nom de la table à ouvrir, passé comme chaîne ANSI.  
  
 *dbid*  
 \[in\] **DBID** de la table à ouvrir.  
  
 *pPropSet*  
 \[in\] pointeur sur un tableau de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) contenant les propriétés et valeurs à définir.  Voir [Ensembles de propriétés et Groupes de propriétés](https://msdn.microsoft.com/en-us/library/ms713696.aspx) dans le *Guide de référence du programmeur OLE DB* dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  La valeur par défaut de NULL ne spécifie aucune propriété.  
  
 `ulPropSets`  
 \[in\] nombre de structures [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx) passé dans l'argument *pPropSet*.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Pour plus de détails, consultez [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) dans le *OLE DB Programmer's Reference*.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CTable, classe](../../data/oledb/ctable-class.md)