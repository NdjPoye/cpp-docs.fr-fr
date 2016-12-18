---
title: "CRowset::MoveToRatio | Microsoft Docs"
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
  - "MoveToRatio"
  - "CRowset<TAccessor>::MoveToRatio"
  - "CRowset::MoveToRatio"
  - "CRowset<TAccessor>.MoveToRatio"
  - "ATL.CRowset.MoveToRatio"
  - "ATL::CRowset::MoveToRatio"
  - "CRowset.MoveToRatio"
  - "ATL.CRowset<TAccessor>.MoveToRatio"
  - "ATL::CRowset<TAccessor>::MoveToRatio"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MoveToRatio (méthode)"
ms.assetid: 1fa313bd-8fd1-4608-8e85-44993b97dd88
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::MoveToRatio
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Extrait des lignes en commençant à une position décimale dans l'ensemble de lignes.  
  
## Syntaxe  
  
```  
  
      HRESULT MoveToRatio(   
   DBCOUNTITEM nNumerator,   
   DBCOUNTITEM nDenominator,   
   bool bForward = true    
) throw( );  
```  
  
#### Paramètres  
 `nNumerator`  
 \[in\] le numérateur utilisé pour déterminer la position décimale à partir de laquelle extraire des données.  
  
 `nDenominator`  
 \[in\] le dénominateur utilisé pour déterminer la position décimale à partir de laquelle extraire des données.  
  
 `bForward`  
 \[in\] indique si le déplacement est en avant ou en arrière.  La valeur par défaut est en avant.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 `MoveToRatio` extrait des lignes selon la formule suivante approximativement :  
  
 `( nNumerator *  RowsetSize ) / nDenominator`  
  
 où `RowsetSize` est la taille de l'ensemble de lignes, mesurée en lignes.  La précision de cette formule dépend du fournisseur spécifique.  Pour plus d'informations, consultez [IRowsetScroll::GetRowsAtRatio](https://msdn.microsoft.com/en-us/library/ms709602.aspx).  
  
 Cette méthode requiert l'interface facultative `IRowsetScroll`, qui ne peut pas être prise en charge sur tous les fournisseurs ; dans ce cas, la méthode retourne **E\_NOINTERFACE**.  Vous devez également définir **DBPROP\_IRowsetScroll** sur `VARIANT_TRUE` avant d'appeler **Ouvrir** sur la table ou la commande contenant l'ensemble de lignes.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)