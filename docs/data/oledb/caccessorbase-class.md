---
title: "CAccessorBase, classe | Microsoft Docs"
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
  - "CAccessorBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAccessorBase (classe)"
ms.assetid: 389b65be-11ca-4ae0-9290-60c621c4982b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CAccessorBase, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Tous les accesseurs dans les modèles OLE DB dérivent de cette classe.  `CAccessorBase` permet à un ensemble de lignes de gérer plusieurs accesseurs.  Il fournit également une liaison des paramètres et des colonnes de sortie.  
  
## Syntaxe  
  
```  
// Replace with syntax  
```  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[Fermer](../../data/oledb/caccessorbase-close.md)|Ferme des accesseurs.|  
|[GetHAccessor](../../data/oledb/caccessorbase-gethaccessor.md)|Récupère le handle d'accesseur.|  
|[GetNumAccessors](../../data/oledb/caccessorbase-getnumaccessors.md)|Récupère le nombre d'accesseurs créés par la classe.|  
|[IsAutoAccessor](../../data/oledb/caccessorbase-isautoaccessor.md)|Teste si l'accesseur spécifié est un auto\-accesseur.|  
|[ReleaseAccessors](../../data/oledb/caccessorbase-releaseaccessors.md)|Libère les accesseurs.|  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)