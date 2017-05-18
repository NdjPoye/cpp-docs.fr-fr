---
title: _read | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _read
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
- _read
dev_langs:
- C++
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
caps.latest.revision: 15
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
ms.openlocfilehash: 6387edb05977f90fe9fb2419a1eccb47ac0b7b43
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="read"></a>_read
Lit les données d’un fichier.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      int _read(  
   int fd,  
   void *buffer,  
   unsigned int count   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `fd`  
 Descripteur de fichier faisant référence au fichier ouvert.  
  
 *buffer*  
 Emplacement de stockage des données.  
  
 *count*  
 Nombre maximal d’octets.  
  
## <a name="return-value"></a>Valeur de retour  
 _**lire** retourne le nombre d’octets lus, qui peut être inférieur à *nombre* s’il y a moins de *nombre* octets restant dans le fichier, ou si le fichier a été ouvert en mode texte, auquel cas chaque retour chariot-ligne flux paire (CR LF) est remplacé par un caractère de saut de ligne unique. Seul le caractère de saut de ligne unique est comptabilisé dans la valeur de retour. Le remplacement n’a pas de conséquence sur le pointeur de fichier.  
  
 Si la fonction tente de lire à la fin du fichier, elle retourne 0. Si `fd` n’est pas valide, le fichier n’est pas ouvert pour lecture, ou le fichier est verrouillé, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, la fonction retourne -1 et définit `errno` avec la valeur `EBADF`.  
  
 Si *buffer* a la valeur **NULL**, le gestionnaire de paramètre non valide est appelé. Si l’exécution est autorisée à se poursuivre, la fonction retourne -1 et `errno` prend la valeur `EINVAL`.  
  
 Pour plus d’informations sur ce code de retour et les autres codes, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_read` lit un maximum de *count* octets dans *buffer* à partir du fichier associé à `fd`. L’opération de lecture commence à la position actuelle du pointeur de fichier associé au fichier donné. À la fin de la l’opération de lecture, le pointeur de fichier pointe vers le caractère non lu suivant.  
  
 Si le fichier a été ouvert en mode texte, la lecture se termine quand `_read` rencontre un caractère CTRL+Z, qui est considéré comme un indicateur de fin de fichier. Utilisez [_lseek](../../c-runtime-library/reference/lseek-lseeki64.md) pour effacer l’indicateur de fin de fichier.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_read`|\<io.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_read.c  
/* This program opens a file named crt_read.txt  
 * and tries to read 60,000 bytes from  
 * that file using _read. It then displays the  
 * actual number of bytes read.  
 */  
  
#include <fcntl.h>      /* Needed only for _O_RDWR definition */  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
char buffer[60000];  
  
int main( void )  
{  
   int fh;  
   unsigned int nbytes = 60000, bytesread;  
  
   /* Open file for input: */  
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
   {  
      perror( "open failed on input file" );  
      exit( 1 );  
   }  
  
   /* Read in input: */  
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )  
      perror( "Problem reading file" );  
   else  
      printf( "Read %u bytes from file\n", bytesread );  
  
   _close( fh );  
}  
```  
  
## <a name="input-crtreadtxt"></a>Entrée : crt_read.txt  
  
```  
Line one.  
Line two.  
```  
  
## <a name="output"></a>Sortie  
  
```  
Read 19 bytes from file  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de bas niveau](../../c-runtime-library/low-level-i-o.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fread](../../c-runtime-library/reference/fread.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_write](../../c-runtime-library/reference/write.md)
