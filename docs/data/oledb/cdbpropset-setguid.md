---
title: "CDBPropSet::SetGUID | Microsoft Docs"
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
  - "ATL.CDBPropSet.SetGUID"
  - "CDBPropSet.SetGUID"
  - "ATL::CDBPropSet::SetGUID"
  - "SetGUID"
  - "CDBPropSet::SetGUID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddProperty (méthode)"
  - "SetGUID (méthode)"
ms.assetid: a4cce036-cf1f-4897-9712-7b01eaf887ff
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDBPropSet::SetGUID
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Affectez la valeur au champ de **EnsembleProprietesGuide** dans la structure de **DBPROPSET**.  
  
## Syntaxe  
  
```  
  
      void SetGUID(   
   const GUID& guid    
) throw( );  
```  
  
#### Paramètres  
 `guid`  
 \[in\] UN GUIDE utilisé pour définir le champ de **ObtenirProprieteGuide** de la structure de [DBPROPSET](https://msdn.microsoft.com/en-us/library/ms714367.aspx).  
  
## Notes  
 Ce champ peut également être défini par [constructeur](../../data/oledb/cdbpropset-cdbpropset.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDBPropSet, classe](../../data/oledb/cdbpropset-class.md)