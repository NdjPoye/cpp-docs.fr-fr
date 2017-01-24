---
title: "CSimpleRow, classe | Microsoft Docs"
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
  - "CSimpleRow"
  - "ATL::CSimpleRow"
  - "ATL.CSimpleRow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleRow (classe)"
ms.assetid: 06d9621d-60cc-4508-8b0c-528d1b1a809b
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleRow, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une implémentation par défaut du gestionnaire de ligne, utilisée dans la classe [IRowsetImpl](../../data/oledb/irowsetimpl-class.md).  
  
## Syntaxe  
  
```  
class CSimpleRow  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[AddRefRow](../../data/oledb/csimplerow-addrefrow.md)|Ajoute un décompte de références à un handle de ligne existant.|  
|[Comparaison](../../data/oledb/csimplerow-compare.md)|Compare deux lignes pour voir si elles font référence à la même instance de ligne.|  
|[CSimpleRow](../../data/oledb/csimplerow-csimplerow.md)|Constructeur.|  
|[ReleaseRow](../../data/oledb/csimplerow-releaserow.md)|Libère des lignes.|  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_dwRef](../../data/oledb/csimplerow-m-dwref.md)|Compteur de références à un gestionnaire de ligne existant.|  
|[m\_iRowset](../../data/oledb/csimplerow-m-irowset.md)|Un index de l'ensemble des lignes représentant le curseur.|  
  
## Notes  
 Un gestionnaire de ligne est logiquement une balise unique d'une ligne de sortie.  `IRowsetImpl` crée un nouvel `CSimpleRow` pour chaque ligne demandée dans [IRowsetImpl::GetNextRows](../../data/oledb/irowsetimpl-getnextrows.md).  `CSimpleRow` peut également être remplacé par votre propre implémentation du gestionnaire de ligne, car il s'agit d'un modèle d'argument par défaut à `IRowsetImpl`.  Le seul impératif pour remplacer cette classe est de faire en sorte que la classe de remplacement fournisse un constructeur qui accepte un seul paramètre de type **LONG**.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [IRowsetImpl, classe](../../data/oledb/irowsetimpl-class.md)