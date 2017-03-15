---
title: "BEGIN_ACCESSOR_MAP | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BEGIN_ACCESSOR_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_ACCESSOR_MAP (macro)"
ms.assetid: e6d6e3a4-62fa-4e49-8c53-caf8c9d20091
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# BEGIN_ACCESSOR_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marque le début des entrées de mappage d’accesseur.  
  
## Syntaxe  
  
```  
  
BEGIN_ACCESSOR_MAP(  
x  
,   
num  
 )  
  
```  
  
#### Paramètres  
 *x*  
 \[in\] Nom de la classe d’enregistrement utilisateur.  
  
 *num*  
 \[in\] Nombre d’accesseurs contenus dans ce mappage d’accesseur.  
  
## Notes  
 Dans le cas où plusieurs accesseurs figurent dans un ensemble de lignes, vous devez spécifier `BEGIN_ACCESSOR_MAP` au début et utiliser la macro `BEGIN_ACCESSOR` pour chaque accesseur individuel. La macro `BEGIN_ACCESSOR` se termine avec la macro `END_ACCESSOR`. Le mappage d’accesseur se termine avec la macro `END_ACCESSOR_MAP`.  
  
 Si l’enregistrement utilisateur ne comprend qu’un seul accesseur, utilisez la macro [BEGIN\_COLUMN\_MAP](../../data/oledb/begin-column-map.md).  
  
## Exemple  
 [!CODE [NVC_OLEDB_Consumer#15](../CodeSnippet/VS_Snippets_Cpp/NVC_OLEDB_Consumer#15)]  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN\_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END\_ACCESSOR](../../data/oledb/end-accessor.md)   
 [END\_ACCESSOR\_MAP](../../data/oledb/end-accessor-map.md)