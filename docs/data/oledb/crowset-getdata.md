---
title: "CRowset::GetData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset<TAccessor>::GetData"
  - "ATL::CRowset<TAccessor>::GetData"
  - "ATL::CRowset::GetData"
  - "ATL.CRowset<TAccessor>.GetData"
  - "CRowset<TAccessor>.GetData"
  - "CRowset::GetData"
  - "CRowset.GetData"
  - "ATL.CRowset.GetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetData (méthode) (OLE DB)"
ms.assetid: 1e0347b5-3e24-4ff8-a790-839616c1522f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::GetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère des données de la copie du jeu de lignes de la ligne.  
  
## Syntaxe  
  
```  
  
      HRESULT GetData( ) throw( );   
HRESULT GetData(   
   int nAccessor    
) throw( );  
```  
  
#### Paramètres  
 `nAccessor`  
 \[in\] le numéro d'indice \(sans décalage\) de l'accesseur à utiliser pour accéder aux données.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Si vous spécifiez un accesseur qui n'est pas un autoaccesseur dans [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md), utilisez cette méthode pour obtenir les données de manière explicite en passant le numéro d'accesseur.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)