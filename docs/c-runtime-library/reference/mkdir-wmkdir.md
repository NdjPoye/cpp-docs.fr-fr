---
title: _mkdir, _wmkdir | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wmkdir
- _mkdir
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
- _mkdir
- tmkdir
- _tmkdir
- wmkdir
- _wmkdir
dev_langs: C++
helpviewer_keywords:
- _wmkdir function
- folders [C++], creating
- wmkdir function
- directories [C++], creating
- mkdir function
- tmkdir function
- _mkdir function
- _tmkdir function
ms.assetid: 7f22d01d-63a5-4712-a6e7-d34878b2d840
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8a94c21cb35237f08a4a8860b1a414c91d5e8801
ms.sourcegitcommit: 4df3cf1ae6ac1154a9dff9de0063377df43380a2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/19/2018
---
# <a name="mkdir-wmkdir"></a>_mkdir, _wmkdir
Crée un répertoire.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
int _mkdir(
   const char *dirname   
);  
int _wmkdir(  
   const wchar_t *dirname   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dirname`  
 Chemin du nouveau répertoire.  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces fonctions retourne la valeur 0 si le répertoire a été créé. Sur une erreur, la fonction retourne -1 et les jeux de `errno` comme suit.  
  
 `EEXIST`  
 Le répertoire n’a pas été créé, car `dirname` est le nom d’un fichier, répertoire ou périphérique existant.  
  
 `ENOENT`  
 Le chemin est introuvable.  
  
 Pour plus d’informations sur ces codes de retour et autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_mkdir` crée un répertoire avec la valeur *dirname* spécifiée. `_mkdir` ne pouvant créer qu’un seul répertoire par appel, seul le dernier composant de `dirname` peut nommer un nouveau répertoire. `_mkdir` ne traduit pas les délimiteurs de chemin. Dans Windows NT, la barre oblique inverse (\\) et la barre oblique (/) sont des délimiteurs de chemin valides dans les chaînes de caractères au sein des routines d’exécution.  
  
 `_wmkdir` est une version à caractères larges de `_mkdir` ; l'argument `dirname` de `_wmkdir` est une chaîne à caractères larges. Sinon, `_wmkdir` et `_mkdir` se comportent de la même façon.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmkdir`|`_mkdir`|`_mkdir`|`_wmkdir`|  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_mkdir`|\<direct.h>|  
|`_wmkdir`|\<direct.h> ou \<wchar.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_makedir.c  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   if( _mkdir( "\\testtmp" ) == 0 )  
   {  
      printf( "Directory '\\testtmp' was successfully created\n" );  
      system( "dir \\testtmp" );  
      if( _rmdir( "\\testtmp" ) == 0 )  
        printf( "Directory '\\testtmp' was successfully removed\n"  );  
      else  
         printf( "Problem removing directory '\\testtmp'\n" );  
   }  
   else  
      printf( "Problem creating directory '\\testtmp'\n" );  
}  
```  
  
## <a name="sample-output"></a>Résultat de l'exemple  
  
```  
Directory '\testtmp' was successfully created  
 Volume in drive C has no label.  
 Volume Serial Number is E078-087A  
  
 Directory of C:\testtmp  
  
02/12/2002  09:56a      <DIR>          .  
02/12/2002  09:56a      <DIR>          ..  
               0 File(s)              0 bytes  
               2 Dir(s)  15,498,690,560 bytes free  
Directory '\testtmp' was successfully removed  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [_chdir, _wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [_rmdir, _wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)