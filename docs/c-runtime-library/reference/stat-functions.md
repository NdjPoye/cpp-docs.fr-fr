---
title: "_stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32 | Microsoft Docs"
ms.custom: ""
ms.date: "12/09/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wstat64"
  - "_stati64"
  - "_stat32"
  - "_stat32i64"
  - "_stat"
  - "_wstati64"
  - "_wstat32"
  - "_wstat64i32"
  - "_wstat"
  - "_stat64"
  - "_stat64i32"
  - "_wstat32i64"
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
  - "tstat32"
  - "tstat"
  - "_tstat64i32"
  - "tstati64"
  - "_wstat64"
  - "_wstat32"
  - "wstati64"
  - "tstat64"
  - "_stati64"
  - "_wstat"
  - "wstat64i32"
  - "stat32i64"
  - "tstat32i64"
  - "_tstat"
  - "_wstati64"
  - "_tstati64"
  - "_wstat32i64"
  - "wstat32"
  - "_wstat64i32"
  - "_stat"
  - "_tstat32"
  - "stat64i32"
  - "wstat64"
  - "stat"
  - "_stat32i64"
  - "_stat32"
  - "stati64"
  - "wstat"
  - "_stat64i32"
  - "stat32"
  - "_tstat32i64"
  - "tstat64i32"
  - "_tstat64"
  - "_stat64"
  - "stat/_stat"
  - "stat/_stat32"
  - "stat/_stat64"
  - "stat/_stati64"
  - "stat/_stat32i64"
  - "stat/_stat64i32"
  - "stat/_wstat"
  - "stat/_wstat32"
  - "stat/_wstat64"
  - "stat/_wstati64"
  - "stat/_wstat32i64"
  - "stat/_wstat64i32"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fichiers [C++], informations d’état"
  - "_stat, fonction"
  - "_wstat, fonction"
  - "_stat64i32, fonction"
  - "tstat, fonction"
  - "_tstat64i32, fonction"
  - "_stati64, fonction"
  - "_stat64, fonction"
  - "tstati64, fonction"
  - "wstati64, fonction"
  - "wstat64, fonction"
  - "_wstat64i32, fonction"
  - "_tstat32i64, fonction"
  - "_stat32i64, fonction"
  - "stat, fonction"
  - "statut des fichiers"
  - "_tstat32, fonction"
  - "tstat64, fonction"
  - "_wstat64, fonction"
  - "_tstat, fonction"
  - "_stat32, fonction"
  - "wstat, fonction"
  - "_wstat32i64, fonction"
  - "_tstati64, fonction"
  - "_wstat32, fonction"
  - "stat64, fonction"
  - "stati64, fonction"
  - "_wstati64, fonction"
  - "_tstat64, fonction"
  - "fichiers [C++], obtenir des informations d’état"
ms.assetid: 99a75ae6-ff26-47ad-af70-5ea7e17226a5
caps.latest.revision: 26
caps.handback.revision: 26
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _stat, _stat32, _stat64, _stati64, _stat32i64, _stat64i32, _wstat, _wstat32, _wstat64, _wstati64, _wstat32i64, _wstat64i32
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtenir des informations sur l’état d’un fichier.  
  
## Syntaxe  
  
```  
int _stat(  
   const char *path,  
   struct _stat *buffer   
);  
int _stat32(  
   const char *path,  
   struct __stat32 *buffer   
);  
int _stat64(  
   const char *path,  
   struct __stat64 *buffer   
);  
int _stati64(  
   const char *path,  
   struct _stati64 *buffer   
);  
int _stat32i64(  
   const char *path,  
   struct _stat32i64 *buffer   
);  
int _stat64i32(  
   const char *path,  
   struct _stat64i32 *buffer   
);  
int _wstat(  
   const wchar_t *path,  
   struct _stat *buffer   
);  
int _wstat32(  
   const wchar_t *path,  
   struct __stat32 *buffer   
);  
int _wstat64(  
   const wchar_t *path,  
   struct __stat64 *buffer   
);  
int _wstati64(  
   const wchar_t *path,  
   struct _stati64 *buffer   
);  
int _wstat32i64(  
   const wchar_t *path,  
   struct _stat32i64 *buffer   
);  
int _wstat64i32(  
   const wchar_t *path,  
   struct _stat64i32 *buffer   
);  
```  
  
