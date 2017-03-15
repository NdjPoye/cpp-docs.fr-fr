---
title: _get_osfhandle | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_osfhandle
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
- get_osfhandle
- _get_osfhandle
dev_langs:
- C++
helpviewer_keywords:
- operating systems, getting file handles
- get_osfhandle function
- _get_osfhandle function
- file handles [C++], operating system
ms.assetid: 0bdd728a-4fd8-410b-8c9f-01a121135196
caps.latest.revision: 14
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 2e96f911e6784744eb539f6ce2b1961102d9869d
ms.lasthandoff: 02/24/2017

---
# <a name="getosfhandle"></a>_get_osfhandle
Récupère le handle de fichier du système d’exploitation qui est associé au descripteur de fichier spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
intptr_t _get_osfhandle(   
   int fd   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `fd`  
 Descripteur de fichier existant.  
  
## <a name="return-value"></a>Valeur de retour  
 Un handle de fichier du système d’exploitation si `fd` est valide. Sinon, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, cette fonction retourne `INVALID_HANDLE_VALUE` (–1) et définit `errno` sur `EBADF`, indiquant un handle de fichier non valide.  
  
## <a name="remarks"></a>Notes  
 Pour fermer un fichier ouvert avec `_get_osfhandle`, appelez `_close`. Le descripteur sous-jacent étant aussi fermé par un appel à `_close`, il n’est pas nécessaire d’appeler la fonction Win32 `CloseHandle` au niveau du descripteur d’origine.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_get_osfhandle`|\<io.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
