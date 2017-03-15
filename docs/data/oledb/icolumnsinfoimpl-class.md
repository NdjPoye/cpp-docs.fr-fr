---
title: "IColumnsInfoImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IColumnsInfoImpl<T>"
  - "ATL::IColumnsInfoImpl"
  - "IColumnsInfoImpl"
  - "ATL.IColumnsInfoImpl"
  - "ATL::IColumnsInfoImpl<T>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IColumnsInfoImpl (classe)"
ms.assetid: ba74c1c5-2eda-4452-8b57-84919fa0d066
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IColumnsInfoImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une implémentation de l'interface [IColumnsInfo](https://msdn.microsoft.com/en-us/library/ms724541.aspx).  
  
## Syntaxe  
  
```  
template <class T>  
class ATL_NO_VTABLE IColumnsInfoImpl :   
   public IColumnsInfo,    
   public CDBIDOps  
```  
  
#### Paramètres  
 `T`  
 Votre classe, dérivée de `IColumnsInfoImpl`.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[GetColumnInfo](../../data/oledb/icolumnsinfoimpl-getcolumninfo.md)|Retourne les métadonnées de colonne exigées par la plupart des consommateurs.|  
|[MapColumnIDs](../../data/oledb/icolumnsinfoimpl-mapcolumnids.md)|Retourne un tableau des numéros des colonnes dans un jeu de lignes identifiées par les ID de colonne spécifiés.|  
  
## Notes  
 Une interface forcé sur les ensembles de lignes et des commandes.  Pour modifier le comportement de l'implémentation de `IColumnsInfo` de votre fournisseur, vous devez modifier le mappage des colonnes du fournisseur.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)