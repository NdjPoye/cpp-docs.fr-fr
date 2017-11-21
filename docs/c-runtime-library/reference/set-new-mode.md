---
title: _set_new_mode | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _set_new_mode
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
- api-ms-win-crt-heap-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- set_new_mode
- _set_new_mode
dev_langs: C++
helpviewer_keywords:
- handler modes
- _set_new_mode function
- set_new_mode function
ms.assetid: 4d14039a-e54e-4689-8c70-74a4b9834768
caps.latest.revision: "14"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 31a738319507f13dc26346b237447b37ee60ce0c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="setnewmode"></a>_set_new_mode
Définit un mode de nouveau gestionnaire pour `malloc`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _set_new_mode(  
   int newhandlermode   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `newhandlermode`  
 Mode de nouveau gestionnaire pour `malloc` ; la valeur valide est 0 ou 1.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le mode de gestionnaire précédent pour `malloc`. La valeur de retour 1 indique qu’en cas d’échec d’allocation de mémoire, `malloc` appelait précédemment la routine de nouveau gestionnaire ; la valeur de retour 0 indique le contraire. Si le `newhandlermode` argument est différent de 0 ou 1, retourne -1.  
  
## <a name="remarks"></a>Remarques  
 La fonction C++ `_set_new_mode` définit le mode de nouveau gestionnaire pour [malloc](../../c-runtime-library/reference/malloc.md). Le mode de nouveau gestionnaire indique si, en cas d’échec, `malloc` doit appeler la routine de nouveau gestionnaire, telle qu’elle est définie par [_set_new_handler](../../c-runtime-library/reference/set-new-handler.md). Par défaut, `malloc` n’appelle pas la routine de nouveau gestionnaire en cas d’échec d’allocation de mémoire. Vous pouvez remplacer ce comportement par défaut de sorte que, quand `malloc` ne parvient pas à allouer de la mémoire, `malloc` appelle la routine de nouveau gestionnaire de la même façon que l’opérateur `new` quand il échoue pour la même raison. Pour plus d’informations, voir les opérateurs [new](../../cpp/new-operator-cpp.md) et [delete](../../cpp/delete-operator-cpp.md) dans la *Référence du langage C++*. Pour substituer la valeur par défaut, appelez :  
  
```  
_set_new_mode(1)  
```  
  
 au début de votre programme, ou créez un lien avec Newmode.obj (consultez [Options de lien](../../c-runtime-library/link-options.md)).  
  
 Cette fonction valide son paramètre. Si `newhandlermode` a une valeur différente de 0 ou 1, la fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, **_**`set_new_mode` retourne -1 et affecte à `errno` la valeur `EINVAL`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_set_new_mode`|\<new.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [calloc](../../c-runtime-library/reference/calloc.md)   
 [free](../../c-runtime-library/reference/free.md)   
 [realloc](../../c-runtime-library/reference/realloc.md)   
 [_query_new_handler](../../c-runtime-library/reference/query-new-handler.md)   
 [_query_new_mode](../../c-runtime-library/reference/query-new-mode.md)