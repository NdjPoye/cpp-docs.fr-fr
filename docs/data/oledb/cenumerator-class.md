---
title: "CEnumerator, classe | Microsoft Docs"
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
  - "CEnumerator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEnumerator (classe)"
ms.assetid: 25805f1b-26e3-402f-af83-1b5fe5ddebf7
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CEnumerator, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilise un objet énumérateur OLE DB, qui expose l'interface d' [ISourcesRowset](https://msdn.microsoft.com/en-us/library/ms715969.aspx) pour retourner un ensemble de lignes décrivant les sources de données et énumérateurs.  
  
## Syntaxe  
  
```  
class CEnumerator :   
   public CAccessorRowset< CAccessor <CEnumeratorAccessor >>  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Find](../../data/oledb/cenumerator-find.md)|Recherche dans divers fournisseurs disponibles \(sources de données\) afin d'en trouver un avec le nom spécifié.|  
|[GetMoniker](../../data/oledb/cenumerator-getmoniker.md)|Récupère l'interface d' `IMoniker` pour l'enregistrement actif.|  
|[Ouvrez .](../../data/oledb/cenumerator-open.md)|Ouvre l'énumérateur.|  
  
## Notes  
 Vous pouvez récupérer indirectement les données d' **ISourcesRowset** à partir de cette classe.  
  
## Configuration requise  
 **En\-tête:**atldbcli.h  
  
## Voir aussi  
 [DBViewer](../../top/visual-cpp-samples.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)