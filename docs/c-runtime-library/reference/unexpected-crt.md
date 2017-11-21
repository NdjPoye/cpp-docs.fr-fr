---
title: unexpected (CRT) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: unexpected
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
f1_keywords: unexpected
dev_langs: C++
helpviewer_keywords: unexpected function
ms.assetid: 2f873763-15ad-4556-a924-dcf28f2b52b4
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 39cc7164a22b95f2c269c7bb1bd558374f56fa3c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="unexpected-crt"></a>unexpected (CRT)
Appelle `terminate` ou la fonction que vous spécifiez à l’aide de `set_unexpected`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void unexpected( void );  
```  
  
## <a name="remarks"></a>Notes  
 La routine `unexpected` n’est pas utilisée avec l’implémentation actuelle de la gestion des exceptions C++. `unexpected` appelle `terminate` par défaut. Vous pouvez modifier ce comportement par défaut en écrivant une fonction d’arrêt personnalisée et en appelant `set_unexpected` avec le nom de votre fonction comme argument. `unexpected` appelle la dernière fonction transmise comme argument à `set_unexpected`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`unexpected`|\<eh.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de gestion des exceptions](../../c-runtime-library/exception-handling-routines.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [_set_se_translator](../../c-runtime-library/reference/set-se-translator.md)   
 [set_terminate](../../c-runtime-library/reference/set-terminate-crt.md)   
 [set_unexpected](../../c-runtime-library/reference/set-unexpected-crt.md)   
 [terminate](../../c-runtime-library/reference/terminate-crt.md)