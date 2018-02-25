---
title: '&lt;forward_list&gt;, fonctions | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: ce66354d2377e52043830925c3f4f880de996663
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt;, fonctions
||  
|-|  
|[swap](#swap)|  
  
##  <a name="swap"></a>  swap  
 Échange les éléments de deux forward_list.  
  
```
void swap(
    forward_list <Type, Allocator>& left,
    forward_list <Type, Allocator>& right);
```  
  
### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`left`|Objet de type `forward_list`.|  
|`right`|Objet de type `forward_list`.|  
  
### <a name="remarks"></a>Notes  
 La fonction de modèle exécute `left.swap(right)`.  
  
## <a name="see-also"></a>Voir aussi  
 [<forward_list>](../standard-library/forward-list.md)



