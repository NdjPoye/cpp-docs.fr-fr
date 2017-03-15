---
title: "_makepath_s, _wmakepath_s | Microsoft Docs"
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
  - "_wmakepath_s"
  - "_makepath_s"
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
  - "_wmakepath_s"
  - "makepath_s"
  - "_makepath_s"
  - "wmakepath_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_makepath_s (fonction)"
  - "wmakepath_s (fonction)"
  - "chemins d'accès"
  - "_wmakepath_s (fonction)"
  - "makepath_s (fonction)"
ms.assetid: 4405e43c-3d63-4697-bb80-9b8dcd21d027
caps.latest.revision: 29
caps.handback.revision: 29
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _makepath_s, _wmakepath_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un nom de chemin d'accès à partir des composants.  Il s'agit de versions de [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t _makepath_s(  
   char *path,  
   size_t sizeInBytes,  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
);  
errno_t _wmakepath_s(  
   wchar_t *path,  
   size_t sizeInWords,  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
);  
template <size_t size>  
errno_t _makepath_s(  
   char (&path)[size],  
   const char *drive,  
   const char *dir,  
   const char *fname,  
   const char *ext   
); // C++ only  
template <size_t size>  
errno_t _wmakepath_s(  
   wchar_t (&path)[size],  
   const wchar_t *drive,  
   const wchar_t *dir,  
   const wchar_t *fname,  
   const wchar_t *ext   
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `path`  
 Mémoire tampon de chemin complet.  
  
 \[in\] `sizeInWords`  
 Taille de la mémoire tampon en lettres.  
  
 \[in\] `sizeInBytes`  
 Taille, en octets, de la mémoire tampon.  
  
 \[in\] `drive`  
 Contient une lettre \(A, B, et ainsi de suite\) correspondant au lecteur souhaité et un deux\-points de fin facultative.  `_makepath_s` insère automatiquement le signe deux\-points dans le chemin d'accès composite s'il manque.  Si `drive` est `NULL` ou pointe vers une chaîne vide, aucune lettre de lecteur ne s'affiche dans la chaîne composite`path`.  
  
 \[in\] `dir`  
 Contient le chemin d'accès des répertoires, sans l'indicateur de lecteur ou le nom de fichier réel.  La barre oblique finale est facultative, et soit une barre oblique \(\/\) soit une barre oblique inverse \(\\\) soit les deux peuvent être utilisées dans un seul argument de `dir`.  Si aucune barre oblique \(\/\) ou \\\) n'est spécifiée, elle est insérée automatiquement.  Si `dir` est `NULL` ou pointe vers une chaîne vide, aucun chemin d'accès au répertoire n'est inséré dans la chaîne composite `path`.  
  
 \[in\] `fname`  
 Contient le nom de fichier de base sans les extensions du nom de fichier.  Si `fname` est `NULL` ou pointe vers une chaîne vide, aucun nom de fichier n'est inséré dans la chaîne composite `path`.  
  
 \[in\] `ext`  
 Contient l'extension de nom de fichier réel, avec ou sans point initial \(.\).  `_makepath_s` insère automatiquement le point s'il n'apparaît pas dans `ext`.  Si `ext` est `NULL` ou pointe vers une chaîne vide, aucune extension n'est insérée dans la chaîne composite `path`.  
  
## Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur en cas de échec.  
  
### Conditions d'erreur  
  
|`path`|`sizeInWords` \/ `sizeInBytes`|Return|Contenu de `path`.|  
|------------|------------------------------------|------------|------------------------|  
|`NULL`|any|`EINVAL`|non modifié|  
|any|\<\= 0|`EINVAL`|non modifié|  
  
 Si une au moins des conditions d'erreur ci dessus se produit, elles appellent le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'execution est autorisée à continuer, `errno` est fixée la valeur`EINVAL` et les fonctions retournent`EINVAL`**.** `NULL` est autorisée pour les paramètres `drive`, `fname`, et `ext`.  Pour plus d'informations sur le comportement lorsque ces paramètres sont des pointeurs NULL ou des chaînes vides, consultez la section remarques.  
  
## Notes  
 La fonction `_makepath_s` crée une chaîne de chemin d'accès composite depuis chaque composant, contenant le résultat dans `path`.  `path` peut inclure une lettre de lecteur, un chemin d'accès au répertoire, un nom de fichier, et une extension de nom de fichier.  `_wmakepath_s` est une version à caractères larges de `_makepath_s` ; les arguments de `_wmakepath_s` sont des chaînes à caractères larges.  `_wmakepath_s` et `_makepath_s` se comportent sinon de manière identique.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tmakepath_s`|`_makepath_s`|`_makepath_s`|`_wmakepath_s`|  
  
 L'argument `path` doit indiquer une mémoire tampon vide suffisante pour contenir le chemin complet.  Le `path` composite ne doit pas être supérieur à la constante `_MAX_PATH`, définie dans Stdlib.h.  
  
 Si le chemin d'accès a la valeur `NULL`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  En outre, `errno` est affecté à la valeur `EINVAL`.  Vous pouvez insérer des valeurs `NULL` pour tous les autres paramètres.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD.  Pour désactiver ce comportement, utilisez [\_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_makepath_s`|\<stdlib.h\>|  
|`_wmakepath_s`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_makepath_s.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char path_buffer[_MAX_PATH];  
   char drive[_MAX_DRIVE];  
   char dir[_MAX_DIR];  
   char fname[_MAX_FNAME];  
   char ext[_MAX_EXT];  
   errno_t err;  
  
   err = _makepath_s( path_buffer, _MAX_PATH, "c", "\\sample\\crt\\",  
                      "crt_makepath_s", "c" );  
   if (err != 0)  
   {  
      printf("Error creating path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path created with _makepath_s: %s\n\n", path_buffer );  
   err = _splitpath_s( path_buffer, drive, _MAX_DRIVE, dir, _MAX_DIR, fname,  
                       _MAX_FNAME, ext, _MAX_EXT );  
   if (err != 0)  
   {  
      printf("Error splitting the path. Error code %d.\n", err);  
      exit(1);  
   }  
   printf( "Path extracted with _splitpath_s:\n" );  
   printf( "  Drive: %s\n", drive );  
   printf( "  Dir: %s\n", dir );  
   printf( "  Filename: %s\n", fname );  
   printf( "  Ext: %s\n", ext );  
}  
```  
  
## Sortie  
  
```  
Path created with _makepath_s: c:\sample\crt\crt_makepath_s.c  
  
Path extracted with _splitpath_s:  
  Drive: c:  
  Dir: \sample\crt\  
  Filename: crt_makepath_s  
  Ext: .c  
```  
  
## Équivalent .NET Framework  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_fullpath, \_wfullpath](../../c-runtime-library/reference/fullpath-wfullpath.md)   
 [\_splitpath\_s, \_wsplitpath\_s](../../c-runtime-library/reference/splitpath-s-wsplitpath-s.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)