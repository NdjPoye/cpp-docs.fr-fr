---
title: "CManualAccessor::AddBindEntry | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CManualAccessor::AddBindEntry"
  - "ATL.CManualAccessor.AddBindEntry"
  - "CManualAccessor::AddBindEntry"
  - "AddBindEntry"
  - "CManualAccessor.AddBindEntry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddBindEntry (méthode)"
ms.assetid: 8556dda9-dda1-4f67-96bc-6031e6c6a271
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CManualAccessor::AddBindEntry
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ajoute une entrée de lien aux colonnes de sortie.  
  
## Syntaxe  
  
```  
  
      void AddBindEntry(  
   DBORDINAL nOrdinal,  
   DBTYPE wType,  
   DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL   
) throw ( );  
```  
  
#### Paramètres  
 Consultez [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) dans le *Guide de référence pour programmeur OLE DB*.  
  
 `nOrdinal`  
 \[in\] Numéro de colonne.  
  
 `wType`  
 \[in\] Type de données.  
  
 `nColumnSize`  
 \[in\] Taille de colonne en octets.  
  
 `pData`  
 \[in\] Un pointeur vers les données de la colonne stockées dans la mémoire tampon.  
  
 `pLength`  
 \[in\] Un pointeur vers la longueur du champ, si nécessaire.  
  
 `pStatus`  
 \[in\] Un pointeur vers la variable à lier à l'état de la colonne, si nécessaire.  
  
## Notes  
 Pour utiliser cette fonctionnalité, vous devez commencer par appeler [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md).  Vous ne pouvez pas ajouter plus d'entrées que le nombre de colonnes spécifié dans `CreateAccessor`.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CManualAccessor, classe](../../data/oledb/cmanualaccessor-class.md)   
 [Exemple de DBViewer](../../top/visual-cpp-samples.md)