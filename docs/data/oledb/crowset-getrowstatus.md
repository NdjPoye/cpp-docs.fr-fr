---
title: "CRowset::GetRowStatus | Microsoft Docs"
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
  - "CRowset.GetRowStatus"
  - "ATL.CRowset<TAccessor>.GetRowStatus"
  - "ATL::CRowset<TAccessor>::GetRowStatus"
  - "CRowset::GetRowStatus"
  - "ATL::CRowset::GetRowStatus"
  - "CRowset<TAccessor>::GetRowStatus"
  - "ATL.CRowset.GetRowStatus"
  - "CRowset<TAccessor>.GetRowStatus"
  - "GetRowStatus"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetRowStatus (méthode)"
ms.assetid: 7a29a235-cb7e-40c1-92ce-5441751febee
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::GetRowStatus
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne l'état de toutes les lignes.  
  
## Syntaxe  
  
```  
  
      HRESULT GetRowStatus(   
   DBPENDINGSTATUS* pStatus    
) const throw( );  
```  
  
#### Paramètres  
 `pStatus`  
 \[out\] pointeur cvers 'emplacement où `GetRowStatus` renvoie la valeur d'état.  Consultez DBPENDINGSTATUS dans le Guide de référence du programmeur OLE DB.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Cette méthode requiert l'interface facultative `IRowsetUpdate`, qui peut ne pas être prise en charge chez tous les fournisseurs ; dans ce cas, la méthode retourne **E\_NOINTERFACE**.  Vous devez également définir **DBPROP\_IRowsetScroll** sur `VARIANT_TRUE` avant d'appeler **Ouvrir** sur la table ou la commande contenant l'ensemble de lignes.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/en-us/library/ms724377.aspx)