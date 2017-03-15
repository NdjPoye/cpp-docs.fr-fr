---
title: "IRowsetImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetImpl (classe)"
ms.assetid: 6a9189af-7556-45b1-adcb-9d62bb36704c
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IRowsetImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une implémentation de l'interface `IRowset`.  
  
## Syntaxe  
  
```  
template <  
   class T,   
   class RowsetInterface,  
   class RowClass = CSimpleRow,  
   class MapClass = CAtlMap <  
      RowClass::KeyType,  
      RowClass*   
   >  
>  
class ATL_NO_VTABLE IRowsetImpl : public RowsetInterface  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IRowsetImpl`.  
  
 `RowsetInterface`  
 Une classe dérivée de `IRowsetImpl`.  
  
 `RowClass`  
 L'unité de stockage pour le **HROW**.  
  
 `MapClass`  
 L'unité de stockage pour les handles de ligne gérés par le fournisseur.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md)|Ajoute un décompte de références à un handle de ligne existant.|  
|[CreateRow](../../data/oledb/irowsetimpl-createrow.md)|Appelé par [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md) pour allouer nouveau **HROW**.  Pas appelé directement par l'utilisateur.|  
|[GetData](../../data/oledb/irowsetimpl-getdata.md)|Récupère des données de la copie du jeu de lignes de la ligne.|  
|[GetDBStatus](../../data/oledb/irowsetimpl-getdbstatus.md)|Renvoie les indicateurs d'état du champ spécifié.|  
|[GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md)|Extrait des lignes séquentiellement, en mémorisant la position précédente.|  
|[IRowsetImpl](../../data/oledb/irowsetimpl-class.md)|Constructeur.  Pas appelé directement par l'utilisateur.|  
|[RefRows](../../data/oledb/irowsetimpl-refrows.md)|Appelé par [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) et [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md).  Pas appelé directement par l'utilisateur.|  
|[ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md)|Libère des lignes.|  
|[RestartPosition](../../data/oledb/irowsetimpl-restartposition.md)|Replace la prochaine position d'extraction dans sa position initiale ; autrement dit, sa position quand l'ensemble de lignes a été créé la première fois.|  
|[SetDBStatus](../../data/oledb/irowsetimpl-setdbstatus.md)|Fixe les indicateurs d'état du champ spécifié.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_bCanFetchBack](../../data/oledb/irowsetimpl-m-bcanfetchback.md)|Indique si un fournisseur prend en charge l'extraction vers l'arrière.|  
|[m\_bCanScrollBack](../../data/oledb/irowsetimpl-m-bcanscrollback.md)|Indique si un fournisseur peut faire défiler le curseur vers l'abonné.|  
|[m\_bReset](../../data/oledb/irowsetimpl-m-breset.md)|Indique si un fournisseur a réinitialisé la position du curseur.  Cela une signification spéciale dans le défilement vers l'arrière ou lors de l'extraction vers l'arrière dans [GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md).|  
|[m\_iRowset](../../data/oledb/irowsetimpl-m-irowset.md)|Un index de l'ensemble des lignes, représentant le curseur.|  
|[m\_rgRowHandles](../../data/oledb/irowsetimpl-m-rgrowhandles.md)|Une liste des poignées de ligne.|  
  
## Notes  
 [IRowset](https://msdn.microsoft.com/en-us/library/ms720986.aspx) est l'interface de base des ensembles de lignes.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)