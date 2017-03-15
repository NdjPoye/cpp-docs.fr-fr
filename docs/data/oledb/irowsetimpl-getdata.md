---
title: "IRowsetImpl::GetData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetImpl.GetData"
  - "ATL::IRowsetImpl::GetData"
  - "IRowsetImpl::GetData"
  - "IRowsetImpl.GetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetData (méthode) (OLE DB)"
ms.assetid: cb15f1cc-bd25-4b74-93c3-db71aa93829c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::GetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère des données de la copie du jeu de lignes de la ligne.  
  
## Syntaxe  
  
```  
  
      STDMETHOD( GetData )(  
   HROW hRow,  
   HACCESSOR hAccessor,  
   void* pDstData   
);  
```  
  
#### Paramètres  
 Consultez [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) dans le *Guide du Programmeur OLE DB*.  
  
 Certains paramètres correspondent aux paramètres du *Guide de référence du programmeur OLE DB* ayant des noms différents, qui sont décrits dans **IRowset::GetData**:  
  
|Paramètres de modèle OLE DB|Paramètres *Guide de référence du programmeur OLE DB*|  
|---------------------------------|-----------------------------------------------------------|  
|*pDstData*|`pData`|  
  
## Notes  
 Gère également la conversion de données en utilisant la DLL de conversion de données OLE DB.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)