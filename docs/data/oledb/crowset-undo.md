---
title: "CRowset::Undo | Microsoft Docs"
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
  - "CRowset.Undo"
  - "ATL::CRowset<TAccessor>::Undo"
  - "CRowset<TAccessor>::Undo"
  - "ATL.CRowset.Undo"
  - "ATL.CRowset<TAccessor>.Undo"
  - "CRowset<TAccessor>.Undo"
  - "ATL::CRowset::Undo"
  - "CRowset::Undo"
  - "Undo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Undo (méthode)"
ms.assetid: 1ccd70e2-3931-41c4-893e-a05d0e295410
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset::Undo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Annule tout changement effectuée sur une colonne depuis la dernière récupératoin ou [Mise à jour](../../data/oledb/crowset-update.md).  
  
## Syntaxe  
  
```  
  
      HRESULT Undo(   
   DBCOUNTITEM* pcRows = NULL,   
   HROW* phRow = NULL,   
   DBROWSTATUS* pStatus = NULL    
) throw( );  
```  
  
#### Paramètres  
 `pcRows`  
 \[out\] Pointeur vers l'emplacement où **Annuler** renvoie le nombre de lignes à annuler, si requis.  
  
 `phRow`  
 \[out\] Pointeur vers l'emplacement où **Undo** renvoie un tableau de handles à toutes les lignes à annuler, si requis.  
  
 `pStatus`  
 \[out\] Un pointeur vers l'emplacement où **Undo** renvoie la valeur de l'état de la ligne.  Aucun état n'est renvoyé si `pStatus` est null.  
  
## Valeur de retour  
 Un `HRESULT` standard.  
  
## Notes  
 Cette méthode requiert `IRowsetUpdate` de l'interface optionnelle, qui peut ne pas être supportée par tous les fournisseurs ; si c'est le cas la méthode renvoie **E\_NOINTERFACE**.  Vous devez aussi définir **DBPROP\_IRowsetUpdate** sur `VARIANT_TRUE` avant d'appeler **Open** sur la table ou commande contenant l'ensemble de lignes.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CRowset, classe](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::Undo](https://msdn.microsoft.com/en-us/library/ms719655.aspx)