---
title: fread_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fread_s
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
- fread_s
- stdio/fread_s
dev_langs:
- C++
ms.assetid: ce735de0-f005-435d-a8f2-6f4b80ac775e
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 6fa9d496bdb5f5d7b4dd4a772778a0f62a484fd8
ms.contentlocale: fr-fr
ms.lasthandoff: 04/01/2017

---
# <a name="freads"></a>fread_s
Lit les données d’un flux. Cette version de [fread](../../c-runtime-library/reference/fread.md) est assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t fread_s(   
   void *buffer,  
   size_t bufferSize,  
   size_t elementSize,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `buffer`  
 Emplacement de stockage des données.  
  
 `bufferSize`  
 Taille de la mémoire tampon de destination en octets.  
  
 `elementSize`  
 Taille de l’élément à lire en octets.  
  
 `count`  
 Nombre maximal d’éléments à lire.  
  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
## <a name="return-value"></a>Valeur de retour  
 `fread_s` retourne le nombre d’éléments (entiers) qui ont été lus dans la mémoire tampon ; ce nombre peut être inférieur à `count` si une erreur de lecture ou la fin du fichier est rencontrée avant que `count` ne soit atteint. Utilisez la fonction `feof` ou `ferror` pour distinguer une erreur d’une condition de fin de fichier. Si `size` ou `count` a la valeur 0, `fread_s` retourne 0 et le contenu de la mémoire tampon n’est pas modifié. Si `stream` ou `buffer` est un pointeur null, `fread_s` appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte à `errno` la valeur `EINVAL` et retourne 0.  
  
 Pour plus d’informations sur les codes d’erreur, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `fread_s` lit jusqu’à `count` éléments de `elementSize` octets à partir de l’entrée `stream` et les stocke dans `buffer`.  Le pointeur de fichier qui est associé à `stream` (le cas échéant) est augmenté du nombre d’octets réellement lus. Si le flux donné est ouvert en mode texte, paires de sauts de ligne de chariot sont remplacées par les caractères de saut de ligne unique. Le remplacement n’a aucun effet sur le pointeur de fichier ou la valeur de retour. La position du pointeur de fichier est indéterminée si une erreur se produit. La valeur d’un élément partiellement lu ne peut pas être déterminée.  
  
 Cette fonction verrouille les autres threads. Si vous avez besoin d’une version sans verrouillage, utilisez `_fread_nolock`.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fread_s`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, voir consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```cpp  
// crt_fread_s.c  
// Command line: cl /EHsc /nologo /W4 crt_fread_s.c  
//  
// This program opens a file that's named FREAD.OUT and  
// writes characters to the file. It then tries to open  
// FREAD.OUT and read in characters by using fread_s. If the attempt succeeds,  
// the program displays the number of actual items read.  
  
#include <stdio.h>  
  
#define BUFFERSIZE 30  
#define DATASIZE 22  
#define ELEMENTCOUNT 2  
#define ELEMENTSIZE (DATASIZE/ELEMENTCOUNT)  
#define FILENAME "FREAD.OUT"  
  
int main( void )  
{  
   FILE *stream;  
   char list[30];  
   int  i, numread, numwritten;  
  
   for ( i = 0; i < DATASIZE; i++ )  
      list[i] = (char)('z' - i);  
   list[DATASIZE] = '\0'; // terminal null so we can print it  
  
   // Open file in text mode:  
   if( fopen_s( &stream, FILENAME, "w+t" ) == 0 )  
   {  
      // Write DATASIZE characters to stream   
      printf( "Contents of buffer before write/read:\n\t%s\n\n", list );  
      numwritten = fwrite( list, sizeof( char ), DATASIZE, stream );  
      printf( "Wrote %d items\n\n", numwritten );  
      fclose( stream );  
   } else {  
      printf( "Problem opening the file\n" );  
      return -1;  
   }  
  
   if( fopen_s( &stream, FILENAME, "r+t" ) == 0 )   {  
      // Attempt to read in characters in 2 blocks of 11  
      numread = fread_s( list, BUFFERSIZE, ELEMENTSIZE, ELEMENTCOUNT, stream );  
      printf( "Number of %d-byte elements read = %d\n\n", ELEMENTSIZE, numread );  
      printf( "Contents of buffer after write/read:\n\t%s\n", list );  
      fclose( stream );  
   } else {  
      printf( "File could not be opened\n" );  
      return -1;  
   }  
}  
```  
  
```Output  
Contents of buffer before write/read:   
        zyxwvutsrqponmlkjihgfe  
  
Wrote 22 items  
  
Number of 11-byte elements read = 2  
  
Contents of buffer after write/read:   
        zyxwvutsrqponmlkjihgfe  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [_read](../../c-runtime-library/reference/read.md)
