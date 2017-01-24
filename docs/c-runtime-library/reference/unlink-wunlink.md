---
title: "_unlink, _wunlink | Microsoft Docs"
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
  - "_unlink"
  - "_wunlink"
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
  - "_tunlink"
  - "_unlink"
  - "wunlink"
  - "_wunlink"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tunlink (fonction)"
  - "_unlink (fonction)"
  - "_wunlink (fonction)"
  - "fichiers (C++), supprimer"
  - "fichiers (C++), supprimer"
  - "tunlink (fonction)"
  - "unlink (fonction)"
  - "wunlink (fonction)"
ms.assetid: 5e4f5f1b-1e99-4391-9b18-9ac63c32fae8
caps.latest.revision: 12
caps.handback.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _unlink, _wunlink
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Supprimer un fichier.  
  
## Syntaxe  
  
```  
int _unlink(  
   const char *filename   
);  
int _wunlink(  
   const wchar_t *filename   
);  
```  
  
#### Paramètres  
 `filename`  
 Nom du fichier à enlever.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne 0 en cas de succès.  Sinon, la fonction retourne – 1 et affecte `errno` à `EACCES`, ce qui signifie que le chemin d'accès indique un fichier en lecture seule, ou à `ENOENT`, c'est\-à\-dire que le fichier ou le chemin d'accès est introuvable ou que le chemin d'accès spécifié un répertoire.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes de retour.  
  
## Notes  
 La fonction `_unlink` supprime le fichier spécifié par `filename`.  `_wunlink` est une version à caractères larges de `_unlink`; l'argument `filename` vers `_wunlink` est une chaîne à caractères larges.  Ces fonctions se comportent sinon de façon identique.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tunlink`|`_unlink`|`_unlink`|`_wunlink`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_unlink`|\<io.h\> et \<stdio.h\>|  
|`_wunlink`|\<io.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple de code  
 Ce programme utilise le \_unlink pour supprimer CRT\_UNLINK.TXT.  
  
```  
// crt_unlink.c  
  
#include <stdio.h>  
  
int main( void )  
{  
   if( _unlink( "crt_unlink.txt" ) == -1 )  
      perror( "Could not delete 'CRT_UNLINK.TXT'" );  
   else  
      printf( "Deleted 'CRT_UNLINK.TXT'\n" );  
}  
```  
  
### Entrée : crt\_unlink.txt  
  
```  
This file will be deleted.  
```  
  
### Résultat de l'exemple  
  
```  
Deleted 'CRT_UNLINK.TXT'  
```  
  
## Équivalent .NET Framework  
 [System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [remove, \_wremove](../../c-runtime-library/reference/remove-wremove.md)