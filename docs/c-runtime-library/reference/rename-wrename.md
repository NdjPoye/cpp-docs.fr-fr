---
title: "rename, _wrename | Microsoft Docs"
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
  - "rename"
  - "_wrename"
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
  - "_wrename"
  - "_trename"
  - "Rename"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_trename (fonction)"
  - "_wrename (fonction)"
  - "répertoires (C++), renommer"
  - "fichiers (C++), renommer"
  - "noms (C++), changer de répertoire"
  - "noms (C++), changer de fichier"
  - "fonction de changement de nom"
  - "renommer les répertoires"
  - "renommer des fichiers"
  - "trename (fonction)"
  - "wrename (fonction)"
ms.assetid: 9f0a6103-26a2-4dda-b14b-79a48946266a
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rename, _wrename
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Renommer un fichier ou un répertoire.  
  
## Syntaxe  
  
```  
  
      int rename(  
   const char *oldname,  
   const char *newname   
);  
int _wrename(  
   const wchar_t *oldname,  
   const wchar_t *newname   
);  
```  
  
#### Paramètres  
 *oldname*  
 Pointeur vers l'ancien nom.  
  
 *newname*  
 Pointeur vers le nouveau nom.  
  
## Valeur de retour  
 Chacune de ces fonctions retourne 0 en cas de succès.  Sur une erreur, la fonction retourne une valeur différente de zéro et définit `errno` à l'une des valeurs suivantes :  
  
 `EACCES`  
 Le fichier ou le répertoire spécifié par *newname* existe déjà ou n'a pas pu être créé \(chemin d'accès non valide\) ; ou *oldname* est un répertoire et le *newname* spécifie un chemin différent.  
  
 `ENOENT`  
 Fichier ou chemin d'accès spécifié par *oldname* introuvable.  
  
 `EINVAL`  
 Nom contient des caractères non valides.  
  
 Pour d'autres valeurs de retour possibles, consultez [\_doserrno, \_errno, syserrlist, et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction **renommer** renomme le fichier ou le répertoire spécifié par *oldname* avec le nom fourni par *newname*.  L'ancien nom doit correspondre au chemin d'accès d'un fichier existant ou d'un répertoire.  Le nouveau nom ne doit pas être le nom d'un fichier existant ou d'un répertoire.  Vous pouvez utiliser **renommer** pour déplacer un fichier à partir d'un répertoire ou d'un périphérique à l'autre en donnant un chemin différent dans l'argument *de newname*.  Toutefois, vous ne pouvez pas utiliser **renommer** pour déplacer un répertoire.  Les répertoires peuvent être renommés, mais pas être déplacés.  
  
 `_wrename` est une version à caractères larges de **\_rename**; les arguments de `_wrename` sont des chaînes à caractères larges.  Sinon, `_wrename` et **\_rename** se comportent de la même façon.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_trename`|**renommer**|**renommer**|`_wrename`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|**renommer**|\<io.h\> or \<stdio.h\>|  
|`_wrename`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_renamer.c  
/* This program attempts to rename a file named  
 * CRT_RENAMER.OBJ to CRT_RENAMER.JBO. For this operation  
 * to succeed, a file named CRT_RENAMER.OBJ must exist and  
 * a file named CRT_RENAMER.JBO must not exist.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   int  result;  
   char old[] = "CRT_RENAMER.OBJ", new[] = "CRT_RENAMER.JBO";  
  
   /* Attempt to rename file: */  
   result = rename( old, new );  
   if( result != 0 )  
      printf( "Could not rename '%s'\n", old );  
   else  
      printf( "File '%s' renamed to '%s'\n", old, new );  
}  
```  
  
## Sortie  
  
```  
File 'CRT_RENAMER.OBJ' renamed to 'CRT_RENAMER.JBO'  
```  
  
## Équivalent .NET Framework  
 [System.IO.File::Move](https://msdn.microsoft.com/en-us/library/system.io.file.move.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)