---
title: Conteneur Class::swap | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: f293f074f2b8e2334dc70fbebba8e6f4c17efecc
ms.openlocfilehash: 33ec601dcc8d32b85c2c38ed3fc5a07842a056fc
ms.lasthandoff: 02/24/2017

---
# <a name="container-classswap"></a>Conteneur Class::swap
> [!NOTE]
>  Cette rubrique fait partie de la documentation Visual C++ comme exemple non fonctionnel de conteneurs utilisés dans la bibliothèque C++ Standard. Pour plus d’informations, consultez [Conteneurs disponibles dans la bibliothèque C++ Standard](../standard-library/stl-containers.md).  
  
Échange les séquences contrôlées entre **\*this** et son argument.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void swap(Container& right);
```  
  
## <a name="remarks"></a>Notes  
Si **\*this.get\_allocator ==** _right_**.get_allocator**, l’échange est effectué en temps constant. Sinon, elle effectue un nombre d’affectations d’éléments et d’appels de constructeurs proportionnel au nombre d’éléments dans les deux séquences contrôlées.  
  
## <a name="see-also"></a>Voir aussi  
[Exemple de classe de conteneur](../standard-library/sample-container-class.md)

