---
title: __max | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- __max
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- max
- __max
dev_langs:
- C++
helpviewer_keywords:
- max macro
- maximum macro
- __max macro
ms.assetid: 05c936f6-0e22-45d6-a58d-4bc102e9dae2
caps.latest.revision: 12
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: a73c66cc0d1e49c514f8f451aa01a0c8ca7a9277
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="max"></a>__max
Retourne la plus grande de deux valeurs.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
type __max(  
   type a,  
   type b   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `type`  
 Tout type de données numérique.  
  
 `a, b`  
 Valeurs de tout type numérique à comparer.  
  
## <a name="return-value"></a>Valeur de retour  
 `__max` retourne le plus grand de ses arguments.  
  
## <a name="remarks"></a>Notes  
 La macro `__max` compare deux valeurs et retourne la valeur la plus grande. Les arguments peuvent être de n’importe quel type de données numérique, signé ou non signé. Les deux arguments et la valeur de retour doivent être du même type de données.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`__max`|\<stdlib.h>|  
  
## <a name="example"></a>Exemple  
 Pour plus d’informations, consultez l’exemple pour [__min](../../c-runtime-library/reference/min.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [__min](../../c-runtime-library/reference/min.md)
