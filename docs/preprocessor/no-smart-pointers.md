---
title: no_smart_pointers | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- no_search_pointers
dev_langs:
- C++
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8d1e06265771a163375d1095b4c481aa6d7d250f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="nosmartpointers"></a>no_smart_pointers
**Spécifique à C++**  
  
 Supprime la création des pointeurs intelligents pour toutes les interfaces dans la bibliothèque de types.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
no_smart_pointers  
```  
  
## <a name="remarks"></a>Notes  
 Par défaut, lorsque vous utilisez `#import`, vous obtenez une déclaration de pointeur intelligent pour toutes les interfaces dans la bibliothèque de types. Ces pointeurs intelligents sont de type [_com_ptr_t, classe](../cpp/com-ptr-t-class.md).  
  
 **FIN spécifique à C++**  
  
## <a name="see-also"></a>Voir aussi  
 [attributs #import](../preprocessor/hash-import-attributes-cpp.md)   
 [#import (directive)](../preprocessor/hash-import-directive-cpp.md)