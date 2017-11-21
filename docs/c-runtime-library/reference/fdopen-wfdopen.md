---
title: _fdopen, _wfdopen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fdopen
- _wfdopen
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
apitype: DLLExport
f1_keywords:
- _tfdopen
- _fdopen
- _wfdopen
- wfdopen
- tfdopen
dev_langs: C++
helpviewer_keywords:
- wfdopen function
- _fdopen function
- _wfdopen function
- tfdopen function
- fdopen function
- _tfdopen function
- streams, associating with files
ms.assetid: 262757ff-1e09-4472-a5b6-4325fc28f971
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: bacc1decd25c5c7291295a9e97eeacb35d55662c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="fdopen-wfdopen"></a>_fdopen, _wfdopen
Associe un flux à un fichier ouvert précédemment pour une E/S de bas niveau.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
FILE *_fdopen(    
   int fd,  
   const char *mode   
);  
FILE *_wfdopen(   
   int fd,  
   const wchar_t *mode   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `fd`  
 Descripteur du fichier ouvert.  
  
 `mode`  
 Type d'accès fichier.  
  
## <a name="return-value"></a>Valeur de retour  
 Chacune de ces fonctions retourne un pointeur désignant le flux ouvert. Une valeur de pointeur null indique une erreur. Quand une erreur se produit, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `errno` a soit la valeur `EBADF`, ce qui indique un descripteur de fichier incorrect, soit la valeur `EINVAL`, ce qui indique que `mode` était un pointeur null.  
  
 Pour plus d’informations sur ces codes d’erreur et autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_fdopen` associe un flux d'E/S au fichier identifié par `fd` et permet donc la mise en mémoire tampon et la mise en forme d'un fichier ouvert pour une E/S de bas niveau. `_wfdopen` est une version à caractères larges de `_fdopen` ; l'argument `mode` de `_wfdopen` est une chaîne à caractères larges. Sinon, `_wfdopen` et `_fdopen` se comportent de la même façon.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfdopen`|`_fdopen`|`_fdopen`|`_wfdopen`|  
  
 La chaîne de caractères `mode` spécifie le type de fichier et d'accès fichier.  
  
 La chaîne de caractères `mode` spécifie le type d'accès demandé pour le fichier, comme indiqué dans le tableau suivant.  
  
 `"r"`  
 Ouvre pour l'accès en lecture. Si le fichier n'existe pas ou est introuvable, l'appel à `fopen` échoue.  
  
 `"w"`  
 Ouvre un fichier vide pour l'accès en écriture. Si le fichier spécifié existe, son contenu est détruit.  
  
 `"a"`  
 Ouvre pour l'accès en écriture, à la fin du fichier (ajout). Crée le fichier s'il n'existe pas.  
  
 `"r+"`  
 Ouvre pour l'accès en lecture et en écriture. (Le fichier doit exister.)  
  
 `"w+"`  
 Ouvre un fichier vide pour l'accès en lecture et en écriture. Si le fichier spécifié existe, son contenu est détruit.  
  
 `"a+"`  
 S'ouvre pour lecture et ajout. Crée le fichier s'il n'existe pas.  
  
 Quand un fichier est ouvert avec le type d'accès `"a"` ou `"a+"`, toutes les opérations d'écriture se produisent à la fin du fichier. Le pointeur de fichier peut être repositionné à l'aide de `fseek` ou `rewind`, mais il est toujours redéplacé à la fin du fichier avant toute opération d'écriture. Par conséquent, les données existantes ne peuvent pas être remplacées. Lorsque le type d'accès `"r+"`, `"w+"` ou `"a+"` est spécifié, la lecture et l'écriture sont autorisées (on dit que le fichier est ouvert pour « mise à jour »). Cependant, quand vous basculez entre lecture et écriture, une opération intermédiaire `fflush`, `fsetpos`, `fseek` ou `rewind` doit exister. Vous pouvez éventuellement spécifier la position actuelle pour l'opération `fsetpos` ou `fseek`.  
  
 Outre les valeurs ci-dessus, les caractères suivants peuvent aussi être inclus dans `mode` pour spécifier le mode de traduction des caractères de nouvelle ligne.  
  
 `t`  
 Ouvrir en mode texte (traduit). Dans ce mode, les combinaisons retour chariot-saut de ligne sont traduites en flux d'une ligne (saut de ligne) en entrée, et les caractères de saut de ligne sont traduits en combinaisons retour chariot/saut de ligne en sortie. De même, Ctrl+Z est interprété comme un caractère de fin de fichier en entrée. Dans les fichiers ouverts pour lecture/écriture, `fopen` recherche un Ctrl+Z à la fin du fichier et le supprime, si possible. En effet, l'utilisation des fonctions `fseek` et `ftell` pour se déplacer dans un fichier qui se termine par un Ctrl+Z peut provoquer un comportement incorrect de `fseek` près de la fin du fichier.  
  
 `b`  
 Ouvrir en mode binaire (non traduit). Les traductions du mode `t` sont supprimées.  
  
 `c`  
 Activer l'indicateur de validation pour le `filename` associé, afin que le contenu de la mémoire tampon de fichier soit écrit directement sur disque si `fflush` ou `_flushall` est appelé.  
  
 `n`  
 Réinitialiser l'indicateur de validation pour le `filename` associé à la valeur « no-commit » Il s'agit de la valeur par défaut. Substitue aussi l'indicateur de validation globale si vous liez votre programme avec Commode.obj. La valeur par défaut de l’indicateur de validation globale est « no-commit », sauf si vous liez explicitement votre programme avec Commode.obj.  
  
 Les options `t`, `c` et `n` `mode` sont des extensions Microsoft pour `fopen` et `_fdopen`. Ne les utilisez pas si vous voulez préserver la portabilité ANSI.  
  
 Si `t` ou `b` n’est pas donné dans `mode`, le mode de traduction par défaut est défini par la variable globale [_fmode](../../c-runtime-library/fmode.md). Si `t` ou `b` a l'argument comme préfixe, la fonction échoue et retourne `NULL`. Pour en savoir plus sur les modes texte et binaire, consultez [E/S de fichier en mode texte et binaire](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
 Les caractères valides pour la chaîne `mode` utilisée dans `fopen` et `_fdopen` correspondent aux arguments `oflag` utilisés dans [_open](../../c-runtime-library/reference/open-wopen.md) et [_sopen](../../c-runtime-library/reference/sopen-wsopen.md), comme suit.  
  
|Caractères dans la chaîne `mode`|Valeur `oflag` équivalente pour `_open`/`_sopen`|  
|---------------------------------|---------------------------------------------------|  
|`a`|`_O_WRONLY &#124; _O_APPEND` (généralement `_O_WRONLY &#124; _O_CREAT &#124; _O_APPEND`)|  
|`a+`|`_O_RDWR &#124; _O_APPEND` (généralement `_O_RDWR &#124; _O_APPEND &#124; _O_CREAT` )|  
|`r`|`_O_RDONLY`|  
|`r+`|`_O_RDWR`|  
|`w`|`_O_WRONLY` (généralement `_O_WRONLY &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`w+`|`_O_RDWR` (généralement `_O_RDWR &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`b`|`_O_BINARY`|  
|`t`|`_O_TEXT`|  
|`c`|Aucun|  
|`n`|Aucun|  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`_fdopen`|\<stdio.h>|  
|`_wfdopen`|\<stdio.h> ou \<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_fdopen.c  
// This program opens a file by using low-level  
// I/O, then uses _fdopen to switch to stream  
// access. It counts the lines in the file.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
#include <share.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  fd, count = 0;  
   char inbuf[128];  
  
   // Open a file.  
   if( _sopen_s( &fd, "crt_fdopen.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
      exit( 1 );  
  
   // Get stream from file descriptor.  
   if( (stream = _fdopen( fd, "r" )) == NULL )  
      exit( 1 );  
  
   while( fgets( inbuf, 128, stream ) != NULL )  
      count++;  
  
   // After _fdopen, close by using fclose, not _close.  
   fclose( stream );  
   printf( "Lines in file: %d\n", count );  
}  
```  
  
## <a name="input-crtfdopentxt"></a>Entrée : crt_fdopen.txt  
  
```  
Line one  
Line two  
```  
  
### <a name="output"></a>Sortie  
  
```  
Lines in file: 2  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)