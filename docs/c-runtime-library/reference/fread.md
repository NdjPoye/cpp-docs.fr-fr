---
title: fread | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- fread
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
- fread
dev_langs:
- C++
helpviewer_keywords:
- reading data [C++], from input streams
- fread function
- data [C++], reading from input stream
- streams [C++], reading data from
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: d01c3362c94b0c644cb53aec6e45ce83b98dbf07
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="fread"></a>fread
Lit les données d’un flux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t fread(   
   void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `buffer`  
 Emplacement de stockage des données.  
  
 `size`  
 Taille de l’élément en octets.  
  
 `count`  
 Nombre maximal d’éléments à lire.  
  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
## <a name="return-value"></a>Valeur de retour  
 `fread` Retourne le nombre d’éléments complets réellement lu, ce qui peut être inférieur à `count` si une erreur se produit ou si la fin du fichier se trouve avant d’atteindre `count`. Utilisez la fonction `feof` ou `ferror` pour distinguer une erreur de lecture d’une condition de fin de fichier. Si `size` ou `count` a la valeur 0, `fread` retourne 0 et le contenu de la mémoire tampon n’est pas modifié. Si `stream` ou `buffer` est un pointeur null, `fread` appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte à `errno` la valeur `EINVAL` et retourne 0.  
  
 Pour plus d’informations sur ces codes d’erreur et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `fread` lit jusqu’à `count` éléments de `size` octets à partir de l’entrée `stream` et les stocke dans `buffer`. Le pointeur de fichier associé à `stream` (le cas échéant) est augmenté du nombre d’octets réellement lus. Si le flux donné est ouvert en mode texte, paires de sauts de ligne de chariot sont remplacées par les caractères de saut de ligne unique. Le remplacement n’a aucun effet sur le pointeur de fichier ou la valeur de retour. La position du pointeur de fichier est indéterminée si une erreur se produit. La valeur d’un élément partiellement lu ne peut pas être déterminée.  
  
 Cette fonction verrouille les autres threads. Si vous avez besoin d’une version sans verrouillage, utilisez `_fread_nolock`.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fread`|\<stdio.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_fread.c  
// This program opens a file named FREAD.OUT and  
// writes 25 characters to the file. It then tries to open  
// FREAD.OUT and read in 25 characters. If the attempt succeeds,  
// the program displays the number of actual items read.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char list[30];  
   int  i, numread, numwritten;  
  
   // Open file in text mode:  
   if( fopen_s( &stream, "fread.out", "w+t" ) == 0 )  
   {  
      for ( i = 0; i < 25; i++ )  
         list[i] = (char)('z' - i);  
      // Write 25 characters to stream   
      numwritten = fwrite( list, sizeof( char ), 25, stream );  
      printf( "Wrote %d items\n", numwritten );  
      fclose( stream );  
  
   }  
   else  
      printf( "Problem opening the file\n" );  
  
   if( fopen_s( &stream, "fread.out", "r+t" ) == 0 )  
   {  
      // Attempt to read in 25 characters   
      numread = fread( list, sizeof( char ), 25, stream );  
      printf( "Number of items read = %d\n", numread );  
      printf( "Contents of buffer = %.25s\n", list );  
      fclose( stream );  
   }  
   else  
      printf( "File could not be opened\n" );  
}  
```  
  
```Output  
Wrote 25 items  
Number of items read = 25  
Contents of buffer = zyxwvutsrqponmlkjihgfedcb  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [_read](../../c-runtime-library/reference/read.md)