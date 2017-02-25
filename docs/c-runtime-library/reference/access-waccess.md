---
title: "_access, _waccess | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_access"
  - "_waccess"
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
  - "_waccess"
  - "_access"
  - "taccess"
  - "waccess"
  - "_taccess"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_access (fonction)"
  - "_taccess (fonction)"
  - "_waccess (fonction)"
  - "access (fonction)"
  - "taccess (fonction)"
  - "waccess (fonction)"
ms.assetid: ba34f745-85c3-49e5-a7d4-3590bd249dd3
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# _access, _waccess
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Pour déterminer si un fichier est en lecture seule  Des versions plus sécurisées sont disponibles ; consultez [\_access\_s, \_waccess\_s](../../c-runtime-library/reference/access-s-waccess-s.md).  
  
## Syntaxe  
  
```  
int _access(   
   const char *path,   
   int mode   
);  
int _waccess(   
   const wchar_t *path,   
   int mode   
);  
```  
  
#### Paramètres  
 `path`  
 Fichier ou chemin d'accès au répertoire.  
  
 `mode`  
 Attribut en lecture\/écriture.  
  
## Valeur de retour  
 Chaque fonction retourne 0 si le fichier est le mode donné.  La fonction retourne – 1 si le fichier nommé n'existe pas ou n'a pas le mode donné ; dans ce cas, `errno` est défini comme indiqué dans le tableau suivant.  
  
 `EACCES`  
 Accès refusé : le paramètre d'autorisation du fichier n'autorise pas l'accès spécifié.  
  
 `ENOENT`  
 Fichier ou chemin d'accès introuvable.  
  
 `EINVAL`  
 Paramètre non valide.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Lorsqu'elle est utilisée avec les fichiers, la fonction `_access` détermine si le fichier ou le répertoire spécifié existe et a les attributs spécifiés par la valeur `mode`.  Lorsqu'ils sont utilisés avec des répertoires, `_access` détermine si le dossier spécifié existe ; dans [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] ou dans les systèmes d'exploitation et versions ultérieures, tous les répertoires ont un accès en lecture et en écriture.  
  
|Valeur de `mode`|Les contrôles de fichier|  
|----------------------|------------------------------|  
|00|Existence uniquement|  
|02|en écriture seule|  
|04|En lecture seule|  
|06|Création, lecture et écriture|  
  
 Cette fonction vérifie uniquement, si le fichier ou le répertoire est en lecture seule ou non, il ne vérifie pas les paramètres de sécurité du système de fichiers.  Pour cela vous avez besoin d'un jeton d'accès.  Pour plus d'informations sur la sécurité du système de fichiers, consultez les[Jetons d'accès](http://msdn.microsoft.com/library/windows/desktop/aa374909).  Une classe ATL existe pour fournir cette fonctionnalité ; consultez [CAccessToken Class](../../atl/reference/caccesstoken-class.md).  
  
 `_waccess` est une version à caractères larges de `_access`; l'argument `path` vers `_waccess` est une chaîne à caractères larges.  `_waccess` et `_access` se comportent sinon de manière identique.  
  
 Cette fonction valide ses paramètres.  Si `path` est `NULL` ou que `mode` ne spécifie aucun mode valide, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction définit `errno` à la valeur `EINVAL` et retourne \-1.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_taccess`|`_access`|`_access`|`_waccess`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-têtes facultatifs|  
|-------------|---------------------|---------------------------|  
|`_access`|\<io.h,\>|\<errno.h\>|  
|`_waccess`|\<stdio.h\> ou \<wchar.h\>|\<errno.h\>|  
  
## Exemple  
 L'exemple suivant utilise `_access`pour vérifier si le fichier nommé crt\_ACCESS.C existe et si l'écriture est autorisée.  
  
```  
// crt_access.c  
// compile with: /W1  
// This example uses _access to check the file named  
// crt_ACCESS.C to see if it exists and if writing is allowed.  
  
#include  <io.h>  
#include  <stdio.h>  
#include  <stdlib.h>  
  
int main( void )  
{  
    // Check for existence.  
    if( (_access( "crt_ACCESS.C", 0 )) != -1 )  
    {  
        printf_s( "File crt_ACCESS.C exists.\n" );  
  
        // Check for write permission.  
        // Assume file is read-only.  
        if( (_access( "crt_ACCESS.C", 2 )) == -1 )  
            printf_s( "File crt_ACCESS.C does not have write permission.\n" );  
    }  
}  
```  
  
  **Le fichier crt\_ACCESS.C existe.**  
**Le fichier crt\_ACCESS.C n'a pas l'autorisation d'écriture.**   
## Équivalent .NET Framework  
 <xref:System.IO.FileAccess?displayProperty=fullName>  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_stat, \_wstat, fonctions](../../c-runtime-library/reference/stat-functions.md)