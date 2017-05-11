---
title: _getdcwd, _wgetdcwd | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _getdcwd
- _wgetdcwd
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
- wgetdcwd
- getdcwd
- _getdcwd
- tgetdcwd
- _wgetdcwd
- _tgetdcwd
dev_langs:
- C++
helpviewer_keywords:
- wgetdcwd function
- working directory
- getdcwd function
- _getdcwd function
- _wgetdcwd function
- current working directory
- directories [C++], current working
ms.assetid: 184152f5-c7b0-495b-918d-f9a6adc178bd
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.openlocfilehash: 03791f920619b98beec3c1bbbd33b45b550eaf7a
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="getdcwd-wgetdcwd"></a>_getdcwd, _wgetdcwd
Obtient le chemin d'accès complet du répertoire de travail actuel sur le lecteur spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *_getdcwd(   
   int drive,  
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetdcwd(   
   int drive,  
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `drive`  
 Entier non négatif qui spécifie le lecteur (0 = lecteur par défaut, 1 = A, 2 = B, etc.).  
  
 Si le lecteur spécifié n’est pas disponible, ou le type de lecteur (par exemple, amovible, fixe, CD-ROM, disque virtuel ou lecteur réseau) ne peut pas être déterminé, le gestionnaire de paramètre non valide, décrit dans [Parameter Validation](../../c-runtime-library/parameter-validation.md), est appelé.  
  
 `buffer`  
 Emplacement de stockage pour le chemin d'accès, ou **NULL**.  
  
 Si la valeur **NULL** est spécifiée, cette fonction alloue une mémoire tampon d'une taille d'au moins `maxlen` à l'aide de **malloc**, et la valeur de retour de `_getdcwd` est un pointeur vers la mémoire tampon allouée. La mémoire tampon peut être libérée en appelant `free` et en lui passant le pointeur.  
  
 `maxlen`  
 Entier positif différent de zéro qui spécifie la longueur maximale du chemin d'accès, en caractères : `char` pour `_getdcwd` et `wchar_t` pour `_wgetdcwd`.  
  
 Si la valeur `maxlen` n’est pas supérieure à zéro, le gestionnaire de paramètres non valides, décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md), est appelé.  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur vers une chaîne qui représente le chemin d'accès complet du répertoire de travail actuel sur le lecteur spécifié, ou `NULL`, qui indique une erreur.  
  
 Si le paramètre `buffer` est spécifié comme `NULL` et si la mémoire est insuffisante pour allouer `maxlen` caractères, une erreur se produit et `errno` a la valeur `ENOMEM`. Si la longueur du chemin d'accès, qui inclut le caractère null de fin, dépasse `maxlen`, une erreur se produit et `errno` a la valeur `ERANGE`. Pour plus d’informations sur ces codes d’erreur, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_getdcwd` obtient le chemin d'accès complet du répertoire de travail actuel sur le lecteur spécifié et l'enregistre dans `buffer`. Si le répertoire de travail actuel est la racine, la chaîne se termine par une barre oblique inverse (\\). Si le répertoire de travail actuel est un répertoire différent de la racine, la chaîne se termine par le nom du répertoire, et non par une barre oblique inverse.  
  
 `_wgetdcwd` est une version à caractère larges de `_getdcwd`, et son paramètre `buffer` et sa valeur de retour sont des chaînes à caractères larges. Sinon, `_wgetdcwd` et `_getdcwd` se comportent de la même façon.  
  
 Cette fonction est thread-safe même si elle dépend de **GetFullPathName**, qui n'est pas elle-même thread-safe. Toutefois, vous pouvez enfreindre la sécurité des threads si votre application multithread appelle cette fonction et **GetFullPathName**. Pour plus d’informations, accédez à [MSDN Library](http://go.microsoft.com/fwlink/?LinkID=150542) , puis recherchez **GetFullPathName**.  
  
 La version de cette fonction avec le suffixe `_nolock` se comporte comme cette fonction sauf qu'elle n'est ni thread-safe ni protégée des interférences avec d'autres threads. Pour plus d'informations, consultez [_getdcwd_nolock, _wgetdcwd_nolock](../../c-runtime-library/reference/getdcwd-nolock-wgetdcwd-nolock.md).  
  
 Lorsque les paramètres `_DEBUG` et `_CRTDBG_MAP_ALLOC` sont définis, les appels à `_getdcwd` et `_wgetdcwd` sont remplacés par des appels à `_getdcwd_dbg` et `_wgetdcwd_dbg` afin que vous puissiez déboguer les allocations de mémoire. Pour plus d’informations, consultez[_getdcwd_dbg, _wgetdcwd_dbg](../../c-runtime-library/reference/getdcwd-dbg-wgetdcwd-dbg.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetdcwd`|`_getdcwd`|`_getdcwd`|`_wgetdcwd`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_getdcwd`|\<direct.h>|  
|`_wgetdcwd`|\<direct.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple dans [_getdrive](../../c-runtime-library/reference/getdrive.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdrive](../../c-runtime-library/reference/getdrive.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)
