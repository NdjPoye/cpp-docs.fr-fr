---
title: _heapadd | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _heapadd
apilocation:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
apitype: DLLExport
f1_keywords:
- heapadd
- _heapadd
dev_langs:
- C++
helpviewer_keywords:
- _heapadd function
- memory, adding to heaps
- heaps, adding memory
- heapadd function
ms.assetid: 4d691fe2-2763-49f4-afb1-62738b7cd3ff
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9c046f9e26848edbbc609b9f3c729a0654fe3718
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="heapadd"></a>_heapadd
Ajoute de la mémoire au tas.  
  
> [!IMPORTANT]
>  Cette fonction est obsolète. Depuis Visual Studio 2015, elle n’est pas disponible dans la bibliothèque CRT.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _heapadd(   
   void *memblock,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `memblock`  
 Pointeur vers la mémoire du tas.  
  
 `size`  
 Taille de la mémoire à ajouter, en octets.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, `_heapadd` retourne 0 ; sinon, la fonction retourne -1 et définit `errno` sur `ENOSYS`.  
  
 Pour plus d’informations sur ce code de retour et sur les autres codes, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Depuis Visual C++ version 4.0, la structure sous-jacente du tas a été déplacée dans les bibliothèques Runtime C pour prendre en charge les nouvelles fonctionnalités de débogage. Par conséquent, `_heapadd` n’est plus pris en charge sur aucune des plateformes basées sur l’API Win32.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_heapadd`|\<malloc.h>|\<errno.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../c-runtime-library/memory-allocation.md)   
 [free](../c-runtime-library/reference/free.md)   
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapmin](../c-runtime-library/reference/heapmin.md)   
 [_heapset](../c-runtime-library/heapset.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [malloc](../c-runtime-library/reference/malloc.md)   
 [realloc](../c-runtime-library/reference/realloc.md)