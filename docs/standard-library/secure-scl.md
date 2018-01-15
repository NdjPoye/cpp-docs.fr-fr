---
title: _SECURE_SCL | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: _SECURE_SCL
dev_langs: C++
helpviewer_keywords: _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6f32a4ebfd9aec0cfbdcc03098f6aa0a23b8ecff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="securescl"></a>_SECURE_SCL
  
Remplacée par [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), cette macro définit si les [itérateurs vérifiés](../standard-library/checked-iterators.md) sont activés. Par défaut, les itérateurs vérifiés sont activés dans les versions de débogage et désactivés dans les versions commerciales.  
  
> [!IMPORTANT]
> L’utilisation directe de la macro `_SECURE_SCL` est dépréciée. Utilisez plutôt `_ITERATOR_DEBUG_LEVEL` pour contrôler les paramètres des itérateurs vérifiés. Pour plus d’informations, consultez [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).  
  
## <a name="remarks"></a>Notes  
  
Quand les itérateurs vérifiés sont activés, toute utilisation non sécurisée d’un itérateur provoque une erreur d’exécution et le programme se termine. Pour activer les itérateurs vérifiés, définissez `_ITERATOR_DEBUG_LEVEL` sur 1 ou 2. Cela équivaut à un paramètre `_SECURE_SCL` de 1, ou activé :  
  
```  
#define _ITERATOR_DEBUG_LEVEL 1  
```  
  
Pour désactiver les itérateurs vérifiés, définissez `_ITERATOR_DEBUG_LEVEL` sur 0. Cela équivaut à un paramètre `_SECURE_SCL` de 0, ou désactivé :  
  
```  
#define _ITERATOR_DEBUG_LEVEL 0  
```  
  
Pour plus d’informations sur la façon de désactiver les avertissements concernant les itérateurs vérifiés, consultez [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## <a name="see-also"></a>Voir aussi  
[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)   
[Itérateurs vérifiés](../standard-library/checked-iterators.md)   
[Prise en charge des itérateurs de débogage](../standard-library/debug-iterator-support.md)   
[Bibliothèques sécurisées : bibliothèque standard C++](../standard-library/safe-libraries-cpp-standard-library.md)

