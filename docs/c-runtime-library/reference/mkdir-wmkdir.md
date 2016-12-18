---
title: "_mkdir, _wmkdir | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wmkdir"
  - "_mkdir"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_mkdir"
  - "tmkdir"
  - "_tmkdir"
  - "wmkdir"
  - "_wmkdir"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mkdir (fonction)"
  - "_tmkdir (fonction)"
  - "_wmkdir (fonction)"
  - "répertoires (C++), créer"
  - "dossiers (C++), créer"
  - "mkdir (fonction)"
  - "tmkdir (fonction)"
  - "wmkdir (fonction)"
ms.assetid: 7f22d01d-63a5-4712-a6e7-d34878b2d840
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _mkdir, _wmkdir
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un nouveau répertoire.  
  
## Syntaxe  
  
```  
  
      int _mkdir(  
   const char *dirname   
);  
int _wmkdir(  
   const wchar_t *dirname   
);  
```  
  
#### Paramètres  
 `dirname`  
 Chemin d'accès d'un nouveau répertoire.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne la valeur 0 si le répertoire a été créé.  Sur une erreur, la fonction retourne – 1 et définit `errno` comme suit.  
  
 `EEXIST`  
 Le répertoire n'a pas été créé car `dirname` est le nom d'un fichier, d'un répertoire, ou d'une unité existant.  
  
 `ENOENT`  
 Chemin d'accès introuvable.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_mkdir` crée un nouveau répertoire avec le *dirname* spécifié.`_mkdir` peut uniquement créer un nouveau répertoire par appel, donc seul le dernier composant de `dirname` peut nommer un nouveau répertoire.  `_mkdir` ne traduit pas les séparateurs de chemin d'accès.  Dans Windows NT, la barre oblique inverse \(\\\) et la barre oblique \(\/\) sont des séparateurs valides de chemin d'accès dans les chaînes de caractères dans les routines de run\-time.  
  
 `_wmkdir` est une version à caractères larges de `_mkdir`; l'argument `dirname` vers `_wmkdir` est une chaîne à caractères larges.  `_wmkdir` et `_mkdir` se comportent sinon de manière identique.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tmkdir`|`_mkdir`|`_mkdir`|`_wmkdir`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_mkdir`|\<direct.h\>|  
|`_wmkdir`|\<direct.h\> or \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
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
  
## Résultat de l'exemple  
  
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
  
## Équivalent .NET Framework  
  
-   [System::IO::Directory::CreateDirectory](https://msdn.microsoft.com/en-us/library/system.io.directory.createdirectory.aspx)  
  
-   [System::IO::DirectoryInfo::CreateSubdirectory](https://msdn.microsoft.com/en-us/library/system.io.directoryinfo.createsubdirectory.aspx)  
  
## Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)