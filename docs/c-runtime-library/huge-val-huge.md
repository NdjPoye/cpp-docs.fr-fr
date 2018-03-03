---
title: HUGE_VAL, _HUGE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _HUGE
apilocation:
- msvcrt.dll
apitype: DLLExport
f1_keywords:
- _HUGE
- HUGE_VAL
dev_langs:
- C++
helpviewer_keywords:
- _HUGE constant
- HUGE_VAL constant
- double value
ms.assetid: 3f044b45-02cd-46b2-b1de-87fd0441dd6a
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27fbb0ae4f8bbe658c37c0e979ea97a4dcec2fb3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="hugeval-huge"></a>HUGE_VAL, _HUGE
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>Notes  
 `HUGE_VAL` est la plus grande valeur double représentable. Cette valeur est retournée par de nombreuses fonctions mathématiques d’exécution quand une erreur se produit. Pour certaines fonctions, -`HUGE_VAL` est retourné. `HUGE_VAL` est défini en tant que `_HUGE`, mais les fonctions mathématiques d’exécution retournent `HUGE_VAL`. Vous devez également utiliser `HUGE_VAL` dans votre code à des fins de cohérence.  
  
## <a name="see-also"></a>Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)