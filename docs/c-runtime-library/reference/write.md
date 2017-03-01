---
title: _write | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _write
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
apitype: DLLExport
f1_keywords:
- _write
dev_langs:
- C++
helpviewer_keywords:
- _write function
- write function
- files [C++], writing to
ms.assetid: 7b868c33-766f-4e1a-95a7-e8d25f0604c4
caps.latest.revision: 21
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: d035a6b0941e7fa916e9306e5ef4f420d4e066d5
ms.lasthandoff: 02/24/2017

---
# <a name="write"></a>_write
Écrit des données dans un fichier.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _write(  
   int fd,  
   const void *buffer,  
   unsigned int count   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `fd`  
 Descripteur de fichier pour le fichier dans lequel les données sont écrites.  
  
 `buffer`  
 Données à écrire.  
  
 `count`  
 Nombre d'octets.  
  
## <a name="return-value"></a>Valeur de retour  
 S'il aboutit, `_write` retourne le nombre d'octets réellement écrits. Si l'espace effectif restant sur le disque est inférieur à la taille de la mémoire tampon que la fonction essaie d'écrire sur le disque, `_write` échoue et le contenu de la mémoire tampon n'est pas vidé sur le disque. Une valeur de retour égale à –1 indique une erreur. Si des paramètres non valides sont passés, cette fonction appelle le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, la fonction retourne -1 et `errno` prend l'une des trois valeurs suivantes : `EBADF`, qui signifie que le descripteur de fichier n'est pas valide ou que le fichier n'est pas ouvert en écriture ; `ENOSPC`, qui signifie que l'espace restant sur l'appareil est insuffisant pour l'opération ; ou `EINVAL`, qui signifie que `buffer` était un pointeur null ou qu'un nombre impair `count` d'octets a été passé pour écriture dans un fichier en mode Unicode.  
  
 Pour plus d’informations sur ces codes de retour et les autres, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 Si le fichier est ouvert en mode texte, chaque saut de ligne est remplacé par une paire retour chariot-saut de ligne dans la sortie. Le remplacement n'a pas de conséquence sur la valeur de retour.  
  
 Quand le fichier est ouvert en mode de traduction Unicode (par exemple si `fd` est ouvert en utilisant `_open` ou `_sopen` et un paramètre de mode qui inclut `_O_WTEXT`, `_O_U16TEXT` ou `_O_U8TEXT`, ou s’il est ouvert en utilisant `fopen` et un paramètre de mode qui inclut `ccs=UNICODE`, `ccs=UTF-16LE` ou `ccs=UTF-8`, ou si le mode est remplacé par un mode de traduction Unicode en utilisant `_setmode`), `buffer` est interprété comme un pointeur désignant un tableau de `wchar_t` qui contient des données **UTF-16**. Toute tentative d’écriture d’une quantité impaire d’octets dans ce mode provoque une erreur de validation de paramètre.  
  
## <a name="remarks"></a>Notes  
 La fonction `_write` écrit des octets `count` de `buffer` vers le fichier associé à `fd`. L'opération d'écriture commence à la position actuelle du pointeur de fichier (le cas échéant) associé au fichier donné. Si le fichier est ouvert pour ajout, l'opération commence à la fin actuelle du fichier. Après l'opération d'écriture, le pointeur de fichier est augmenté du nombre d'octets réellement écrits.  
  
 Quand l'écriture se produit dans des fichiers ouverts en mode texte, `_write` considère un caractère CTRL+Z comme la fin de fichier logique. Quand l'écriture vise un appareil, `_write` considère un caractère CTRL+Z dans la mémoire tampon comme un terminateur de sortie.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_write`|\<io.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt__write.c  
//   
// This program opens a file for output and uses _write to write  
// some bytes to the file.  
  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <errno.h>  
#include <share.h>  
  
char buffer[] = "This is a test of '_write' function";  
  
int main( void )  
{  
   int         fileHandle = 0;  
   unsigned    bytesWritten = 0;  
  
   if ( _sopen_s(&fileHandle, "write.o", _O_RDWR | _O_CREAT,  
                  _SH_DENYNO, _S_IREAD | _S_IWRITE) )  
      return -1;  
  
   if (( bytesWritten = _write( fileHandle, buffer, sizeof( buffer ))) == -1 )  
   {  
      switch(errno)  
      {  
         case EBADF:  
            perror("Bad file descriptor!");  
            break;  
         case ENOSPC:  
            perror("No space left on device!");  
            break;  
         case EINVAL:  
            perror("Invalid parameter: buffer was NULL!");  
            break;  
         default:  
            // An unrelated error occured   
            perror("Unexpected error!");  
      }  
   }  
   else  
   {  
      printf_s( "Wrote %u bytes to file.\n", bytesWritten );  
   }  
   _close( fileHandle );  
}  
```  
  
```Output  
Wrote 36 bytes to file.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de bas niveau](../../c-runtime-library/low-level-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_read](../../c-runtime-library/reference/read.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)
