---
title: "CBulkRowset, classe | Microsoft Docs"
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
  - "ATL::CBulkRowset"
  - "ATL.CBulkRowset"
  - "ATL::CBulkRowset<TAccessor>"
  - "CBulkRowset"
  - "ATL.CBulkRowset<TAccessor>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBulkRowset (classe)"
ms.assetid: c6bde426-c543-4022-a98a-9519d9e2ae59
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBulkRowset, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère et manipule les lignes pour travailler sur des données en bloc en récupérant plusieurs descripteurs de ligne avec un appel unique.  
  
## Syntaxe  
  
```  
template <class TAccessor>  
class CBulkRowset : public CRowset<TAccessor>  
```  
  
#### Paramètres  
 `TAccessor`  
 Un classe accesseur.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/cbulkrowset-addrefrows.md)|Incrémente le nombre de références.|  
|[CBulkRowset](../../data/oledb/cbulkrowset-cbulkrowset.md)|Constructeur.|  
|[MoveFirst](../../data/oledb/cbulkrowset-movefirst.md)|Récupère la première ligne de données, en effectuant un nouvelle extraction de bloc si nécessaire.|  
|[MoveLast](../../data/oledb/cbulkrowset-movelast.md)|Passe à la dernière ligne.|  
|[MoveNext](../../data/oledb/cbulkrowset-movenext.md)|Extrait la ligne suivante de données.|  
|[MovePrev](../../data/oledb/cbulkrowset-moveprev.md)|Passe à la ligne précédente.|  
|[MoveToBookmark](../../data/oledb/cbulkrowset-movetobookmark.md)|Extrait la ligne marquée par un signet ou la ligne à un nombre de lignes spécifié de ce signet.|  
|[MoveToRatio](../../data/oledb/cbulkrowset-movetoratio.md)|Extrait des lignes en commençant à une position décimale dans l'ensemble de lignes.|  
|[ReleaseRows](../../data/oledb/cbulkrowset-releaserows.md)|Mets la ligne actuelle \(**m\_nCurrentRow**\) à zéro et libère toutes les lignes.|  
|[SetRows](../../data/oledb/cbulkrowset-setrows.md)|Définit le nombre de descripteurs de lignes à extraire avec un appel.|  
  
## Exemple  
 L'exemple suivant illustre l'utilisation de la classe `CBulkRowset`.  
  
 [!code-cpp[NVC_OLEDB_Consumer#1](../../data/oledb/codesnippet/CPP/cbulkrowset-class_1.cpp)]  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)