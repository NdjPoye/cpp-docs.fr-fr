---
title: ftell, _ftelli64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ftelli64
- ftell
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
- _ftelli64
- ftell
dev_langs:
- C++
helpviewer_keywords:
- ftell function
- ftelli64 function
- _ftelli64 function
- file pointers [C++], getting current position
- file pointers [C++]
ms.assetid: 40149cd8-65f2-42ff-b70c-68e3e918cdd7
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 220b34e5bba7a4a6716d6ef18d6621b58d36ecc3
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="ftell-ftelli64"></a>ftell, _ftelli64
Obtient la position actuelle d’un pointeur de fichier.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
long ftell(   
   FILE *stream   
);  
__int64 _ftelli64(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Structure `FILE` cible.  
  
## <a name="return-value"></a>Valeur de retour  
 `ftell` et `_ftelli64` retournent la position de fichier actuelle. La valeur retournée par `ftell` et `_ftelli64` peuvent ne pas refléter le décalage d’octet physique pour les flux ouverts en mode texte, car le mode texte provoque la traduction des sauts de ligne de transport. Utilisez `ftell` avec `fseek` ou `_ftelli64` avec `_fseeki64` vers les emplacements de fichier correctement. En cas d’erreur, `ftell` et `_ftelli64` appellent le Gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, ces fonctions retournent-1 L et le jeu de `errno` à une des deux constantes, définis dans ERRNO. H. La constante `EBADF` signifie que l’argument `stream` n’est pas une valeur de pointeur de fichier valide ou ne fait pas référence à un fichier ouvert. `EINVAL` signifie qu’un argument `stream` non valide a été passé à la fonction. Sur les appareils sans fonctionnalités de recherche (tels que les terminaux et les imprimantes) ou quand `stream` ne fait pas référence à un fichier ouvert, la valeur de retour n’est pas définie.  
  
 Pour plus d’informations sur ces codes de retour et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Remarques  
 Le `ftell` et `_ftelli64` fonctions de récupérer la position actuelle du pointeur de fichier (le cas échéant) associée à `stream`. La position est exprimée sous la forme d’un décalage par rapport au début du flux.  
  
 Notez que quand un fichier est ouvert pour un ajout de données, la position de fichier actuelle est déterminée par la dernière opération d’E/S, pas par l’emplacement auquel l’écriture suivante se produirait. Par exemple, si un fichier est ouvert pour un ajout et que la dernière opération était une lecture, la position de fichier est le point où l’opération de lecture suivante commencerait, pas celui où l’écriture suivante démarrerait. (Quand un fichier est ouvert pour un ajout, la position de fichier est déplacée vers la fin du fichier avant toute opération d’écriture.) Si aucune opération d’E/S ne s’est produite sur un fichier ouvert pour un ajout, la position de fichier correspond au début du fichier.  
  
 En mode texte, Ctrl+Z est interprété comme un caractère de fin de fichier en entrée. Dans les fichiers ouverts en lecture/écriture, `fopen` et toutes les routines connexes recherchent un Ctrl+Z à la fin du fichier et le suppriment, si possible. En effet, l’utilisation de la combinaison des fonctions `ftell` et `fseek` ou `_ftelli64` et `_fseeki64` pour se déplacer dans un fichier qui se termine par un Ctrl+Z peut provoquer un comportement incorrect de `ftell` ou `_ftelli64` vers la fin du fichier.  
  
 Cette fonction verrouille le thread appelant pendant l’exécution et est donc thread-safe. Pour une version sans verrouillage, voir `_ftell_nolock`.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|En-têtes facultatifs|  
|--------------|---------------------|----------------------|  
|`ftell`|\<stdio.h>|\<errno.h>|  
|`_ftelli64`|\<stdio.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_ftell.c  
// This program opens a file named CRT_FTELL.C  
// for reading and tries to read 100 characters. It  
// then uses ftell to determine the position of the  
// file pointer and displays this position.  
  
#include <stdio.h>  
  
FILE *stream;  
  
int main( void )  
{  
   long position;  
   char list[100];  
   if( fopen_s( &stream, "crt_ftell.c", "rb" ) == 0 )  
   {  
      // Move the pointer by reading data:   
      fread( list, sizeof( char ), 100, stream );  
      // Get position after read:   
      position = ftell( stream );  
      printf( "Position after trying to read 100 bytes: %ld\n",  
              position );  
      fclose( stream );  
   }  
}  
```  
  
```Output  
Position after trying to read 100 bytes: 100  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fgetpos](../../c-runtime-library/reference/fgetpos.md)   
 [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [_lseek, _lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)
