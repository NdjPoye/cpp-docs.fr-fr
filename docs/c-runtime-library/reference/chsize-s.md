---
title: _chsize_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _chsize_s
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
- chsize_s
- _chsize_s
dev_langs:
- C++
helpviewer_keywords:
- files [C++], changing size
- chsize_s function
- _chsize_s function
ms.assetid: d88d2e94-6e3b-42a5-8631-16ac4d82fa38
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 89ed8eb6511c9ba7126506e84e815616af78f84f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="chsizes"></a>_chsize_s
Modifie la taille d’un fichier. Il s’agit d’une version de [_chsize](../../c-runtime-library/reference/chsize.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _chsize_s(   
   int fd,  
   __int64 size   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `fd`  
 Descripteur de fichier qui fait référence à un fichier ouvert.  
  
 `size`  
 Nouvelle longueur, en octets, du fichier.  
  
## <a name="return-value"></a>Valeur de retour  
 `_chsize_s` retourne la valeur 0 si la taille du fichier a été correctement modifiée. Une valeur de retour différente de zéro indique une erreur : `EACCES` si le fichier spécifié est verrouillé contre tout accès, `EBADF` si le fichier spécifié est en lecture seule ou si le descripteur n’est pas valide, `ENOSPC` en l’absence d’espace disponible sur le périphérique ou `EINVAL` si la taille est inférieure à zéro. `errno` est défini sur la même valeur.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_chsize_s` étend ou tronque le fichier associé à `fd` à la longueur spécifiée par `size`. Le fichier doit être ouvert dans un mode qui permet l’écriture. Des caractères Null (« \0 ») sont ajoutés si le fichier est étendu. Si le fichier est tronqué, toutes les données depuis la fin du fichier raccourci jusqu’à la longueur d’origine du fichier sont perdues.  
  
 `_chsize_s`, qui accepte un entier 64 bits comme taille de fichier, peut gérer des tailles de fichier supérieures à 4 Go. `_chsize` est limité aux tailles de fichier 32 bits.  
  
 Cette fonction valide ses paramètres. Si `fd` n’est pas un descripteur de fichier valide ou que la taille est inférieure à zéro, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_chsize_s`|\<io.h>|\<errno.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)