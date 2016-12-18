---
title: "CRowset, classe | Microsoft Docs"
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
  - "ATL.CRowset<TAccessor>"
  - "CRowset"
  - "ATL::CRowset"
  - "ATL::CRowset<TAccessor>"
  - "ATL.CRowset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CRowset (classe)"
ms.assetid: b0228a90-b8dd-47cc-b397-8d4c15c1e7f4
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CRowset, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule un objet d'ensemble de lignes OLE DB et plusieurs interfaces qui y sont liées et fournit les méthodes de manipulation des données d'un ensemble de lignes.  
  
## Syntaxe  
  
```  
template <class TAccessor = CAccessorBase>  
class CRowset  
```  
  
#### Paramètres  
 `TAccessor`  
 Un classe accesseur.  La valeur par défaut est `CAccessorBase`.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[AddRefRows](../../data/oledb/crowset-addrefrows.md)|Incrémente le nombre de références associées à la ligne actuelle.|  
|[Fermer](../../data/oledb/crowset-close.md)|Libères des lignes et l'interface actuelle de l'interface `IRowset`.|  
|[Comparaison](../../data/oledb/crowset-compare.md)|Compare deux signets en utilisant [IRowsetLocate::Compare](https://msdn.microsoft.com/en-us/library/ms709539.aspx).|  
|[CRowset](../../data/oledb/crowset-crowset.md)|Crée un nouvel objet `CRowset` et l'associe \(éventuellement\) avec une interface **IRowset**  fournie en tant que paramètre.|  
|[Supprimer](../../data/oledb/crowset-delete.md)|Suppressime des lignes de l'ensemble de lignes à l'aide de [IRowsetChange:DeleteRows](https://msdn.microsoft.com/en-us/library/ms724362.aspx).|  
|[FindNextRow](../../data/oledb/crowset-findnextrow.md)|Recherche la ligne correspondante suivante après le signet spécifié.|  
|[GetApproximatePosition](../../data/oledb/crowset-getapproximateposition.md)|Retourne la position approximative d'une ligne correspondant à un signet.|  
|[GetData](../../data/oledb/crowset-getdata.md)|Récupère des données de la copie du jeu de lignes de la ligne.|  
|[GetDataHere](../../data/oledb/crowset-getdatahere.md)|Récupère les données de la mémoire tampon spécifiée.|  
|[GetOriginalData](../../data/oledb/crowset-getoriginaldata.md)|Récupère les données récemment transmises ou obtenues de la source de données, en ignorant les modifications en attente.|  
|[GetRowStatus](../../data/oledb/crowset-getrowstatus.md)|Retourne l'état de toutes les lignes.|  
|[Insert](../../data/oledb/crowset-insert.md)|Crée et insère une nouvelle ligne en utilisant [IRowsetChange:InsertRow](https://msdn.microsoft.com/en-us/library/ms716921.aspx).|  
|[IsSameRow](../../data/oledb/crowset-issamerow.md)|Compare la rangée spécifiée à la rangée actuelle.|  
|[MoveFirst](../../data/oledb/crowset-movefirst.md)|Repositionne la position d'extraction suivante à sa position initiale.|  
|[MoveLast](../../data/oledb/crowset-movelast.md)|Déplace jusqu'au dernier enregistrement|  
|[MoveNext](../../data/oledb/crowset-movenext.md)|Extrait des données de la ligne séquentielle suivante ou un nombre spécifié de positions au delà de la ligne suivante.|  
|[MovePrev](../../data/oledb/crowset-moveprev.md)|Pour revenir à l'enregistrement précédent|  
|[MoveToBookmark](../../data/oledb/crowset-movetobookmark.md)|Extrait la ligne marquée par un signet ou la ligne à un nombre de lignes spécifié de ce signet.|  
|[MoveToRatio](../../data/oledb/crowset-movetoratio.md)|Extrait des lignes en commençant à une position décimale dans l'ensemble de lignes.|  
|[ReleaseRows](../../data/oledb/crowset-releaserows.md)|Appelle [IRowset::ReleaseRows](https://msdn.microsoft.com/en-us/library/ms719771.aspx) pour libérer le handle de ligne actuelle.|  
|[SetData](../../data/oledb/crowset-setdata.md)|Définit des valeurs de données dans une colonne ou plus d'une ligne en utilisant [IRowsetChange:SetData](https://msdn.microsoft.com/en-us/library/ms721232.aspx).|  
|[Annuler](../../data/oledb/crowset-undo.md)|Annule toutes les modifications apportées à une ligne depuis la dernière extraction ou [Mise à jour](../../data/oledb/crowset-update.md).|  
|[Update](../../data/oledb/crowset-update.md)|Transfère les modifications en attente apportées à la ligne en cours depuis la dernière extraction.|  
|[UpdateAll](../../data/oledb/crowset-updateall.md)|CRowset::UpdateAll transfère les modifications en attente apportées à toutes les lignes depuis la dernière extraction ou mise à jour.|  
  
## Notes  
 Dans OLE DB, un ensemble de lignes est l'objet dans lequel un programme définit et extrait des données.  
  
 Cette classe n'est pas destinée à être instanciée mais plutôt passée comme paramètre de modèle à `CTable` ou à `CCommand` \(`CRowset` est la valeur par défaut\).  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Exemple de DBViewer](../../top/visual-cpp-samples.md)   
 [Exemple de MultiRead](../../top/visual-cpp-samples.md)   
 [Exemple d'attributs de MultiRead](../../top/visual-cpp-samples.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)