#### Paramètres  
 `path`  
 Pointeur vers une chaîne contenant le chemin d’accès du fichier ou répertoire existant.  
  
 `buffer`  
 Pointeur vers une structure qui stocke les résultats.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne 0 si les informations sur l’état des fichiers sont obtenues. Une valeur de retour de \-1 indique une erreur. Dans ce cas, `errno` prend la valeur `ENOENT`, ce qui indique que le nom de fichier ou le chemin d’accès est introuvable. Une valeur de retour de `EINVAL` indique un paramètre non valide ; dans ce cas, `errno` prend également la valeur `EINVAL`.  
  
 Pour plus d’informations sur ce code de retour et sur les autres codes, consultez [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 L’horodatage d’un fichier peut être représenté si celle\-ci est ultérieure au 1er janvier 1970 à minuit et avant le 23:59:59 le 31 décembre 3000 UTC, sauf si vous utilisez `_stat32` ou `_wstat32`, ou vous avez défini `_USE_32BIT_TIME_T`, auquel cas la date peut être représentée uniquement jusqu'à 23:59:59 18 janvier 2038, UTC.  
  
## Notes  
 La fonction `_stat` obtient des informations sur le fichier ou le répertoire spécifié par `path` et les stocke dans la structure vers laquelle `buffer` pointe.`_stat` gère automatiquement les arguments de chaîne de caractères multioctets si nécessaire, en identifiant les séquences de caractères multioctets en fonction de la page de codes multioctets en cours d’utilisation.  
  
 `_wstat` est une version à caractères larges de `_stat` ; l'argument `path` de `_wstat` est une chaîne à caractères larges.`_wstat` et `_stat` se comportent de la même manière, sauf que `_wstat` ne gère pas les chaînes de caractères multioctets.  
  
 Les variantes de ces fonctions prennent en charge les types d’heures 32 ou 64 bits et les longueurs de fichiers 32 ou 64 bits. Le premier suffixe numérique \(`32` ou `64`\) indique la taille du type d’heure utilisé ; le deuxième suffixe est `i32` ou `i64`, qui indique si la taille du fichier est représentée comme un entier 32 bits ou 64 bits.  
  
 `_stat` est équivalent à `_stat64i32`, et `struct``_stat` contient une heure de 64 bits. Cela est vrai, sauf si `_USE_32BIT_TIME_T` est défini, auquel cas l’ancien comportement en vigueur, `_stat` utilise une durée de 32 bits, et `struct``_stat` contient une heure de 32 bits. La même remarque s’applique à `_stati64`.  
  
> [!NOTE]
>  `_wstat` ne fonctionne pas avec des liens symboliques [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Dans ce cas, `_wstat` indique toujours une taille de fichier de 0.`_stat` fonctionne correctement avec les liens symboliques.  
  
 Cette fonction valide ses paramètres. Si `path` ou `buffer` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
### Variantes de type d’heure et de type de longueur de fichier de \_stat  
  
|Fonctions|\_USE\_32BIT\_TIME\_T défini ?|Type d’heure|Type de longueur de fichier|  
|---------------|------------------------------------|------------------|---------------------------------|  
|`_stat`, `_wstat`|Non défini|64 bits|32 bits|  
|`_stat`, `_wstat`|Défini|32 bits|32 bits|  
|`_stat32`, `_wstat32`|Non affecté par la définition de macro|32 bits|32 bits|  
|`_stat64`, `_wstat64`|Non affecté par la définition de macro|64 bits|64 bits|  
|`_stati64`, `_wstati64`|Non défini|64 bits|64 bits|  
|`_stati64`, `_wstati64`|Défini|32 bits|64 bits|  
|`_stat32i64`, `_wstat32i64`|Non affecté par la définition de macro|32 bits|64 bits|  
|`_stat64i32`, `_wstat64i32`|Non affecté par la définition de macro|64 bits|32 bits|  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tstat`|`_stat`|`_stat`|`_wstat`|  
|`_tstat64`|`_stat64`|`_stat64`|`_wstat64`|  
|`_tstati64`|`_stati64`|`_stati64`|`_wstati64`|  
|`_tstat32i64`|`_stat32i64`|`_stat32i64`|`_wstat32i64`|  
|`_tstat64i32`|`_stat64i32`|`_stat64i32`|`_wstat64i32`|  
  
 La structure `_stat`, définie dans SYS\\STAT. H, contient les champs suivants.  
  
 `st_gid`  
 Identificateur numérique du groupe propriétaire du fichier \(propre à UNIX\). Ce champ est toujours zéro sur les systèmes Windows. Un fichier de redirection est classé comme un fichier Windows.  
  
 `st_atime`  
 Heure du dernier accès au fichier. Valide sur NTFS, mais pas sur les lecteurs de disque au format FAT.  
  
 `st_ctime`  
 Heure de création du fichier. Valide sur NTFS, mais pas sur les lecteurs de disque au format FAT.  
  
 `st_dev`  
 Numéro de lecteur du disque contenant le fichier \(identique à `st_rdev`\).  
  
 `st_ino`  
 Numéro du nœud d’informations \(le `inode`\) du fichier \(propre à UNIX\). Sur les systèmes de fichiers UNIX, le `inode` décrit la date et l’heure du fichier, les horodatages, les autorisations et le contenu. Lorsque les fichiers sont liés par des liens physiques, ils partagent le même `inode`. Le `inode`, et par conséquent `st_ino`, n’a aucune signification dans les systèmes de fichiers FAT, HPFS et NTFS.  
  
 `st_mode`  
 Masque de bits pour les informations relatives au mode de fichier. Le bit `_S_IFDIR` est défini si `path` spécifie un répertoire. Le bit `_S_IFREG` est défini si `path` spécifie un fichier ordinaire ou un périphérique. Les bits de lecture\/écriture utilisateur sont définis en fonction du mode d’autorisation du fichier. Les bits d’exécution utilisateur sont définis en fonction de l’extension de nom de fichier.  
  
 `st_mtime`  
 Heure de dernière modification du fichier.  
  
 `st_nlink`  
 Toujours 1 sur les systèmes de fichiers autres que NTFS.  
  
 `st_rdev`  
 Numéro de lecteur du disque contenant le fichier \(identique à `st_dev`\).  
  
 `st_size`  
 Taille du fichier en octets. Entier 64 bits pour les variantes avec le suffixe `i64`**.**  
  
 `st_uid`  
 Identificateur numérique de l’utilisateur propriétaire du fichier \(propre à UNIX\). Ce champ est toujours zéro sur les systèmes Windows. Un fichier de redirection est classé comme un fichier Windows.  
  
 Si `path` fait référence à un périphérique, le `st_size`, divers champs d’heure et les champs `st_dev` et `st_rdev` dans la structure `_stat` n’ont aucune signification. Étant donné que STAT.H utilise le type [\_dev\_t](../../c-runtime-library/standard-types.md) défini dans TYPES.H, vous devez inclure TYPES.H avant STAT.H dans votre code.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-têtes facultatifs|  
|-------------|---------------------|---------------------------|  
|`_stat`, `_stat32`, `_stat64`, `_stati64`, `_stat32i64`, `_stat64i32`|\<sys\/types.h\> suivi de \<sys\/stat.h\>|\<errno.h\>|  
|`_wstat`, `_wstat32`, `_wstat64`, `_wstati64`, `_wstat32i64`, `_wstat64i32`|\<sys\/types.h\> suivi de \<sys\/stat.h\> ou \<wchar.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_stat.c  
// This program uses the _stat function to  
// report information about the file named crt_stat.c.  
  
#include <time.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
   struct _stat buf;  
   int result;  
   char timebuf[26];  
   char* filename = "crt_stat.c";  
   errno_t err;  
  
   // Get data associated with "crt_stat.c":   
   result = _stat( filename, &buf );  
  
   // Check if statistics are valid:   
   if( result != 0 )  
   {  
      perror( "Problem getting information" );  
      switch (errno)  
      {  
         case ENOENT:  
           printf("File %s not found.\n", filename);  
           break;  
         case EINVAL:  
           printf("Invalid parameter to _stat.\n");  
           break;  
         default:  
           /* Should never be reached. */  
           printf("Unexpected error in _stat.\n");  
      }  
   }  
   else  
   {  
      // Output some of the statistics:   
      printf( "File size     : %ld\n", buf.st_size );  
      printf( "Drive         : %c:\n", buf.st_dev + 'A' );  
      err = ctime_s(timebuf, 26, &buf.st_mtime);  
      if (err)  
      {  
         printf("Invalid arguments to ctime_s.");  
         exit(1);  
      }  
      printf( "Time modified : %s", timebuf );  
   }  
}  
```  
  
```Output  
File size     : 732 Drive         : C: Time modified : Thu Feb 07 14:39:36 2002  
```  
  
## Équivalent .NET Framework  
  
-   [System::IO::File::GetAttributes](https://msdn.microsoft.com/en-us/library/system.io.file.getattributes.aspx)  
  
-   [System::IO::File::GetCreationTime](https://msdn.microsoft.com/en-us/library/system.io.file.getcreationtime.aspx)  
  
-   [System::IO::File::GetLastAccessTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastaccesstime.aspx)  
  
-   [System::IO::File::GetLastWriteTime](https://msdn.microsoft.com/en-us/library/system.io.file.getlastwritetime.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_access, \_waccess](../../c-runtime-library/reference/access-waccess.md)   
 [\_fstat, \_fstat32, \_fstat64, \_fstati64, \_fstat32i64, \_fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)