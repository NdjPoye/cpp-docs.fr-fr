---
title: "_getcwd, _wgetcwd | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wgetcwd"
  - "_getcwd"
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
  - "api-ms-win-crt-environment-l1-1-0.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getcwd"
  - "wgetcwd"
  - "_wgetcwd"
  - "tgetcwd"
  - "_tgetcwd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "getcwd (fonction)"
  - "répertoire de travail"
  - "_wgetcwd (fonction)"
  - "_getcwd (fonction)"
  - "répertoire de travail en cours"
  - "wgetcwd (fonction)"
  - "utilisation de répertoires (C++), en cours"
ms.assetid: 888dc8c6-5595-4071-be55-816b38e3e739
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _getcwd, _wgetcwd
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient le répertoire de travail actuel.  
  
## Syntaxe  
  
```  
char *_getcwd(   
   char *buffer,  
   int maxlen   
);  
wchar_t *_wgetcwd(   
   wchar_t *buffer,  
   int maxlen   
);  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour le chemin.  
  
 `maxlen`  
 Longueur maximale du chemin en caractères : `char` pour `_getcwd` et `wchar_t` pour `_wgetcwd`.  
  
## Valeur de retour  
 Retourne un pointeur vers `buffer`. Une valeur de retour `NULL` indique une erreur et `errno` prend la valeur `ENOMEM`, ce qui indique que la mémoire est insuffisante pour allouer `maxlen` octets \(quand un argument `NULL` est donné comme `buffer`\), ou la valeur `ERANGE`, ce qui indique que le chemin d’accès fait plus de `maxlen` caractères. Si `maxlen` est inférieur ou égal à zéro, cette fonction appelle un gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Pour plus d’informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_getcwd` obtient le chemin complet du répertoire de travail actuel pour le lecteur spécifié et le stocke dans `buffer`. L’argument entier `maxlen` spécifie la longueur maximale du chemin. Une erreur se produit si la longueur du chemin \(y compris le caractère null de fin\) dépasse `maxlen`*.* L’argument `buffer` peut être `NULL` ; une mémoire tampon d’une taille d’au moins `maxlen` \(plus seulement si nécessaire\) est allouée automatiquement, en utilisant `malloc`, pour stocker le chemin. Cette mémoire tampon ultérieurement peut être libérée en appelant `free` et en lui passant la valeur de retour `_getcwd` \(un pointeur vers la mémoire tampon allouée\).  
  
 `_getcwd` retourne une chaîne qui représente le chemin du répertoire de travail actuel. Si le répertoire de travail actuel est la racine, la chaîne se termine par une barre oblique inverse \( `\` \). Si le répertoire de travail actuel est un répertoire autre que la racine, la chaîne se termine par le nom du répertoire, et non pas par une barre oblique inverse.  
  
 `_wgetcwd` est une version à caractères larges de `_getcwd` ; l’argument `buffer` et la valeur de retour de `_wgetcwd` sont des chaînes à caractères larges. Sinon, `_wgetcwd` et `_getcwd` se comportent de la même façon.  
  
 Quand `_DEBUG` et `_CRTDBG_MAP_ALLOC` sont définis, les appels à `_getcwd` et `_wgetcwd` sont remplacés par les appels à `_getcwd_dbg` et `_wgetcwd_dbg` pour permettre le débogage des allocations de mémoire. Pour plus d’informations, consultez [\_getcwd\_dbg, \_wgetcwd\_dbg](../../c-runtime-library/reference/getcwd-dbg-wgetcwd-dbg.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tgetcwd`|`_getcwd`|`_getcwd`|`_wgetcwd`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_getcwd`|\<direct.h\>|  
|`_wgetcwd`|\<direct.h\> ou \<wchar.h\>|  
  
 Pour plus d’informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_getcwd.c  
// This program places the name of the current directory in the   
// buffer array, then displays the name of the current directory   
// on the screen. Passing NULL as the buffer forces getcwd to allocate  
// memory for the path, which allows the code to support file paths  
// longer than _MAX_PATH, which are supported by NTFS.  
  
#include <direct.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char* buffer;  
  
   // Get the current working directory:   
   if( (buffer = _getcwd( NULL, 0 )) == NULL )  
      perror( "_getcwd error" );  
   else  
   {  
      printf( "%s \nLength: %d\n", buffer, strnlen(buffer) );  
      free(buffer);  
   }  
}  
```  
  
```Output  
C:\Code  
```  
  
## Équivalent .NET Framework  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [\_chdir, \_wchdir](../../c-runtime-library/reference/chdir-wchdir.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)