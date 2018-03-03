---
title: _FREEENTRY, _USEDENTRY | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- USEDENTRY
- _USEDENTRY
- _FREEENTRY
- FREEENTRY
dev_langs:
- C++
helpviewer_keywords:
- _USEDENTRY constant
- _FREEENTRY constant
- FREEENTRY constant
- USEDENTRY constant
ms.assetid: 26f658e6-6846-4a4e-9984-262cfe392770
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82f33c60ae5be642e29e588cdab27508b207d62a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="freeentry-usedentry"></a>_FREEENTRY, _USEDENTRY
## <a name="syntax"></a>Syntaxe  
  
```  
#include <malloc.h>  
```  
  
## <a name="remarks"></a>Notes  
 Ces constantes représentent les valeurs affectées par les routines `_heapwalk` à l’élément **_useflag** de la structure **_HEAPINFO**. Ils indiquent l’état de l’entrée de tas.  
  
## <a name="see-also"></a>Voir aussi  
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)