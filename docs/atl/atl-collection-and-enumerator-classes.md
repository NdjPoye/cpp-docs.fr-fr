---
title: "Classes des énumérateurs et des collections ATL | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- enumerators, ATL classes
- collection classes, ATL
ms.assetid: 6818db73-7094-48d8-a0ca-18147beec362
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8b172c0d3a6f453ec0d5f7b5bb3584ebf2f5140e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-collection-and-enumerator-classes"></a>Classes des énumérateurs et des collections ATL
ATL fournit les classes suivantes pour vous aider à implémenter des collections et énumérateurs.  
  
|Classe|Description|  
|-----------|-----------------|  
|[ICollectionOnSTLImpl](../atl/reference/icollectiononstlimpl-class.md)|Implémentation d’interface de collection|  
|[IEnumOnSTLImpl](../atl/reference/ienumonstlimpl-class.md)|Implémentation d’interface énumérateur (suppose que les données stockées dans un conteneur compatible de bibliothèque C++ Standard)|  
|[CComEnumImpl](../atl/reference/ccomenumimpl-class.md)|Implémentation d’interface énumérateur (Cela suppose que les données stockées dans un tableau)|  
|[CComEnumOnSTL](../atl/reference/ccomenumonstl-class.md)|Implémentation d’objet énumérateur (utilise `IEnumOnSTLImpl`)|  
|[CComEnum](../atl/reference/ccomenum-class.md)|Implémentation d’objet énumérateur (utilise `CComEnumImpl`)|  
|[_Copy](../atl/atl-copy-policy-classes.md)|Classe de stratégie de copie|  
|[_CopyInterface](../atl/atl-copy-policy-classes.md)|Classe de stratégie de copie|  
|[CAdapt](../atl/reference/cadapt-class.md)|Classe d’adaptateur (masque **opérateur &** autorisant `CComPtr`, `CComQIPtr`, et `CComBSTR` à stocker dans les conteneurs de bibliothèque C++ Standard)|  
  
## <a name="see-also"></a>Voir aussi  
 [Collections et énumérateurs](../atl/atl-collections-and-enumerators.md)

