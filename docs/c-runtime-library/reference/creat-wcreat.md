---
title: _creat, _wcreat | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _creat
- _wcreat
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
- wcreat
- _wcreat
- _creat
- tcreat
- _tcreat
dev_langs:
- C++
helpviewer_keywords:
- wcreat function
- _wcreat function
- files [C++], creating
- _creat function
- tcreat function
- creat function
- _tcreat function
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0355f28ada6313e201b8d761813767135ee3cbf8
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="creat-wcreat"></a>_creat, _wcreat
Crée un fichier. `_creat` et `_wcreat` ont été déconseillées ; utilisez [_sopen_s, _wsopen_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md) à la place.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _creat(   
   const char *filename,  
   int pmode   
);  
int _wcreat(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `filename`  
 Nom du nouveau fichier.  
  
 `pmode`  
 Paramètre d'autorisation.  
  
## <a name="return-value"></a>Valeur de retour  
 Ces fonctions, en cas de réussite, retournent un descripteur de fichier pour le fichier créé. Dans le cas contraire, les fonctions retournent -1 et la valeur `errno` comme indiqué dans le tableau suivant.  
  
|Paramètre `errno` |Description|  
|---------------------|-----------------|  
|`EACCES`|`filename` spécifie un fichier en lecture seule existant ou un répertoire au lieu d’un fichier.|  
|`EMFILE`|Aucun autre descripteur de fichier n'est disponible.|  
|`ENOENT`|Le fichier spécifié est introuvable.|  
  
 Si `filename` a la valeur NULL ou est une chaîne vide, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent -1.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_creat` crée un fichier ou ouvre et tronque un fichier existant. `_wcreat` est une version à caractères larges de `_creat` ; l'argument `filename` de `_wcreat` est une chaîne à caractères larges. Sinon, `_wcreat` et `_creat` se comportent de la même façon.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 Si le fichier spécifié par `filename` n’existe pas, un fichier est créé avec le paramètre d’autorisation donné et est ouvert pour écriture. Si le fichier existe déjà et que son paramètre d’autorisation autorise l’écriture, `_creat` tronque le fichier à la longueur 0, détruisant le contenu précédent, et l’ouvre pour écriture. Le paramètre d’autorisation, `pmode`, s’applique uniquement aux fichiers qui viennent d’être créés. Le nouveau fichier reçoit le paramètre d’autorisation spécifié après sa première fermeture. L’expression entière `pmode` contient l’une des constantes de manifeste `_S_IWRITE` et `_S_IREAD` (ou les deux), définies dans SYS\Stat.h. Quand les deux constantes sont données, elles sont jointes avec l’opérateur `OR` au niveau du bit ( **&#124;**). Le paramètre `pmode` a l’une des valeurs suivantes.  
  
|Value|Définition|  
|-----------|----------------|  
|`_S_IWRITE`|Écriture autorisée.|  
|`_S_IREAD`|Lecture autorisée.|  
|`_S_IREAD &#124; _S_IWRITE`|Lecture et écriture autorisées.|  
  
 Si l'autorisation d'écriture n'est pas accordée, le fichier est en lecture seule. Tous les fichiers sont toujours accessibles en lecture ; il est impossible d’accorder l’autorisation en écriture seule. Ainsi, les modes `_S_IWRITE` et `_S_IREAD | _S_IWRITE` sont équivalents. Les fichiers ouverts à l’aide de `_creat` sont toujours ouverts en mode de compatibilité (voir [_sopen](../../c-runtime-library/reference/sopen-wsopen.md)) avec `_SH_DENYNO`.  
  
 `_creat` applique le masque d’autorisation de fichier actuel à `pmode` avant de définir les autorisations (voir [_umask](../../c-runtime-library/reference/umask.md)). `_creat` est fourni principalement pour assurer la compatibilité avec les bibliothèques précédentes. Un appel à `_open` avec `_O_CREAT` et `_O_TRUNC` dans le paramètre `oflag` équivaut à `_creat` et est préférable pour le nouveau code.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_creat`|\<io.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
|`_wcreat`|\<io.h> ou \<wchar.h>|\<sys/types.h>, \<sys/stat.h>, \<errno.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_creat.c  
// compile with: /W3  
// This program uses _creat to create  
// the file (or truncate the existing file)  
// named data and open it for writing.  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int fh;  
  
   fh = _creat( "data", _S_IREAD | _S_IWRITE ); // C4996  
   // Note: _creat is deprecated; use _sopen_s instead  
   if( fh == -1 )  
      perror( "Couldn't create data file" );  
   else  
   {  
      printf( "Created data file.\n" );  
      _close( fh );  
   }  
}  
```  
  
```Output  
Created data file.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de bas niveau](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_chsize](../../c-runtime-library/reference/chsize.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [_umask](../../c-runtime-library/reference/umask.md)