---
title: "_dupenv_s_dbg, _wdupenv_s_dbg | Microsoft Docs"
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
  - "_dupenv_s_dbg"
  - "_wdupenv_s_dbg"
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
apitype: "DLLExport"
f1_keywords: 
  - "_tdupenv_s_dbg"
  - "_dupenv_s_dbg"
  - "_wdupenv_s_dbg"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tdupenv_s_dbg (fonction)"
  - "dupenv_s_dbg (fonction)"
  - "_wdupenv_s_dbg (fonction)"
  - "variables d'environnement"
  - "tdupenv_s_dbg (fonction)"
  - "wdupenv_s_dbg (fonction)"
  - "_dupenv_s_dbg (fonction)"
ms.assetid: e3d81148-e24e-46d0-a21d-fd87b5e6256c
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _dupenv_s_dbg, _wdupenv_s_dbg
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtenir une valeur de l'environnement actuel.  Versions de [\_dupenv\_s, \_wdupenv\_s](../../c-runtime-library/reference/dupenv-s-wdupenv-s.md) qui allouent la mémoire avec [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md) pour fournir des informations de débogage supplémentaires.  
  
## Syntaxe  
  
```  
errno_t _dupenv_s_dbg(  
   char **buffer,  
   size_t *numberOfElements,  
   const char *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
errno_t _wdupenv_s_dbg(  
   wchar_t **buffer,  
   size_t * numberOfElements,  
   const wchar_t *varname,  
   int blockType,  
   const char *filename,  
   int linenumber  
);  
```  
  
#### Paramètres  
 `buffer`  
 Mémoire tampon pour stocker la valeur de la variable.  
  
 `numberOfElements`  
 Taille du `buffer`.  
  
 `varname`  
 nom de la variable d'environnement  
  
 `blockType`  
 Type de bloc de mémoire demandé : `_CLIENT_BLOCK` ou `_NORMAL_BLOCK`.  
  
 `filename`  
 Pointeur du nom du fichier source ou `NULL`.  
  
 `linenumber`  
 Numéro de ligne dans le fichier source ou `NULL`.  
  
## Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur en cas de échec.  
  
 Ces fonctions valident leurs paramètres ; si `buffer` ou `varname` sont `NULL`, le gestionnaire de paramètre non valide est appelé comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, les fonctions définissent `errno` avec la valeur `EINVAL` et retournent `EINVAL`.  
  
 Si ces fonctions ne peuvent pas allouer suffisamment de mémoire, ils définissent `buffer` à `NULL` et `numberOfElements` à 0, et retournent `ENOMEM`.  
  
## Notes  
 Les fonctions `_dupenv_s_dbg` et `_wdupenv_s_dbg` sont identiques à `_dupenv_s` et `_wdupenv_s` mais lorsque `_DEBUG` est défini, ces fonctions utilisent la version Debug [malloc](../../c-runtime-library/reference/malloc.md), [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md), pour allouer de la mémoire à la variable d'environnement.  Pour plus d'informations sur les fonctionnalités de débogage de `_malloc_dbg`, consultez [\_malloc\_dbg](../../c-runtime-library/reference/malloc-dbg.md).  
  
 Vous n'avez pas besoin d'appeler ces fonctions explicitement dans la plupart des cas.  À la place, il vous est possible d'affecter l'indicateur `_CRTDBG_MAP_ALLOC`.  Lorsque `_CRTDBG_MAP_ALLOC` est défini, les appels à `_dupenv_s` et l'`_wdupenv_s` sont remappés à `_dupenv_s_dbg` et `_wdupenv_s_dbg`, respectivement, avec `blockType` à la valeur `_NORMAL_BLOCK`.  Ainsi, vous n'avez pas besoin d'appeler ces fonctions explicitement sauf si vous souhaitez marquer les blocs de tas comme `_CLIENT_BLOCK`.  Pour plus d'informations sur les types de bloc, consultez [Types de bloc sur le tas de débogage](../Topic/CRT%20Debug%20Heap%20Details.md#BKMK_Types_of_blocks_on_the_debug_heap).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tdupenv_s_dbg`|`_dupenv_s_dbg`|`_dupenv_s_dbg`|`_wdupenv_s_dbg`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_dupenv_s_dbg`|\<crtdbg.h\>|  
|`_wdupenv_s_dbg`|\<crtdbg.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_dupenv_s_dbg.c  
#include  <stdlib.h>  
#include <crtdbg.h>  
  
int main( void )  
{  
   char *pValue;  
   size_t len;  
   errno_t err = _dupenv_s_dbg( &pValue, &len, "pathext",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "pathext = %s\n", pValue );  
   free( pValue );  
   err = _dupenv_s_dbg( &pValue, &len, "nonexistentvariable",  
      _NORMAL_BLOCK, __FILE__, __LINE__ );  
   if ( err ) return -1;  
   printf( "nonexistentvariable = %s\n", pValue );  
   free( pValue ); // It's OK to call free with NULL  
}  
```  
  
## Résultat de l'exemple  
  
```  
pathext = .COM;.EXE;.BAT;.CMD;.VBS;.VBE;.JS;.JSE;.WSF;.WSH;.pl  
nonexistentvariable = (null)  
```  
  
## Équivalent .NET Framework  
 [System::Environment::GetEnvironmentVariable](https://msdn.microsoft.com/en-us/library/system.environment.getenvironmentvariable.aspx)  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [Constantes d'environnement](../../c-runtime-library/environmental-constants.md)   
 [getenv\_s, \_wgetenv\_s](../../c-runtime-library/reference/getenv-s-wgetenv-s.md)   
 [\_putenv\_s, \_wputenv\_s](../../c-runtime-library/reference/putenv-s-wputenv-s.md)