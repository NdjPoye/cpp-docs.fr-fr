---
title: fgetpos | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fgetpos
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
- fgetpos
dev_langs:
- C++
helpviewer_keywords:
- fgetpos function
- streams, file position indicator
ms.assetid: bfa05c38-1135-418c-bda1-d41be51acb62
caps.latest.revision: 14
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: c53e5742a518934ad0afcfaa06ad4e5905c484e3
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="fgetpos"></a>fgetpos
Obtient l’indicateur de position de fichier d’un flux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fgetpos(   
   FILE *stream,  
   fpos_t *pos   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Flux cible.  
  
 `pos`  
 Stockage de l’indicateur de position.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, `fgetpos` retourne 0. En cas d’échec, elle retourne une valeur différente de zéro et définit `errno` sur une des constantes manifestes suivantes (définies dans STDIO.H) : `EBADF` (le flux spécifié n’est pas un pointeur de fichier valide ou n’est pas accessible) ou `EINVAL` (la valeur `stream` ou la valeur de `pos` n’est pas valide, par exemple, un pointeur null). Si `stream` ou `pos` est un pointeur `NULL`, la fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `fgetpos` obtient la valeur actuelle de l’indicateur de position de fichier de l’argument `stream` et la stocke dans l’objet désigné par `pos`. La fonction `fsetpos` peut utiliser ultérieurement les informations stockées dans `pos` pour réinitialiser le pointeur de l’argument `stream` à la position qu’il occupait au moment de l’appel à `fgetpos`. La valeur `pos` est stockée dans un format interne en vue d’une utilisation par `fgetpos` et `fsetpos` uniquement.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fgetpos`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_fgetpos.c  
// This program uses fgetpos and fsetpos to  
// return to a location in a file.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE   *stream;  
   fpos_t pos;  
   char   buffer[20];  
  
   if( fopen_s( &stream, "crt_fgetpos.txt", "rb" ) ) {  
      perror( "Trouble opening file" );  
      return -1;  
   }  
  
   // Read some data and then save the position.   
   fread( buffer, sizeof( char ), 8, stream );  
   if( fgetpos( stream, &pos ) != 0 ) {  
      perror( "fgetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fgetpos: %.13s\n", buffer );  
  
   // Restore to old position and read data   
   if( fsetpos( stream, &pos ) != 0 ) {  
      perror( "fsetpos error" );  
      return -1;  
   }  
  
   fread( buffer, sizeof( char ), 13, stream );  
   printf( "after fsetpos: %.13s\n", buffer );  
   fclose( stream );  
}  
```  
  
## <a name="input-crtfgetpostxt"></a>Entrée : crt_fgetpos.txt  
  
```  
fgetpos gets a stream's file-position indicator.  
```  
  
### <a name="output-crtfgetpostxt"></a>Sortie : crt_fgetpos.txt  
  
```  
after fgetpos: gets a stream  
after fsetpos: gets a stream  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fsetpos](../../c-runtime-library/reference/fsetpos.md)
