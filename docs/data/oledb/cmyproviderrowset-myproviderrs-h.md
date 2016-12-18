---
title: "CMyProviderRowset (MyProviderRS.H) | Microsoft Docs"
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
  - "cmyproviderrowset"
  - ""myproviderrs.h""
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMyProviderRowset (classe dans MyProviderRS.H)"
  - "fournisseurs OLE DB, fichiers générés par l'Assistant"
ms.assetid: 7ba1a124-3842-40eb-a36b-302190a1af3a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMyProviderRowset (MyProviderRS.H)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

L'Assistant génère une entrée pour l'objet rowset.  En ce cas, elle est appelée `CMyProviderRowset`.  La classe `CMyProviderRowset` hérite d'une classe de fournisseur OLE DB appelée `CRowsetImpl`, qui implémente toutes les interfaces nécessaires pour l'objet rowset.  Le code suivant montre la chaîne d'héritage de la classe `CRowsetImpl` :  
  
```  
template <class T, class Storage, class CreatorClass,   
   class ArrayType = CAtlArray<Storage> >  
class CMyRowsetImpl:  
   public CRowsetImpl<T, Storage, CreatorClass, ArrayType,   
      CSimpleRow, IRowsetLocateImpl< T > >  
```  
  
 `CRowsetImpl` utilise également les interfaces `IAccessor` et `IColumnsInfo`.  Elle utilise ces interfaces pour les champs de sortie dans les tables.  La classe assure également une implémentation pour **IRowsetIdentity**, qui permet au consommateur de déterminer si deux lignes sont identiques.  L'interface `IRowsetInfo` implémente les propriétés de l'objet rowset.  L'interface **IConvertType** permet au fournisseur de gommer les différences entre les types de données demandés par le consommateur et ceux utilisés par le fournisseur.  
  
 L'interface `IRowset` gère en fait la récupération des données.  Le consommateur appelle d'abord une méthode nommée `GetNextRows` pour retourner un handle à une ligne, appelé **HROW**.  Le consommateur appelle ensuite **IRowset::GetData** à l'aide de **HROW** pour récupérer les données demandées.  
  
 `CRowsetImpl` prend également plusieurs paramètres de modèles.  Ces paramètres permettent de déterminer comment la classe `CRowsetImpl` gère les données.  L'argument `ArrayType` permet de déterminer le mécanisme de stockage qui est utilisé pour stocker les données de ligne.  Le paramètre **RowClass** spécifie la classe qui contient une **HROW**.  
  
 Le paramètre **RowsetInterface** permet aussi d'utiliser l'interface `IRowsetLocate` ou `IRowsetScroll`.  Les interfaces `IRowsetLocate` et `IRowsetScroll` héritent toutes les deux de l'interface `IRowset`.  Par conséquent, les modèles du fournisseur OLE DB doivent assurer une gestion spéciale pour ces interfaces.  Si vous souhaitez utiliser l'une de ces interfaces, vous devez alors faire appel à ce paramètre.  
  
## Voir aussi  
 [Fichiers générés par l'Assistant Fournisseur](../../data/oledb/provider-wizard-generated-files.md)