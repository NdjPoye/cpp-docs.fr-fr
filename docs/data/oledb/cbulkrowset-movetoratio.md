---
title: "CBulkRowset::MoveToRatio | Microsoft Docs"
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
  - "CBulkRowset.MoveToRatio"
  - "ATL::CBulkRowset::MoveToRatio"
  - "MoveToRatio"
  - "CBulkRowset::MoveToRatio"
  - "ATL.CBulkRowset<TAccessor>.MoveToRatio"
  - "ATL::CBulkRowset<TAccessor>::MoveToRatio"
  - "ATL.CBulkRowset.MoveToRatio"
  - "CBulkRowset<TAccessor>::MoveToRatio"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToRatio (méthode)"
ms.assetid: 86be60f5-9341-44c1-8e1e-9174c082d0d5
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset::MoveToRatio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Extrait des lignes en commençant à une position décimale dans l'ensemble de lignes.  
  
## Syntaxe  
  
```  
  
      HRESULT MoveToRatio(  
   DBCOUNTITEM nNumerator,  
   DBCOUNTITEM nDenominator   
) throw( );  
```  
  
#### Paramètres  
 `nNumerator`  
 \[in\] le numérateur utilisé pour déterminer la position décimale à partir de laquelle extraire des données.  
  
 `nDenominator`  
 \[in\] le dénominateur utilisé pour déterminer la position décimale à partir de laquelle extraire des données.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 `MoveToRatio` extrait les lignes approximativement selon la formule suivante :  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 Où `RowsetSize` est la taille de l'ensemble de lignes, mesurée en lignes.  La précision de cette formule dépend du fournisseur spécifique.  Pour plus d'informations, consultez l'[IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx) dans le *Guide de référence du programmeur OLE DB*.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CBulkRowset, classe](../../data/oledb/cbulkrowset-class.md)