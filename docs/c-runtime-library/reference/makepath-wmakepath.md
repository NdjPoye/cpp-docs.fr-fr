---
title: _makepath, _wmakepath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _makepath
- _wmakepath
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _wmakepath
- _tmakepath
- makepath
- tmakepath
- wmakepath
- _makepath
dev_langs:
- C++
helpviewer_keywords:
- _makepath function
- wmakepath function
- makepath function
- _tmakepath function
- paths
- _wmakepath function
- tmakepath function
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: 22
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
ms.openlocfilehash: deb4333b36bf0b3eb2080d838ef3f23a052cf262
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="makepath-wmakepath"></a>_makepath, _wmakepath
Créent un nom de chemin à partir des composants. Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _makepath(  
   char *path,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
void _wmakepath(  
   wchar_t *path,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `path`  
 Mémoire tampon du chemin d’accès complet.  
  
 `drive`  
 Contient une lettre (A, B, etc.) correspondant au lecteur souhaité et un signe deux-points de fin facultatif. `_makepath` insère automatiquement le signe deux-points dans le chemin d'accès composite s'il est manquant. Si `drive` a la valeur `NULL` ou pointe vers une chaîne vide, aucune lettre de lecteur ne s'affiche dans la chaîne composite `path`.  
  
 `dir`  
 Contient le chemin d’accès des répertoires, sans l’indicateur de lecteur ou le nom de fichier réel. La barre oblique finale est facultative, et une barre oblique (/) ou une barre oblique inverse (\\) ou les deux peuvent être utilisées dans un seul argument `dir`. Si aucune barre oblique finale (/ ou \\) n’est spécifiée, elle est insérée automatiquement. Si `dir` a la valeur `NULL` ou pointe vers une chaîne vide, aucun chemin d'accès de répertoire n'est inséré dans la chaîne composite `path`.  
  
 `fname`  
 Contient le nom de fichier de base sans les extensions du nom de fichier. Si `fname` a la valeur `NULL` ou pointe vers une chaîne vide, aucun nom de fichier n'est inséré dans la chaîne composite `path`.  
  
 `ext`  
 Contient l’extension de nom de fichier réelle, avec ou sans point initial (.). `_makepath` insère automatiquement le point s'il n'apparaît pas dans `ext`. Si `ext` a la valeur `NULL` ou pointe vers une chaîne vide, aucune extension n'est insérée dans la chaîne composite `path`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_makepath` crée une chaîne de chemin d'accès composite à partir de chaque composant, en stockant le résultat dans `path`. `path` peut inclure une lettre de lecteur, un chemin de répertoire, un nom de fichier et une extension de nom de fichier. `_wmakepath` est une version à caractères larges de `_makepath` ; les arguments de `_wmakepath` sont des chaînes à caractères larges. Sinon, `_wmakepath` et `_makepath` se comportent de la même façon.  
  
 **Remarque relative à la sécurité** Utilisez une chaîne se terminant par un caractère Null. Pour éviter les dépassements de mémoire tampon, la chaîne ne doit pas dépasser la taille de la mémoire tampon `path`. `_makepath` ne garantit pas que la longueur de la chaîne de chemin composite ne dépasse pas `_MAX_PATH`. Pour plus d’informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmakepath`|`_makepath`|`_makepath`|`_wmakepath`|  
  
 L'argument `path` doit pointer vers une mémoire tampon vide suffisamment grande pour contenir le chemin d'accès complet. L'argument composite `path` ne doit pas être supérieur à la constante `_MAX_PATH`, définie dans Stdlib.h.  
  
 Si path a la valeur `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). En outre, `errno` prend la valeur `EINVAL`. Les valeurs `NULL` sont autorisées pour tous les autres paramètres.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_makepath`|\<stdlib.h>|  
|`_wmakepath`|\<stdlib.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_makepath.c  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
  
   _makepath( path_buffer, "c", "\\sample\\crt\\", "makepath", "c" ); // C4996  
   // Note: _makepath is deprecated; consider using _makepath_s instead  
   printf( "Path created with _makepath: %s\n\n", path_buffer );  
   _splitpath( path_buffer, drive, dir, fname, ext ); // C4996  
   // Note: _splitpath is deprecated; consider using _splitpath_s instead  
   printf( "Path extracted with _splitpath:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
```Output  
Path created with _makepath: c:\sample\crt\makepath.c  
  
Path extracted with _splitpath:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: makepath  
  Ext: .c  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [_fullpath, _wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [_makepath_s, _wmakepath_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)
