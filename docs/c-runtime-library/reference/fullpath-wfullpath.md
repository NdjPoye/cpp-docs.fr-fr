---
title: _fullpath, _wfullpath | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fullpath
- _wfullpath
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
- wfullpath
- fullpath
- _wfullpath
- _fullpath
dev_langs:
- C++
helpviewer_keywords:
- _wfullpath function
- relative file paths
- absolute paths
- wfullpath function
- _fullpath function
- fullpath function
ms.assetid: 4161ec17-0d22-45dd-b07d-0222553afae9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a9874d4c0b3576f79880d95a04285be9ff299c7c
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="fullpath-wfullpath"></a>_fullpath, _wfullpath
Créer un nom de chemin absolu ou complet pour le nom de chemin relatif spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
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
  
#### <a name="parameters"></a>Paramètres  
 `absPath`  
 Pointeur vers une mémoire tampon contenant le nom de chemin absolu ou complet, ou NULL.  
  
 `relPath`  
 Nom de chemin d’accès relatif.  
  
 `maxLength`  
 Longueur maximale de la mémoire tampon du nom de chemin d'accès absolu (`absPath`). Cette longueur est représentée en octets pour `_fullpath` mais en caractères larges (`wchar_t`) pour `_wfullpath`.  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces fonctions retourne un pointeur vers une mémoire tampon contenant le nom de chemin absolu (`absPath`). En cas d’erreur (par exemple, si la valeur passée dans `relPath` comprend une lettre de lecteur qui n’est pas valide ou qui est introuvable, ou si la longueur du nom de chemin absolu créé (`absPath`) est supérieure à `maxLength`) la fonction retourne `NULL`.  
  
## <a name="remarks"></a>Notes  
 Le `_fullpath` développe le nom de chemin d’accès relatif dans `relPath` et son chemin d’accès complet ou absolu stocke ce nom dans `absPath`. Si `absPath` a la valeur NULL, `malloc` est utilisé pour allouer une mémoire tampon de longueur suffisante pour contenir le nom du chemin. Il incombe à l’appelant de libérer cette mémoire tampon. Un nom de chemin relatif spécifie un chemin vers un autre emplacement à partir de l’emplacement actuel (tel que le répertoire de travail actuel : « . »). Un nom de chemin absolu est l’extension d’un nom de chemin relatif qui indique le chemin complet requis pour atteindre l’emplacement souhaité à partir de la racine du système de fichiers. Contrairement à `_makepath`, `_fullpath` peut être utilisé pour obtenir le nom de chemin absolu pour les chemins relatifs (`relPath`) dont le nom comprend « ./ » ou « ../ ».  
  
 Par exemple, pour utiliser les routines du runtime C, l’application doit inclure les fichiers d’en-tête qui contiennent les déclarations pour les routines. Chaque instruction include du fichier d’en-tête référence l’emplacement du fichier de manière relative (à partir du répertoire de travail de l’application) :  
  
```  
#include <stdlib.h>  
```  
  
 quand le chemin absolu (emplacement de système de fichiers actuel) du fichier peut être :  
  
```  
\\machine\shareName\msvcSrc\crt\headerFiles\stdlib.h  
```  
  
 `_fullpath` gère automatiquement les arguments de chaîne de caractères multioctets si nécessaire, en identifiant les séquences de caractères multioctets en fonction de la page de codes multioctets en cours d’utilisation. `_wfullpath` est une version à caractères larges de `_fullpath` ; les arguments de chaîne de `_wfullpath` sont des chaînes à caractères larges. `_wfullpath` et `_fullpath` se comportent de la même manière, à ceci près que `_wfullpath` ne gère pas de chaînes de caractères multioctets.  
  
 Si `_DEBUG` et `_CRTDBG_MAP_ALLOC` sont tous deux définis, les appels à `_fullpath` et `_wfullpath` sont remplacés par les appels à `_fullpath_dbg` et `_wfullpath_dbg` pour permettre le débogage des allocations de mémoire. Pour plus d’informations, consultez [_fullpath_dbg, _wfullpath_dbg](../../c-runtime-library/reference/fullpath-dbg-wfullpath-dbg.md).  
  
 Si `maxlen` est inférieur ou égal à 0, cette fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `NULL`.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfullpath`|`_fullpath`|`_fullpath`|`_wfullpath`|  
  
 Si la mémoire tampon `absPath` a la valeur `NULL`, `_fullpath` appelle [malloc](../../c-runtime-library/reference/malloc.md) pour allouer une mémoire tampon et ignore l’argument `maxLength`. Il incombe à l’appelant de libérer cette mémoire tampon (à l’aide de [free](../../c-runtime-library/reference/free.md)) selon les besoins. Si l’argument `relPath` spécifie un lecteur de disque, le répertoire actuel de ce lecteur est combiné avec le chemin.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`_fullpath`|\<stdlib.h>|  
|`_wfullpath`|\<stdlib.h> ou \<wchar.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
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
  
```Output  
Full path is: C:\Documents and Settings\user\My Documents\test  
Full path is: C:\test  
Full path is: C:\Documents and Settings\user\test  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [_getcwd, _wgetcwd](../../c-runtime-library/reference/getcwd-wgetcwd.md)   
 [_getdcwd, _wgetdcwd](../../c-runtime-library/reference/getdcwd-wgetdcwd.md)   
 [_makepath, _wmakepath](../../c-runtime-library/reference/makepath-wmakepath.md)   
 [_splitpath, _wsplitpath](../../c-runtime-library/reference/splitpath-wsplitpath.md)