---
title: "ATL Collection and Enumerator Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes de collection, ATL"
  - "énumérateurs, ATL classes"
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL Collection and Enumerator Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL fournit les classes suivantes pour vous aider des collections et des énumérateurs d'implémenter.  
  
|Classe|Description|  
|------------|-----------------|  
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|Implémentation d'interface de la collection|  
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|Implémentation d'interface d'énumérateur \(supposé des données stockées dans un conteneur STL\- compatible\)|  
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|Implémentation d'interface d'énumérateur \(supposé des données stockées dans un tableau\)|  
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|Implémentation d'objet énumérateur \(utilise `IEnumOnSTLImpl`\)|  
|[CComEnum](../atl/reference/ccomenum-class.md)|Implémentation d'objet énumérateur \(utilise `CComEnumImpl`\)|  
|[\_Copy](../atl/atl-copy-policy-classes.md)|Classe de stratégie de copie|  
|[\_CopyInterface](../atl/atl-copy-policy-classes.md)|Classe de stratégie de copie|  
|[CAdapt](../atl/reference/cadapt-class.md)|Classe d'adaptateur \(masque **operator &** permettant `CComPtr`, `CComQIPtr`, et `CComBSTR` à stocker dans des conteneurs STL\)|  
  
## Voir aussi  
 [Collections et énumérateurs](../atl/atl-collections-and-enumerators.md)