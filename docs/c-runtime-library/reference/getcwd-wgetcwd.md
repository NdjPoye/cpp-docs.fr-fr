---
title: _getcwd, _wgetcwd | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wgetcwd
- _getcwd
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
- api-ms-win-crt-environment-l1-1-0.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _getcwd
- wgetcwd
- _wgetcwd
- tgetcwd
- _tgetcwd
dev_langs:
- C++
helpviewer_keywords:
- getcwd function
- working directory
- _wgetcwd function
- _getcwd function
- current working directory
- wgetcwd function
- directories [C++], current working
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 91e660f548fdb8814e521f9c63c58e1b965949d4
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="getcwd-wgetcwd"></a>_getcwd, _wgetcwd
Obtient le répertoire de travail actuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *_getcwd(   
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetcwd(   
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `buffer`  
 Emplacement de stockage pour le chemin.  
  
 `maxlen`  
 Longueur maximale du chemin en caractères : `char` pour `_getcwd` et `wchar_t` pour `_wgetcwd`.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers `buffer`. Une valeur de retour `NULL` indique une erreur et `errno` prend la valeur `ENOMEM`, ce qui indique que la mémoire est insuffisante pour allouer `maxlen` octets (quand un argument `NULL` est donné comme `buffer`), ou la valeur `ERANGE`, ce qui indique que le chemin d’accès fait plus de `maxlen` caractères. Si `maxlen` est inférieur ou égal à zéro, cette fonction appelle un gestionnaire de paramètre non valide, comme décrit dans [Parameter Validation](../../c-runtime-library/parameter-validation.md).  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_getcwd` obtient le chemin complet du répertoire de travail actuel pour le lecteur spécifié et le stocke dans `buffer`. L’argument entier `maxlen` spécifie la longueur maximale du chemin. Une erreur se produit si la longueur du chemin (y compris le caractère null de fin) dépasse `maxlen`. La fonction `buffer` peut être `NULL`; une mémoire tampon d’une taille d’au moins `maxlen` (plus seulement si nécessaire) est allouée automatiquement, en utilisant `malloc`, pour stocker le chemin. Cette mémoire tampon ultérieurement peut être libérée en appelant `free` et en lui passant la valeur de retour `_getcwd` (un pointeur vers la mémoire tampon allouée).  
  
 `_getcwd` retourne une chaîne qui représente le chemin du répertoire de travail actuel. Si le répertoire de travail actuel est la racine, la chaîne se termine par une barre oblique inverse ( `\` ). Si le répertoire de travail actuel est un répertoire autre que la racine, la chaîne se termine par le nom du répertoire, et non pas par une barre oblique inverse.  
  
 `_wgetcwd` est une version à caractères larges de `_getcwd`; l’argument `buffer` et la valeur de retour de `_wgetcwd` sont des chaînes à caractères larges. Sinon,`_wgetcwd` et `_getcwd` se comportent de la même façon.  
  
 Quand `_DEBUG` et `_CRTDBG_MAP_ALLOC` sont définis, les appels à `_getcwd` et `_wgetcwd` sont remplacés par les appels à `_getcwd_dbg` et `_wgetcwd_dbg` pour permettre le débogage des allocations de mémoire. Pour plus d’informations, consultez [_getcwd_dbg, _wgetcwd_dbg](../../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tgetcwd`|`_getcwd`|`_getcwd`|`_wgetcwd`|  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_getcwd`|\<direct.h>|  
|`_wgetcwd`|\<direct.h> ou \<wchar.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_getcwd.c  
// This program places the name of the current directory in the   
// buffer array, then displays the name of the current directory   
// on the screen. Passing NULL as the buffer forces getcwd to allocate  
// memory for the path, which allows the code to support file paths  
// longer than _MAX_PATH, which are supported by NTFS.  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* buffer;  
  
   // Get the current working directory:   
   if( (buffer = _getcwd( NULL, 0 )) == NULL )  
      perror( "_getcwd error" );  
   else  
   {  
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );  
      free(buffer);  
   }  
}  
```  
  
```Output  
C:\Code  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_mkdir, _wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)