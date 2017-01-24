---
title: "_fullpath, _wfullpath | Microsoft Docs"
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
  - "_fullpath"
  - "_wfullpath"
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
  - "wfullpath"
  - "fullpath"
  - "_wfullpath"
  - "_fullpath"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fullpath (fonction)"
  - "_wfullpath (fonction)"
  - "chemins d'accès absolus"
  - "fullpath (fonction)"
  - "chemins d'accès de fichier relatifs"
  - "wfullpath (fonction)"
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fullpath, _wfullpath
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un nom de chemin d'accès absolu ou complet pour le chemin d'accès relatif spécifié.  
  
## Syntaxe  
  
```  
char *_fullpath(   
   char *absPath,  
   const char *relPath,  
   size_t maxLength   
);  
wchar_t *_wfullpath(   
   wchar_t *absPath,  
   const wchar_t *relPath,  
   size_t maxLength   
);  
```  
  
#### Paramètres  
 `absPath`  
 Pointeur vers une mémoire tampon qui contient le de chemin absolu ou relatif, ou NULL.  
  
 `relPath`  
 Nom du chemin d'accès relatif.  
  
 `maxLength`  
 Longueur maximale de la mémoire tampon du nom de chemin d'accès absolu \(`absPath`\).  Cette longueur est en octets pour `_fullpath` mais en caractères larges \(`wchar_t`\) pour `_wfullpath`.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne un pointeur vers une mémoire tampon qui contient le chemin d'accès absolu \(`absPath`\).  En cas d'erreur \(par exemple, si la valeur transmise dans `relPath` inclut une lettre de lecteur qui n'est pas valide ou est introuvable, ou si le nom du chemin d'accès absolu créé \(`absPath`\) est supérieur à `maxLength`\) la fonction retourne `NULL`.  
  
## Notes  
 La fonction `_fullpath` développe le chemin d'accès relatif dans `relPath` en son chemin d'accès complet ou absolu et enregistre ce nom dans `absPath`*.* Si `absPath` est NULL, `malloc` est utilisée pour allouer une mémoire tampon de taille suffisante pour contenir le chemin d'accès.  Il incombe à l'appelleur \(client\) de libérer cette mémoire tampon.  Un nom de chemin d'accès relatif spécifie un chemin d'accès à un autre emplacement de la position actuelle \(comme le répertoire de travail actuel : " ."\).  Un chemin d'accès absolu est l'extension d'un nom de chemin d'accès relatif qui décrit le chemin d'accès complet requis pour accéder à l'emplacement souhaité de la racine du système de fichiers.  Contrairement à `_makepath`, `_fullpath` peut être utilisé pour obtenir le chemin d'accès absolu pour les chemins d'accès relatif \(`relPath`\) qui contiennent « . \/ » ou « . \/ » dans leurs noms.  
  
 Par exemple, pour utiliser des routines runtime C, l'application doit inclure les fichiers d'en\-tête contenant les déclarations des routines.  Chaque fichier d'en\-tête incluent des références d'instructions l'emplacement du fichier de manière relative \(à partir de le répertoire de travail d'application\) :  
  
```  
#include <stdlib.h>  
```  
  
 lorsque le chemin d'accès absolu \(emplacement du système de fichiers réel\) du fichier peut être :  
  
```  
\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h  
```  
  
 `_fullpath`  gère automatiquement des arguments de chaîne de caractères multi\-octets comme appropriés, en identifiant des séquences de caractères multi\-octets d'après la page de codes multioctets en cours d'utilisation.  `_wfullpath`  est une version à caractères larges de `_fullpath` ; les arguments de chaînes de `_wfullpath`  sont des chaînes à caractères larges.  `_wfullpath`  et `_fullpath`  se comportent de la même manière que `_wfullpath`  mais ne gèrent pas les chaînes de caractères multi\-octets.  
  
 Si `_DEBUG`  et `_CRTDBG_MAP_ALLOC`  sont définis, les appels à `_fullpath` et `_wfullpath` sont remplacés par des appels à `_fullpath_dbg` et `_wfullpath_dbg` pour conserver de la mémoire pour les allocations de déboguage.  Pour plus d'informations, consultez l'[\_fullpath\_dbg, \_wfullpath\_dbg](../../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md).  
  
 Cette fonction appelle le gestionnaire de paramètres invalides, comme décrit dans[Validation de paramètre](../../c-runtime-library/parameter-validation.md), si `maxlen` est inférieur ou égal à zéro.  Si l'exécution est autorisée à se poursuivre, cette fonction paramètre `errno` à `EINVAL` et renvoie `NULL`.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tfullpath`|`_fullpath`|`_fullpath`|`_wfullpath`|  
  
 Si la mémoire tampon `absPath` est `NULL`, `_fullpath` appelle [malloc](../../c-runtime-library/reference/malloc.md) pour allouer une mémoire tampon et ignore l'argument `maxLength`.  Il incombe à l'appelant de libérer cette mémoire tampon \(en utilisaut  [disponible](../../c-runtime-library/reference/free.md)\) comme il convient.  Si l'argument `relPath` spécifie un lecteur de disque, le répertoire actif de ce lecteur est associé au chemin d'accès.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fullpath`|\<stdlib.h\>|  
|`_wfullpath`|\<stdlib.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fullpath.c  
// This program demonstrates how _fullpath  
// creates a full path from a partial path.  
  
#include <stdio.h>  
#include <conio.h>  
#include <stdlib.h>  
#include <direct.h>  
  
void PrintFullPath( char * partialPath )  
{  
   char full[_MAX_PATH];  
   if( _fullpath( full, partialPath, _MAX_PATH ) != NULL )  
      printf( "Full path is: %s\n", full );  
   else  
      printf( "Invalid path\n" );  
}  
  
int main( void )  
{  
   PrintFullPath( "test" );  
   PrintFullPath( "\\test" );  
   PrintFullPath( "..\\test" );  
}  
```  
  
  **Le chemin d'accès complet est : C:\\Documents and settings\\utilisateur\\mes documents\\test**  
**Le chemin d'accès complet est : C:\\test**  
**Le chemin d'accès complet est : C:\\Documents and settings\\utilisateur\\test**   
## Équivalent .NET Framework  
 [System::IO::File::Create](https://msdn.microsoft.com/en-us/library/system.io.file.create.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_getcwd, \_wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [\_getdcwd, \_wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [\_makepath, \_wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [\_splitpath, \_wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)