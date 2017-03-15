---
title: "_creat, _wcreat | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_creat"
  - "_wcreat"
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
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wcreat"
  - "_wcreat"
  - "_creat"
  - "tcreat"
  - "_tcreat"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "wcreat, fonction"
  - "_wcreat, fonction"
  - "fichiers [C++], créer"
  - "_creat, fonction"
  - "tcreat, fonction"
  - "creat, fonction"
  - "_tcreat, fonction"
ms.assetid: 3b3b795d-1620-40ec-bd2b-a4bbb0d20fe5
caps.latest.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 21
---
# _creat, _wcreat
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un fichier.  `_creat` et `_wcreat` ont été déconseillés ; utilisez [\_sopen\_s, \_wsopen\_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md) à la place.  
  
## Syntaxe  
  
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
  
#### Paramètres  
 `filename`  
 Nom du nouveau fichier.  
  
 `pmode`  
 Définition des autorisations  
  
## Valeur de retour  
 Ces fonctions, si exécutées avec succès, retournent un descripteur de fichier du fichier créé.  Sinon, les fonctions retournent – 1 et définissent `errno` comme indiqué dans le tableau suivant.  
  
|Paramètre `errno`|Description|  
|-----------------------|-----------------|  
|`EACCES`|`filename` spécifie un fichier en lecture seule existant ou spécifie un répertoire au lieu d'un fichier.|  
|`EMFILE`|Plus aucun fichier de descripteurs de fichiers ne sont disponibles.|  
|`ENOENT`|Le fichier spécifié est introuvable.|  
  
 Si `filename` est NULL, ces fonctions appellent le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent \-1.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_creat` crée un nouveau fichier ou ouvre et en tronque un existant.  `_wcreat` est une version à caractères larges de `_creat`; l'argument `filename` vers `_wcreat` est une chaîne à caractères larges.  `_wcreat` et `_creat` se comportent sinon de manière identique.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tcreat`|`_creat`|`_creat`|`_wcreat`|  
  
 Si le fichier spécifié par `filename` n'existe pas, un nouveau fichier est créé avec le paramètre d'autorisation spécifique et est ouvert pour l'écriture.  Si le fichier existe déjà et que son paramètre d'autorisation autorise l'écriture, `_creat` tronque le fichier à la longueur 0, détruisant le contenu précédent, puis l'ouvre en écriture.  Le paramètre d'autorisation, `pmode`, s'applique aux fichiers récemment créé uniquement.  Le fichier obtient le paramètre d'autorisations spécifié après qu'il a été fermé pour la première fois.  L'expression entière `pmode` contient une des deux ou les deux constantes manifestes suivantes `_S_IWRITE` and `_S_IREAD`, définies dans SYS\\Stat.h :  Lorsque les deux constantes sont fournies, elles sont jointes à l'opérateur de bits `OR` \(  **&#124;**\).  Le paramètre `pmode` est fixé à l'une des valeurs suivantes.  
  
|Valeur|Définition|  
|------------|----------------|  
|`_S_IWRITE`|Écriture autorisée.|  
|`_S_IREAD`|Lecture autorisée.|  
|`_S_IREAD &#124; _S_IWRITE`|Lecture et écriture autorisées.|  
  
 Si l'autorisation d'écriture n'est pas donnée, le fichier est en lecture seule.  Tous les fichiers peuvent toujours être lus ; il est impossible de donner une autorisation pour l'écriture seule.  Les modes `_S_IWRITE` et `_S_IREAD``| _S_IWRITE` sont donc équivalents.  Les fichiers ouverts en utilisant `_creat` sont toujouts ouverts dans le mode de compatibilité \(voir [\_sopen](../../c-runtime-library/reference/sopen-wsopen.md)\) avec `_SH_DENYNO`.  
  
 `_creat` applique le masque d'autorisation de fichier actuel à `pmode` avant de définir les autorisations \(voir [\_umask](../../c-runtime-library/reference/umask.md)\).  `_creat` est principalement fournis à des fins de compatibilité avec les bibliothèques précédentes.  Un appel à `_open` avec `_O_CREAT` et `_O_TRUNC` dans le paramètre `oflag` équivaut à `_creat` et est préférable pour un nouveau code.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_creat`|\<io.h,\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
|`_wcreat`|\<io.h\> ou \<wchar.h\>|\<sys\/types.h\>, \<sys\/stat.h\>, \<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
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
  
  **Fichier de données créé.**   
## Voir aussi  
 [E\/S niveau bas](../../c-runtime-library/low-level-i-o.md)   
 [\_chmod, \_wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [\_chsize](../../c-runtime-library/reference/chsize.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_dup, \_dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_sopen, \_wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [\_umask](../../c-runtime-library/reference/umask.md)