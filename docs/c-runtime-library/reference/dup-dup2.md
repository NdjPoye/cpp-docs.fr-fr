---
title: _dup, _dup2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _dup
- _dup2
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _dup2
- _dup
dev_langs:
- C++
helpviewer_keywords:
- _dup2 function
- dup function
- file handles [C++], duplicating
- file handles [C++], reassigning
- dup2 function
- _dup function
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
caps.latest.revision: 19
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: a85a26fbe7ab8417ea9ecd3c43745789117ac856
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="dup-dup2"></a>_dup, _dup2
Crée un second descripteur de fichier pour un fichier ouvert (`_dup`), ou réaffecte un descripteur de fichier (`_dup2`).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _dup(   
   int fd   
);  
int _dup2(   
   int fd1,  
   int fd2   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `fd`, `fd1`  
 Descripteurs de fichier qui font référence à un fichier ouvert.  
  
 `fd2`  
 Un descripteur de fichier.  
  
## <a name="return-value"></a>Valeur de retour  
 `_dup` retourne un nouveau descripteur de fichier. `_dup2` retourne la valeur 0 en cas de réussite. Si une erreur se produit, chaque fonction retourne -1 et les jeux de `errno` à `EBADF` si le descripteur de fichier n’est pas valide ou à `EMFILE` si plus aucun descripteur de fichier n’est disponibles. En cas de descripteur de fichier non valide, la fonction appelle également le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Pour plus d’informations sur ces codes de retour et autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 Les fonctions `_dup` et `_dup2` associent un second descripteur de fichier à un fichier ouvert. Ces fonctions peuvent être utilisées pour associer un descripteur de fichier prédéfini, par exemple celui pour `stdout`, à un autre fichier. Les opérations sur le fichier peuvent être effectuées à l’aide de l’un des descripteurs de fichier. Le type d’accès autorisé pour le fichier n’est pas affecté par la création d’un descripteur. `_dup` retourne le descripteur de fichier disponible suivant pour le fichier donné. `_dup2` force `fd2` à faire référence au même fichier que `fd1`. Si `fd2` est associé à un fichier ouvert au moment de l’appel, ce fichier est fermé.  
  
 `_dup` et `_dup2` acceptent des descripteurs de fichiers en tant que paramètres. Pour passer un flux `(FILE *)` à une de ces fonctions, utilisez [_fileno](../../c-runtime-library/reference/fileno.md). La routine `fileno` retourne le descripteur de fichier associé au flux donné. L’exemple suivant montre comment associer `stderr` (défini en tant que `FILE` `*` dans Stdio.h) à un descripteur de fichier :  
  
```  
int cstderr = _dup( _fileno( stderr ));  
```  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_dup`|\<io.h>|  
|`_dup2`|\<io.h>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] . Les handles de flux standard associés à la console (`stdin`, `stdout` et `stderr`) doivent être redirigés pour que les fonctions Runtime C puissent les utiliser dans les applications du [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
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
  
```Output  
This goes to stdout first  
This goes to stdout  
  
The file 'data' contains:  
This goes to file 'data'  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de bas niveau](../../c-runtime-library/low-level-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
