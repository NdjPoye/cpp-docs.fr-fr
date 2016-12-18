---
title: "_makepath, _wmakepath | Microsoft Docs"
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
  - "_makepath"
  - "_wmakepath"
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
  - "_wmakepath"
  - "_tmakepath"
  - "makepath"
  - "tmakepath"
  - "wmakepath"
  - "_makepath"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_makepath (fonction)"
  - "_tmakepath (fonction)"
  - "_wmakepath (fonction)"
  - "makepath (fonction)"
  - "chemins d'accès"
  - "tmakepath (fonction)"
  - "wmakepath (fonction)"
ms.assetid: 5930b197-a7b8-46eb-8519-2841a58cd026
caps.latest.revision: 22
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _makepath, _wmakepath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Create a path name from components.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md).  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `path`  
 Mémoire tampon de chemin complet.  
  
 `drive`  
 Contient une lettre \(A, B, et ainsi de suite\) correspondant au lecteur souhaité et un deux\-points de fin facultative.  `_makepath` insère automatiquement le signe deux\-points dans le chemin d'accès composite s'il manque.  Si `drive` est `NULL` ou pointe vers une chaîne vide, aucune lettre de lecteur ne s'affiche dans la chaîne composite `path`.  
  
 `dir`  
 Contient le chemin d'accès des répertoires, sans l'indicateur de lecteur ou le nom de fichier réel.  La barre oblique finale est facultative, et soit une barre oblique \(\/\) soit une barre oblique inverse \(\\\) soit les deux peuvent être utilisées dans un seul argument de `dir`.  Si aucune barre oblique \(\/\) ou \\\) n'est spécifiée, elle est insérée automatiquement.  Si `dir` est `NULL` ou pointe vers une chaîne vide, aucun chemin d'accès au répertoire n'est inséré dans la chaîne composite `path`.  
  
 `fname`  
 Contient le nom de fichier de base sans les extensions du nom de fichier.  Si `fname` est `NULL` ou pointe vers une chaîne vide, aucun nom de fichier n'est inséré dans la chaîne composite `path`.  
  
 `ext`  
 Contient l'extension de nom de fichier réel, avec ou sans point initial \(.\).  `_makepath` insère automatiquement le point s'il n'apparaît pas dans `ext`.  Si `ext` est `NULL` ou pointe vers une chaîne vide, aucune extension n'est insérée dans la chaîne composite `path`.  
  
## Notes  
 La fonction `_makepath` crée une chaîne de chemin d'accès composite depuis chaque composant, contenant le résultat dans `path`.  `path` peut inclure une lettre de lecteur, un chemin d'accès au répertoire, un nom de fichier, et une extension de nom de fichier.  `_wmakepath` est une version à caractères larges de `_makepath` ; les arguments de `_wmakepath` sont des chaînes à caractères larges.  `_wmakepath` et `_makepath` se comportent sinon de manière identique.  
  
 **Note de Securité** Utilisez une chaîne terminée par le caractère NULL.  Pour éviter un dépassement de mémoire tampon, la chaîne terminée par le caractère NULL ne doit pas dépasser la taille de la mémoire tampon `path`.  `_makepath` ne garantit pas que la longueur de la chaîne de chemin d'accès composite ne dépasse pas `_MAX_PATH`.  Pour plus d'informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tmakepath`|`_makepath`|`_makepath`|`_wmakepath`|  
  
 L'argument `path` doit indiquer une mémoire tampon vide suffisante pour contenir le chemin complet.  Le `path` composite ne doit pas être supérieur à la constante `_MAX_PATH`, définie dans Stdlib.h.  
  
 Si le chemin d'accès a la valeur `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  En outre, `errno` est affecté à la valeur `EINVAL`.  Vous pouvez insérer des valeurs `NULL` pour tous les autres paramètres.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_makepath`|\<stdlib.h\>|  
|`_wmakepath`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
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
  
  **Chemin d'accès créé avec le \_makepath : c:\\sample\\crt\\makepath.c**  
**Chemin d'accès extrait avec le \_splitpath :**  
 **Lecteur : c:**  
 **Dir: \\sample\\crt\\**  
 **Nom du fichier : makepath**  
 **Ext: .c**   
## Équivalent .NET Framework  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)   
 [\_makepath\_s, \_wmakepath\_s](../../c-runtime-library/reference/makepath-s-wmakepath-s.md)