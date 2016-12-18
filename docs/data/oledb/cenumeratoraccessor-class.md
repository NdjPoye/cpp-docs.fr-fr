---
title: "CEnumeratorAccessor, classe | Microsoft Docs"
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
  - "ATL::CEnumeratorAccessor"
  - "CEnumeratorAccessor"
  - "ATL.CEnumeratorAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CEnumeratorAccessor (classe)"
ms.assetid: 21e8e7ea-3511-4afe-b33f-d520f4ff82bb
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CEnumeratorAccessor, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé par [CEnumerator](../../data/oledb/cenumerator-class.md) pour accéder aux données à partir de l'énumérateur d'ensemble de lignes.  
  
## Syntaxe  
  
```  
class CEnumeratorAccessor  
```  
  
## Membres  
  
### Membres de données  
  
|||  
|-|-|  
|[m\_bIsParent](../../data/oledb/cenumeratoraccessor-m-bisparent.md)|Une variable qui indique si l'énumérateur est un énumérateur parent, si la ligne est un énumérateur.|  
|[m\_nType](../../data/oledb/cenumeratoraccessor-m-ntype.md)|Une variable qui indique si la ligne décrit une source de données ou un énumérateur.|  
|[m\_szDescription](../../data/oledb/cenumeratoraccessor-m-szdescription.md)|La description de la source de données ou du recenseur.|  
|[m\_szName](../../data/oledb/cenumeratoraccessor-m-szname.md)|Le nom de la source de données ou du recenseur.|  
|[m\_szParseName](../../data/oledb/cenumeratoraccessor-m-szparsename.md)|Chaîne à transmettre à [IParseDisplayName](http://msdn.microsoft.com/library/windows/desktop/ms680604) pour obtenir un surnom pour la source de données ou l'énumérateur.|  
  
## Notes  
 Cet ensemble de lignes comprend les sources de données et les énumérateurs visibles pour l'énumérateur actuel.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)