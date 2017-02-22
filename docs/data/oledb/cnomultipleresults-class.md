---
title: "CNoMultipleResults, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CNoMultipleResults"
  - "ATL.CNoMultipleResults"
  - "ATL::CNoMultipleResults"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CNoMultipleResults (classe)"
ms.assetid: 343e77c4-b319-476e-b592-901ab9b2f34e
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CNoMultipleResults, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisé comme un modèle d'argument \(*TMultiple*\) à [CCommand](../../data/oledb/ccommand-class.md) pour créer une commande optimisée qui gère un seul jeu de résultats.  
  
## Syntaxe  
  
```  
class CNoMultipleResults  
```  
  
## Notes  
 Si vous souhaitez une commande gérant plusieurs jeux de résultats, utilisez [CMultipleResults](../../data/oledb/cmultipleresults-class.md) à la place.  
  
## Configuration requise  
 **En\-tête :** : atldbcli.h  
  
## Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)