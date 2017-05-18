---
title: _close | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _close
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _close
dev_langs:
- C++
helpviewer_keywords:
- _close function
- close function
- files [C++], closing
ms.assetid: 4708a329-8acf-4cd9-b7b0-a952e1897247
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
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 9dab323afc6c70e81592119e0cec2775c239d87f
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="close"></a>_close
Ferme un fichier.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _close(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `fd`  
 Descripteur de fichier qui fait référence au fichier ouvert.  
  
## <a name="return-value"></a>Valeur de retour  
 `_close` retourne 0 si le fichier a été fermé correctement. Une valeur de retour de -1 indique une erreur.  
  
## <a name="remarks"></a>Remarques  
 La fonction `_close` ferme le fichier associé à `fd`.  
  
 Le descripteur de fichier et le handle de fichier du système d’exploitation sous-jacent sont fermés. Ainsi, il n’est pas nécessaire d’appeler `CloseHandle` si le fichier a été initialement ouvert à l’aide de la fonction Win32 `CreateFile` et converti en descripteur de fichier à l’aide de `_open_osfhandle`.  
  
 Cette fonction valide ses paramètres. Si `fd` est un descripteur de fichier incorrect, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, la fonction retourne -1 et `errno` est défini sur `EBADF`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_close`|\<io.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [_open](../../c-runtime-library/reference/open-wopen.md).  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de bas niveau](../../c-runtime-library/low-level-i-o.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_unlink, _wunlink](../../c-runtime-library/reference/unlink-wunlink.md)
