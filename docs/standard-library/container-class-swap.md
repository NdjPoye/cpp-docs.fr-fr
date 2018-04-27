---
title: Conteneur Class::swap | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3c6691b8ee8471ebf0e8edc8f1513d0229193a4a
ms.sourcegitcommit: dd1a509526fa8bb18e97ab7bc7b91cbdb3ec7059
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2018
---
# <a name="container-classswap"></a>Conteneur Class::swap

> [!NOTE]
> Cette rubrique fait partie de la documentation Visual C++ comme exemple non fonctionnel de conteneurs utilisés dans la bibliothèque standard C++. Pour plus d’informations, consultez [Conteneurs de la bibliothèque standard C++](../standard-library/stl-containers.md).

Échange les séquences contrôlées entre **\*this** et son argument.

## <a name="syntax"></a>Syntaxe

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>Notes

Si **\*this.get\_allocator ==** _right_**.get_allocator**, l’échange est effectué en temps constant. Sinon, elle effectue un nombre d’affectations d’éléments et d’appels de constructeurs proportionnel au nombre d’éléments dans les deux séquences contrôlées.

## <a name="see-also"></a>Voir aussi

[Sample Container, classe](../standard-library/sample-container-class.md)<br/>
