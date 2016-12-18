---
title: "_access_s, _waccess_s | Microsoft Docs"
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
  - "_access_s"
  - "_waccess_s"
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
  - "waccess_s"
  - "access_s"
  - "_waccess_s"
  - "_access_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_access_s (fonction)"
  - "_taccess_s (fonction)"
  - "_waccess_s (fonction)"
  - "access_s (fonction)"
  - "taccess_s (fonction)"
  - "waccess_s (fonction)"
ms.assetid: fb3004fc-dcd3-4569-8b27-d817546e947e
caps.latest.revision: 28
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _access_s, _waccess_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine les autorisations de lecture\/écriture du fichier.  Il s'agit de versions de [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t _access_s(   
   const char *path,   
   int mode   
);  
errno_t _waccess_s(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### Paramètres  
 `path`  
 Fichier ou chemin d'accès au répertoire.  
  
 `mode`  
 Définition des autorisations  
  
## Valeur de retour  
 Chaque fonction retourne 0 si le fichier est le mode donné.  La fonction retourne un code d'erreur si le fichier nommé n'existe pas ou n'est pas disponible dans le mode donné.  Dans ce cas, la fonction retourne un code d'erreur de l'ensemble de la façon suivante et définit également `errno`à la même valeur.  
  
 `EACCES`  
 Accès refusé.  Le paramètre d'autorisation du fichier n'autorise pas l'accès spécifié.  
  
 `ENOENT`  
 Fichier ou chemin d'accès introuvable.  
  
 `EINVAL`  
 Paramètre non valide.  
  
 Pour plus d'informations, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Lorsqu'elle est utilisée avec les fichiers, la fonction `_access_s` détermine si le fichier spécifié existe et est accessible comme spécifié par la valeur de`mode`.  Lorsqu'ils sont utilisés avec des répertoires, `_access_s` détermine seulement si le repertoire spécifié existe.  Dans [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] et dans les systèmes d'exploitation ultérieurs, tous les répertoires ont un accès en lecture et en écriture.  
  
|valeur du mode|Les contrôles de fichier|  
|--------------------|------------------------------|  
|00|Existence uniquement.|  
|02|Autorisation d'écriture.|  
|04|Autorisation de lecture.|  
|06|Autorisation de lecture et d'écriture.|  
  
 L'autorisation de lire ou écrire le fichier n'est pas suffisante pour garantir la possibilité d'ouvrir un fichier.  Par exemple, si un fichier est verrouillé par un autre processus, elle peut ne pas être accessibles même si  `_access_s`retourne 0.  
  
 `_waccess_s` est une version à caractères larges de `_access_s`; dans laquelle l'argument `path` vers `_waccess_s` est une chaîne à caractères larges.  Sinon, `_waccess_s` et `_access_s` se comportent de la même façon.  
  
 Ces fonctions valident leurs paramètres.  Si `path` est `NULL` ou que `mode` ne spécifie aucun mode valide, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` à la valeur `EINVAL` et retournent `EINVAL`.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_taccess_s`|`_access_s`|`_access_s`|`_waccess_s`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_access_s`|\<io.h,\>|\<errno.h\>|  
|`_waccess_s`|\<stdio.h\> ou \<wchar.h\>|\<errno.h\>|  
  
## Exemple  
 L'exemple suivant utilise `_access_s`pour vérifier si le fichier nommé crt\_ACCESS.C existe et si l'écriture est autorisée.  
  
```  
// crt_access_s.c  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    errno_t err = 0;  
  
    // Check for existence.   
    if ((err = _access_s( "crt_access_s.c", 0 )) == 0 )  
    {  
        printf_s( "File crt_access_s.c exists.\n" );  
  
        // Check for write permission.   
        if ((err = _access_s( "crt_access_s.c", 2 )) == 0 )  
        {  
            printf_s( "File crt_access_s.c does have "  
                      "write permission.\n" );  
        }  
        else  
        {  
            printf_s( "File crt_access_s.c does not have "  
                      "write permission.\n" );  
        }  
    }  
    else  
    {  
        printf_s( "File crt_access_s.c does not exist.\n" );  
    }  
}  
```  
  
  **Le fichier crt\_access\_s.c existe.**  
**Le fichier crt\_access\_s.c n'a pas l'autorisation d'écriture.**   
## Équivalent .NET Framework  
 <xref:System.IO.FileAccess?displayProperty=fullName>  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat, \_wstat, fonctions](../../c-runtime-library/reference/stat-functions.md)