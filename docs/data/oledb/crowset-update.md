---
title: "CRowset::Update | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CRowset.Update"
  - "ATL.CRowset.Update"
  - "ATL.CRowset<TAccessor>.Update"
  - "ATL::CRowset<TAccessor>::Update"
  - "CRowset<TAccessor>::Update"
  - "CRowset::Update"
  - "CRowset<TAccessor>.Update"
  - "ATL::CRowset::Update"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Update (méthode)"
ms.assetid: cd5fedc8-2b85-4cb8-8c40-c79576316903
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CRowset::Update
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Transfère les modifications en attente apportées à la ligne en cours depuis la dernière extraction ou la dernière mise à jour **CRowset::Update** la concernant.  
  
## Syntaxe  
  
```  
  
      HRESULT Update(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### Paramètres  
 `pcRows`  
 \[out\] Un pointeur à l'emplacement où **\-Update** retourne le nombre de lignes qu'il a essayé de mettre à jour, si nécessaire.  
  
 `phRow`  
 \[out\] le pointeur à l'emplacement où **Mettre à jour** retourne le descripteur de la ligne qu'il a essayé de mettre à jour.  Aucun descripteur n'est retourné si `phRow` est null.  
  
 `pStatus`  
 \[out\] Un pointeur sur l'emplacement où **Mettre à jour** retourne la valeur d'état de ligne.  Aucun état n'est retourné si `pStatus` est null.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Transmet toutes les modifications en attente apportées à la ligne actuelle depuis que la ligne a reçu la dernière extraction ou été mise à jour \(en utilisant **Mettre à jour** ou [UpdateAll](../../data/oledb/crowset-updateall.md)\).  Vous appelez en général [SetData](../../data/oledb/crowset-setdata.md) pour définir des valeurs de données à la suite dans les colonnes, puis appelez **Mettre à jour** pour transmettre ces modifications.  
  
 Cette méthode requiert l'interface facultative `IRowsetUpdate`, qui peut ne pas être prise en charge chez tous les fournisseurs ; dans ce cas, la méthode retourne **E\_NOINTERFACE**.  Vous devez également définir **DBPROP\_IRowsetScroll** sur `VARIANT_TRUE` avant d'appeler **Ouvrir** sur la table ou la commande contenant l'ensemble de lignes.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Update](https://msdn.microsoft.com/en-us/library/ms719709.aspx)   
 [CRowset::UpdateAll](../../data/oledb/crowset-updateall.md)   
 [CRowset::SetData](../../data/oledb/crowset-setdata.md)