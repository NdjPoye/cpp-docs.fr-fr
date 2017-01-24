---
title: "_chmod, _wchmod | Microsoft Docs"
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
  - "_chmod"
  - "_wchmod"
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
  - "_chmod"
  - "_wchmod"
  - "wchmod"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_chmod (fonction)"
  - "_wchmod (fonction)"
  - "chmod (fonction)"
  - "autorisations fichier (C++)"
  - "fichiers (C++), modifier les autorisations"
  - "wchmod (fonction)"
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
caps.latest.revision: 23
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _chmod, _wchmod
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Modifie les paramètres d'autorisation du fichier.  
  
## Syntaxe  
  
```  
  
      int _chmod(   
   const char *filename,  
   int pmode   
);  
int _wchmod(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### Paramètres  
 `filename`  
 Nom du fichier existant  
  
 `pmode`  
 Paramètre d'autorisation pour le fichier.  
  
## Valeur de retour  
 Ces fonctions retournent 0 si le paramètre d'autorisation a été modifié avec succès.  Une valeur de retour de – 1 indique un échec.  Si le fichier spécifié est introuvable, `errno` a la valeur `ENOENT`; si un paramètre est non valide, `errno` a la valeur `EINVAL`.  
  
## Notes  
 La fonction `_chmod` change le paramètre d'autorisation du fichier spécifié par `filename`*.* Le paramètre d'autorisation contrôle l'accès en lecture et en écriture au fichier.  L'expression entière `pmode` contient une des deux ou les deux constantes manifestes suivantes, défini dans SYS\\Stat.h.  
  
 `_S_IWRITE`  
 Écriture autorisée.  
  
 `_S_IREAD`  
 Lecture autorisée.  
  
 `_S_IREAD | _S_IWRITE`  
 Lecture et écriture autorisées.  
  
 Lorsque les deux constantes sont fournies, elles sont jointes à l'opérateur de bits `OR` \(          `|` \).  Si l'autorisation d'écriture n'est pas donnée, le fichier est en lecture seule.  Notez que tous les fichiers sont toujours lisibles ; il est impossible de donner l'autorisation en écriture seule.  Par conséquent, les modes `_S_IWRITE` et `_S_IREAD | _S_IWRITE` sont équivalents.  
  
 `_wchmod` est une version à caractères larges de `_chmod`; l'argument `filename` vers `_wchmod` est une chaîne à caractères larges.  `_wchmod` et `_chmod` se comportent sinon de manière identique.  
  
 Cette fonction valide ses paramètres.  Si `pmode` n'est pas une combinaison de l'une des constantes manifestes ou n'incorpore pas un jeu de remplacement de constantes, la fonction ignore simplement celles\-ci.  Si `filename` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est défini comme `EINVAL` et la fonction retourne \-1.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tchmod`|`_chmod`|`_chmod`|`_wchmod`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_chmod`|\<io.h,\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
|`_wchmod`|\<io.h\> ou \<wchar.h\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_chmod.c  
// This program uses _chmod to  
// change the mode of a file to read-only.  
// It then attempts to modify the file.  
//  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
// Change the mode and report error or success   
void set_mode_and_report(char * filename, int mask)  
{  
   // Check for failure   
   if( _chmod( filename, mask ) == -1 )  
   {  
      // Determine cause of failure and report.   
      switch (errno)  
      {  
         case EINVAL:  
            fprintf( stderr, "Invalid parameter to chmod.\n");  
            break;  
         case ENOENT:  
            fprintf( stderr, "File %s not found\n", filename );  
            break;  
         default:  
            // Should never be reached   
            fprintf( stderr, "Unexpected error in chmod.\n" );  
       }  
   }  
   else  
   {  
      if (mask == _S_IREAD)  
        printf( "Mode set to read-only\n" );  
      else if (mask & _S_IWRITE)  
        printf( "Mode set to read/write\n" );  
   }  
   fflush(stderr);  
}  
  
int main( void )  
{   
  
   // Create or append to a file.   
   system( "echo /* End of file */ >> crt_chmod.c_input" );  
  
   // Set file mode to read-only:   
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );  
  
   // Change back to read/write:   
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );   
}   
```  
  
  **`Une ligne de texte.`  `Une ligne de texte.` Mode défini en lecture seule**  
**Accès refusé.**  
**Mode défini en lecture\-écriture**   
## Équivalent .NET Framework  
  
-   [System::IO::File::SetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.setattributes.aspx)  
  
-   [System::Security::Permissions::FileIOPermission](https://msdn.microsoft.com/en-us/library/system.security.permissions.fileiopermission.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat, \_wstat, fonctions](../../c-runtime-library/reference/stat-functions.md)