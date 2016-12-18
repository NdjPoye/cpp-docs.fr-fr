---
title: "remove, _wremove | Microsoft Docs"
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
  - "_wremove"
  - "remove"
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
  - "remove"
  - "_wremove"
  - "_tremove"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tremove (fonction)"
  - "_wremove (fonction)"
  - "fichiers (C++), supprimer"
  - "fichiers (C++), supprimer"
  - "remove (fonction)"
  - "tremove (fonction)"
  - "wremove (fonction)"
ms.assetid: b6345ec3-3289-4645-93a4-28b9e478cc19
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# remove, _wremove
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Supprimer un fichier.  
  
## Syntaxe  
  
```  
  
      int remove(  
   const char *path   
);  
int _wremove(  
   const wchar_t *path   
);  
```  
  
#### Paramètres  
 *path*  
 Chemin d'accès du fichier à changer.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne 0 si le fichier a été supprimé avec succès.  Sinon, retourne \-1 et affecte `errno` soit à `EACCES` pour indiquer que le chemin d'accès indique un fichier en lecture seule ou le fichier est ouvert, soit à **ENOENT** pour indiquer que le nom de fichier et le chemin d'accès est introuvable ou que le chemin d'accès spécifie un répertoire.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes de retour.  
  
## Notes  
 La fonction  **supprimer** supprime le fichier spécifié par le *chemin d'accès.* `_wremove` est une version de caractères larges de **\_remove**; l'argument *path* à `_wremove` est une chaîne de caractères larges.  Sinon, `_wremove` et  se comportent de la même façon.  Tous les descripteurs d'un fichier doivent être fermés avant de pouvoir le supprimer.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_tremove`|**remove**|**remove**|`_wremove`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|**remove**|\<stdio.h\> ou \<wchar.h\>|  
|`_wremove`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_remove.c  
/* This program uses remove to delete crt_remove.txt */  
  
#include <stdio.h>  
  
int main( void )  
{  
   if( remove( "crt_remove.txt" ) == -1 )  
      perror( "Could not delete 'CRT_REMOVE.TXT'" );  
   else  
      printf( "Deleted 'CRT_REMOVE.TXT'\n" );  
}  
```  
  
## Entrée : crt\_remove.txt  
  
```  
This file will be deleted.  
```  
  
## Résultat de l'exemple  
  
```  
Deleted 'CRT_REMOVE.TXT'  
```  
  
## Équivalent .NET Framework  
 [System::IO::File::Delete](https://msdn.microsoft.com/en-us/library/system.io.file.delete.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_unlink, \_wunlink](../../c-runtime-library/reference/unlink-wunlink.md)