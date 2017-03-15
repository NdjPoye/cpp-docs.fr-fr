---
title: "IRowsetChangeImpl Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::IRowsetChangeImpl"
  - "IRowsetChangeImpl"
  - "ATL.IRowsetChangeImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IRowsetChangeImpl (classe)"
  - "fournisseurs, pouvant être mis à jour"
  - "fournisseurs pouvant être mis à jour, mise à jour immédiate"
ms.assetid: 1e9fee15-ed9e-4387-af8f-215569beca6c
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# IRowsetChangeImpl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'implémentation de modèles OLE DB de l'interface [IRowsetChange](https://msdn.microsoft.com/en-us/library/ms715790.aspx) dans la spécification OLE DB.  
  
## Syntaxe  
  
```  
template <  
   class T,   
   class Storage,   
   class BaseInterface = IRowsetChange,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >   
>  
class ATL_NO_VTABLE IRowsetChangeImpl : public BaseInterface  
```  
  
#### Paramètres  
 `T`  
 Une classe dérivée de `IRowsetChangeImpl`.  
  
 `Storage`  
 L'enregistrement utilisateur  
  
 `BaseInterface`  
 La classe de base pour l'interface, comme `IRowsetChange`.  
  
 `RowClass`  
 L'unité de stockage de le handle de ligne.  
  
 `MapClass`  
 L'unité de stockage pour les handles de ligne gérés par le fournisseur.  
  
## Membres  
  
### Méthodes de l'interface \(utilisées avec IRowsetChange\)  
  
|||  
|-|-|  
|[DeleteRows](../../data/oledb/irowsetchangeimpl-deleterows.md)|Supprime des lignes de l'ensemble de lignes.|  
|[InsertRow](../../data/oledb/irowsetchangeimpl-insertrow.md)|Insère une ligne dans l'ensemble de lignes.|  
|[SetData](../../data/oledb/irowsetchangeimpl-setdata.md)|Définit les valeurs de données dans une ou plusieurs colonnes d'une ligne.|  
  
### Méthode d'implémentation \(rappel\)  
  
|||  
|-|-|  
|[FlushData](../../data/oledb/irowsetchangeimpl-flushdata.md)|Overidden par le fournisseur pour soumettre des données à son magasin.|  
  
## Notes  
 Cette interface est responsables des opérations d'écriture immédiate dans un magasin de données. « Immédiat » signifie que lorsque l'utilisateur final \(la personne utilisant le consommateur\) effectue une modifications, ces modifications sont immédiatement transmises à la banque de données \(et ne peuvent pas être annulée\).  
  
 `IRowsetChangeImpl` implémente l'interface OLE DB `IRowsetChange`, qui permet de mettre à jour les valeurs des colonnes dans les lignes, supprimer des lignes, puis insérer de nouvelles lignes.  
  
 L'implémentation de modèles OLE DB prend en charge toutes les méthodes de base \(`SetData`, `InsertRow`, et `DeleteRows`\).  
  
> [!IMPORTANT]
>  Il est fortement recommandé de lire la documentation suivante AVANT toute tentative d'implémenter votre fournisseur :  
  
-   [Création d'un fournisseur actualisable](../../data/oledb/creating-an-updatable-provider.md)  
  
-   Chapitre 6 de *OLE DB Programmer's Reference*  
  
-   Consultez également comment la classe `RUpdateRowset` est utilisée dans l'exemple de UpdatePV  
  
## Configuration requise  
 **En\-tête:** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)