---
title: '&lt;forward_list&gt;, fonctions | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
caps.latest.revision: 11
manager: ghogen
ms.openlocfilehash: 7b990c760a94589967d5e2020082cb1f48250dac
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="ltforwardlistgt-functions"></a>&lt;forward_list&gt;, fonctions

||
|-|
|[swap](#swap)|

## <a name="swap"></a>  swap

Échange les éléments de deux forward_list.

```cpp
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

[<forward_list>](../standard-library/forward-list.md)<br/>
