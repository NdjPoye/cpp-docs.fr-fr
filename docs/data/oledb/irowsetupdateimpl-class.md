---
title: "IRowsetUpdateImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IRowsetUpdateImpl"
  - "ATL.IRowsetUpdateImpl"
  - "ATL::IRowsetUpdateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetUpdateImpl (classe)"
  - "fournisseurs, pouvant être mis à jour"
  - "fournisseurs pouvant être mis à jour, mise à jour différée"
ms.assetid: f85af76b-ab6f-4f8b-8f4a-337c9679d68f
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IRowsetUpdateImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'implémentation de modèles DB OLE de l'interface [oledbirowsetupdate\_\_\_irowsetchange](https://msdn.microsoft.com/en-us/library/ms714401.aspx).  
  
## Syntaxe  
  
```  
template <  
   class T,   
   class Storage,   
   class UpdateArray = CAtlArray<Storage>,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap <RowClass::KeyType, RowClass*>   
>  
class IRowsetUpdateImpl : public IRowsetChangeImpl<  
   T,   
   Storage,   
   IRowsetUpdate,   
   RowClass,   
   MapClass  
>  
```  
  
#### Paramètres  
 `T`  
 Une classe dérivée de `IRowsetUpdateImpl`.  
  
 `Storage`  
 L'enregistrement utilisateur  
  
 `UpdateArray`  
 Un tableau contenant les données mises en cache pour mettre à jour l'ensemble de lignes.  
  
 `RowClass`  
 L'unité de stockage pour le **HROW**.  
  
 `MapClass`  
 L'unité de stockage pour les handles de ligne gérés par le fournisseur.  
  
## Membres  
  
### Méthodes de l'interface \(utilisées avec IRowsetChange\)  
  
|||  
|-|-|  
|[SetData](../../data/oledb/irowsetupdateimpl-setdata.md)|Définit les valeurs de données dans une ou plusieurs colonnes d'une ligne.|  
  
### Méthodes d'interface \(utilisées avec IRowsetUpdate\)  
  
|||  
|-|-|  
|[GetOriginalData](../../data/oledb/irowsetupdateimpl-getoriginaldata.md)|Obtient les données récemment transmises ou obtenues de la source de données, en ignorant les modifications en attente.|  
|[GetPendingRows](../../data/oledb/irowsetupdateimpl-getpendingrows.md)|Retourne une liste de lignes avec des modifications en attente.|  
|[GetRowStatus](../../data/oledb/irowsetupdateimpl-getrowstatus.md)|Retourne l'état de lignes spécifiées.|  
|[Annuler](../../data/oledb/irowsetupdateimpl-undo.md)|Transmet toutes les modifications apportées à la ligne depuis la dernière extraction ou mise à jour.|  
|[Update](../../data/oledb/irowsetupdateimpl-update.md)|Transmet toutes les modifications apportées à la ligne depuis la dernière extraction ou mise à jour.|  
  
### Méthodes d'implémentation \(rappel\)  
  
|||  
|-|-|  
|[IsUpdateAllowed](../../data/oledb/irowsetupdateimpl-isupdateallowed.md)|Utilisé pour vérifier la sécurité, intégrité, etc. avant d'autoriser les mises à jour.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_mapCachedData](../../data/oledb/irowsetupdateimpl-m-mapcacheddata.md)|Contient les données d'origine pour l'opération différée.|  
  
## Notes  
 Vous devez d'abord lire et comprendre la documentation de [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx), car tout ce qui y est décrit s'applique également ici.  Vous devez également lire le chapitre 6 de `OLE``DB``Programmer's``Reference` sur les données de paramètre.  
  
 `IRowsetUpdateImpl` implémente l'interface OLE DB `IRowsetUpdate`, qui permet aux consommateurs de retarder la transmission des modifications apportées avec `IRowsetChange` à la source de données et pour annuler les modifications avant transmission.  
  
> [!IMPORTANT]
>  Il est fortement recommandé de lire la documentation suivante AVANT toute tentative d'implémenter votre fournisseur :  
  
-   [Création d'un fournisseur actualisable](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Chapitre 6 du `OLE``DB``Programmer's``Reference`  
  
-   Consultez également comment la classe `RUpdateRowset` est utilisée dans l'exemple de UpdatePV  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur actualisable](../../data/oledb/creating-an-updatable-provider.md)