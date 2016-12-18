---
title: "CRowset::Compare | Microsoft Docs"
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
  - "CRowset<TAccessor>.Compare"
  - "CRowset<TAccessor>::Compare"
  - "ATL.CRowset<TAccessor>.Compare"
  - "ATL::CRowset<TAccessor>::Compare"
  - "CRowset.Compare"
  - "ATL::CRowset::Compare"
  - "ATL.CRowset.Compare"
  - "CRowset::Compare"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Compare (méthode)"
ms.assetid: a8117b40-7abd-4867-b0ba-eb9e9808204e
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::Compare
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Compare deux signets en utilisant [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx).  
  
## Syntaxe  
  
```  
  
      HRESULT Compare(   
   const CBookmarkBase& bookmark1,   
   const CBookmarkBase& bookmark2,   
   DBCOMPARE* pComparison    
) const throw( );  
```  
  
#### Paramètres  
 *Bookmark1*  
 \[in\] Premier signet à comparer.  
  
 *Bookmark2*  
 \[in\] Second signet à comparer.  
  
 `pComparison`  
 \[out\] Un pointeur vers le résultat de la comparaison.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Cette méthode requiert l'interface facultative `IRowsetLocate`, qui peut ne pas être prise en charge chez tous les fournisseurs ; dans ce cas, la méthode retourne **E\_NOINTERFACE**.  Vous devez également définir **DBPROP\_IRowsetLocate** sur `VARIANT_TRUE` avant d'appeler **Ouvrir** sur la table ou la commande contenant l'ensemble de lignes.  
  
 Pour plus d'informations sur l'utilisation de signets dans les consommateurs, consultez [Utilisation de signets](../../data/oledb/using-bookmarks.md).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)