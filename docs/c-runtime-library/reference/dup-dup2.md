---
title: "_dup, _dup2 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_dup"
  - "_dup2"
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
  - "_dup2"
  - "_dup"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_dup (fonction)"
  - "_dup2 (fonction)"
  - "dup (fonction)"
  - "dup2 (fonction)"
  - "handles de fichiers (C++), dupliquer"
  - "handles de fichiers (C++), réassigner"
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _dup, _dup2
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un deuxième descripteur de fichier pour un fichier ouvert \(`_dup`\), ou réaffecte un descripteur de fichier \(`_dup2`\).  
  
## Syntaxe  
  
```  
int _dup(   
   int fd   
);  
int _dup2(   
   int fd1,  
   int fd2   
);  
```  
  
#### Paramètres  
 `fd`, `fd1`  
 Descripteurs de fichier faisant référence au fichier ouvert.  
  
 `fd2`  
 Tout descripteur de fichier.  
  
## Valeur de retour  
 `_dup` retourne un descripteur de fichier.  `_dup2` retourne 0 pour indiquer le succès.  Si une erreur se produit, chaque fonction retourne – 1 et affecte à `errno` la valeur `EBADF` si le descripteur de fichier est invalide ou la valeur `EMFILE` si aucun descripteur de fichier n'est disponible.  Dans le cas d'un descripteur de fichier invalide, la fonction appelle également le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 Les fonctions `_dup` et `_dup2` associent un deuxième descripteur de fichier avec un fichier ouvert à l'heure actuelle.  Ces fonctions peuvent être utilisées pour associer un descripteur de fichier prédéfini, tels que ceux pour `stdout`, avec un autre fichier.  Les opérations sur le fichier peuvent être exécutées à l'aide de l'un ou l'autre des descripteurs de fichier.  Le type d'accès autorisé pour le fichier n'est pas affecté par la création d'un nouveau descripteur.  `_dup` retourne le descripteur de fichier disponible suivant pour le fichier donné.  `_dup2` forces `fd2` font référence au même fichier que `fd1`.  Si `fd2` est associé à un fichier ouvert au moment de l'appel, ce fichier est fermé.  
  
 `_dup` et `_dup2` acceptent tous les deux des descripteurs de fichier comme paramètres.  Pour passer un flux `(FILE *)` à l'une ou l'autre de ces fonctions, utilisez [\_fileno](../../c-runtime-library/reference/fileno.md).  La routine `fileno` retourne le descripteur de fichier actuellement associé au flux donné.  L'exemple suivant indique comment associer `stderr` \(défini comme `FILE` `*` dans Stdio.h\) avec un descripteur de fichier :  
  
```  
int cstderr = _dup( _fileno( stderr ));  
```  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_dup`|\<io.h,\>|  
|`_dup2`|\<io.h,\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_dup.c  
// This program uses the variable old to save  
// the original stdout. It then opens a new file named  
// DataFile and forces stdout to refer to it. Finally, it  
// restores stdout to its original state.  
//  
  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int old;  
   FILE *DataFile;  
  
   old = _dup( 1 );   // "old" now refers to "stdout"   
                      // Note:  file descriptor 1 == "stdout"   
   if( old == -1 )  
   {  
      perror( "_dup( 1 ) failure" );  
      exit( 1 );  
   }  
   _write( old, "This goes to stdout first\n", 26 );  
   if( fopen_s( &DataFile, "data", "w" ) != 0 )  
   {  
      puts( "Can't open file 'data'\n" );  
      exit( 1 );  
   }  
  
   // stdout now refers to file "data"   
   if( -1 == _dup2( _fileno( DataFile ), 1 ) )  
   {  
      perror( "Can't _dup2 stdout" );  
      exit( 1 );  
   }  
   puts( "This goes to file 'data'\n" );  
  
   // Flush stdout stream buffer so it goes to correct file   
   fflush( stdout );  
   fclose( DataFile );  
  
   // Restore original stdout   
   _dup2( old, 1 );  
   puts( "This goes to stdout\n" );  
   puts( "The file 'data' contains:" );  
   _flushall();  
   system( "type data" );  
}  
```  
  
  **Cela va dans stdout d'abord**  
**Cela va dans stdout**  
**Les fichier "data" contient :**  
**Cela va dans le fichier "data"**   
## Voir aussi  
 [E\/S niveau bas](../../c-runtime-library/low-level-i-o.md)   
 [\_close](../../c-runtime-library/reference/close.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)