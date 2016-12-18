---
title: "perror, _wperror | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wperror"
  - "perror"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_wperror"
  - "_tperror"
  - "perror"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tperror (fonction)"
  - "_wperror (fonction)"
  - "messages d'erreur, imprimer"
  - "perror (fonction)"
  - "messages d'erreur d'impression"
  - "tperror (fonction)"
  - "wperror (fonction)"
ms.assetid: 34fce792-16fd-4673-9849-cd88b54b6cd5
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# perror, _wperror
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourner un message d'erreur.  
  
## Syntaxe  
  
```  
  
      void perror(  
   const char *string   
);  
void _wperror(  
   const wchar_t *string   
);  
```  
  
#### Paramètres  
 `string`  
 Chaîne du message à retourner.  
  
## Notes  
 La fonction `perror` affiche un message d'erreur à `stderr`.  `_wperror` est une version à large caractères de **\_perror**; l'argument `string` de `_wperror` est une chaîne de larges caractères.  Pour le reste, `_wperror` et **\_perror** se comportent de la même manière.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tperror`|`perror`|`perror`|`_wperror`|  
  
 `string` est retourné tout d'abord, suivi de deux\-points, puis par le message d'erreur du système pour le dernier appel de bibliothèque qui a généré l'erreur, et enfin par un caractère de saut de ligne.  Si `string` est un pointeur null ou un pointeur vers une chaîne Null, `perror` affiche uniquement le message d'erreur système.  
  
 Numéro d'erreur stocké dans [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) variable \(défini dans ERRNO.H\).  Les messages d'erreur système sont accessibles via le variable [\_sys\_errlist](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md), qui est un tableau du nombre par erreur classé par messages.  `perror` imprime le message d'erreur approprié à la valeur `errno` en tant qu'index de `_sys_errlist`.  La valeur de la variable [\_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) est définie comme nombre maximal d'éléments du tableau `_sys_errlist`.  
  
 Pour des résultats exacts, appelez `perror` immédiatement après une routine de bibliothèque retourne avec une erreur.  Sinon, les appels suivants peuvent réecrire la valeur `errno`.  
  
 Dans le système d'exploitation Windows, certaines valeurs `errno` répertoriées dans ERRNO.H sont non\-utilisées.  Ces valeurs sont réservés pour une utilisation par le système d'exploitation UNIX.  Voir [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour une liste de valeurs `errno` utilisées par le système d'exploitation Windows.  `perror` affiche une chaîne vide pour toute valeur `errno` non utilisée par ces plateformes.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`perror`|\<stdio.h\> or \<stdlib.h\>|  
|`_wperror`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_perror.c  
// compile with: /W3  
/* This program attempts to open a file named  
 * NOSUCHF.ILE. Because this file probably doesn't exist,  
 * an error message is displayed. The same message is  
 * created using perror, strerror, and _strerror.  
 */  
  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <share.h>  
  
int main( void )  
{  
   int  fh;  
  
   if( _sopen_s( &fh, "NOSUCHF.ILE", _O_RDONLY, _SH_DENYNO, 0 ) != 0 )  
   {  
      /* Three ways to create error message: */  
      perror( "perror says open failed" );  
      printf( "strerror says open failed: %s\n",  
         strerror( errno ) ); // C4996  
      printf( _strerror( "_strerror says open failed" ) ); // C4996  
      // Note: strerror and _strerror are deprecated; consider  
      // using strerror_s and _strerror_s instead.  
   }  
   else  
   {  
      printf( "open succeeded on input file\n" );  
      _close( fh );  
   }  
}  
```  
  
## Sortie  
  
```  
perror says open failed: No such file or directory  
strerror says open failed: No such file or directory  
_strerror says open failed: No such file or directory  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [strerror, \_strerror, \_wcserror, \_\_wcserror](../../c-runtime-library/reference/strerror-strerror-wcserror-wcserror.md)