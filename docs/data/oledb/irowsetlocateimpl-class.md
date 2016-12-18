---
title: "IRowsetLocateImpl, classe | Microsoft Docs"
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
  - "IRowsetLocateImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "signets, OLE DB"
  - "IRowsetLocateImpl (classe)"
  - "fournisseurs, signets"
ms.assetid: a8aa3149-7ce8-4976-a680-2da193fd3234
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetLocateImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implémente l'interface OLE DB [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx), pour extraire des lignes aléatoires d'un ensemble de lignes.  
  
## Syntaxe  
  
```  
template <  
   class T,   
   class RowsetInterface,   
   class RowClass = CSimpleRow,   
   class MapClass = CAtlMap < RowClass::KeyType, RowClass* >,   
   class BookmarkKeyType = LONG,   
   class BookmarkType = LONG,   
   class BookmarkMapClass = CAtlMap < RowClass::KeyType, RowClass* >  
>  
class ATL_NO_VTABLE IRowsetLocateImpl : public IRowsetImpl<  
   T,   
   RowsetInterface,   
   RowClass,   
   MapClass  
>  
```  
  
#### Paramètres  
 `T`  
 Une classe dérivée de `IRowsetLocateImpl`.  
  
 `RowsetInterface`  
 Une classe dérivée de `IRowsetImpl`.  
  
 `RowClass`  
 L'unité de stockage pour le **HROW**.  
  
 `MapClass`  
 L'unité de stockage pour les handles de ligne gérés par le fournisseur.  
  
 `BookmarkKeyType`  
 Le type du signet, par exemple un LONG ou une chaîne.  Les signets ordinaires doivent avoir une longueur d'au moins deux octets. \(La longueur codés sur un octet est réservée pour les [signets standard](https://msdn.microsoft.com/en-us/library/ms712954.aspx) OLE DB **DBBMK\_FIRST**, **DBBMK\_LAST**, et **DBBMK\_INVALID**.\)  
  
 `BookmarkType`  
 Le mécanisme de mappage pour gérer les relations de signet\-à\-données.  
  
 `BookmarkMapClass`  
 L'unité de stockage pour les handles de ligne gérés par le signet.  
  
## Membres  
  
### Méthodes d'interface  
  
|||  
|-|-|  
|[Comparaison](../../data/oledb/irowsetlocateimpl-compare.md)|Compare deux signets.|  
|[GetRowsAt](../../data/oledb/irowsetlocateimpl-getrowsat.md)|Extrait les lignes commençant par la ligne spécifiée par un offset dans un signet.|  
|[GetRowsByBookmark](../../data/oledb/irowsetlocateimpl-getrowsbybookmark.md)|Extrait les lignes qui correspondent aux signets spécifiés.|  
|[Hachage](../../data/oledb/irowsetlocateimpl-hash.md)|Retourne des valeurs de hachage pour les signets spécifiés.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_rgBookmarks](../../data/oledb/irowsetlocateimpl-m-rgbookmarks.md)|Un tableau de signets.|  
  
## Notes  
 `IRowsetLocateImpl` est l'implémentation de modèles OLE DB de l'interface [IRowsetLocate](https://msdn.microsoft.com/en-us/library/ms721190.aspx).  `IRowsetLocate` est utilisé pour extraire les lignes aléatoires d'un ensemble de lignes.  Un ensemble de lignes qui n'implémente pas cette interface est un ensemble de lignes `sequential`.  Lorsque `IRowsetLocate` est présent sur un ensemble de lignes, la colonne 0 est le signet pour les lignes ; la lecture cette colonne obtiendra une valeur de signet qui peut être utilisée pour repositionner la même ligne.  
  
 `IRowsetLocateImpl` est utilisé pour implémenter la prise en charge des signets dans les fournisseurs.  Les signets sont des espaces réservés \(index dans un ensemble de lignes\) qui permettent au consommateur de revenir rapidement à une ligne, ce qui permet l'accès à haute vitesse des données.  Le fournisseur détermine quels signets peuvent identifier une ligne de manière uique.  En utilisant des méthodes `IRowsetLocateImpl`, vous pouvez comparer des signets, extraire des lignes par décalage, extraire les lignes par signet, et retourner des valeurs de hachage pour des signets.  
  
 Pour prendre en charge les signets OLE DB dans un ensemble de lignes, faites l'ensemble de lignes hériter de cette classe.  
  
 Pour plus d'informations sur l'implémentation de la prise en charge des signets, consultez [Prise en charge par le fournisseur des signets](../../data/oledb/provider-support-for-bookmarks.md) dans le *Visual C\+\+ Programmer's Guide* et [Signets](https://msdn.microsoft.com/en-us/library/ms709728.aspx) dans le *OLE DB Programmer's Reference* dans `Platform``SDK`.  
  
## Configuration requise  
 **En\-tête :** : atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetLocate:IRowset](https://msdn.microsoft.com/en-us/library/ms721190.aspx)   
 [Prise en charge des signets par le fournisseur](../../data/oledb/provider-support-for-bookmarks.md)   
 [Bookmarks](https://msdn.microsoft.com/en-us/library/ms709728.aspx)