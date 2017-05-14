---
title: fseek, _fseeki64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fseeki64
- fseek
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
- fseek
- _fseeki64
dev_langs:
- C++
helpviewer_keywords:
- _fseeki64 function
- fseeki64 function
- fseek function
- file pointers [C++], moving
- file pointers [C++]
- seek file pointers
ms.assetid: f6bb1f8b-891c-426e-9e14-0e7e5c62df70
caps.latest.revision: 23
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
ms.openlocfilehash: 0d0c0bf620f1b89b9decceed3db9434dae4f9437
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="fseek-fseeki64"></a>fseek, _fseeki64
Déplace le pointeur de fichier vers un emplacement spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fseek(   
   FILE *stream,  
   long offset,  
   int origin   
);  
int _fseeki64(   
   FILE *stream,  
   __int64 offset,  
   int origin   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
 `offset`  
 Nombre d’octets à partir de `origin`.  
  
 `origin`  
 Position initiale.  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, `fseek` et `_fseeki64` retournent 0. Sinon, elles retournent une valeur différente de zéro. Sur les appareils incapables de rechercher, la valeur de retour n’est pas définie. Si `stream` est un pointeur Null ou que `origin` n’est pas une des valeurs autorisées décrites ci-dessous, `fseek` et `_fseeki64` appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` avec la valeur `EINVAL` et retournent -1.  
  
## <a name="remarks"></a>Remarques  
 Le `fseek` et `_fseeki64` déplace le pointeur de fichier (le cas échéant) associé à des fonctions `stream` vers un nouvel emplacement est `offset` octets à partir de `origin`. L’opération suivante sur le flux a lieu au nouvel emplacement. Sur un flux ouvert pour la mise à jour, l’opération suivante peut être une lecture ou une écriture. L’argument origin doit être une des constantes suivantes, définies dans STDIO.H :  
  
 `SEEK_CUR`  
 Position actuelle du pointeur de fichier.  
  
 `SEEK_END`  
 Fin du fichier.  
  
 `SEEK_SET`  
 Début du fichier.  
  
 Vous pouvez utiliser `fseek` et `_fseeki64` pour repositionner le pointeur n’importe où dans un fichier. Le pointeur peut également être positionné au-delà de la fin du fichier. `fseek`et `_fseeki64` efface l’indicateur de fin de fichier et annule l’effet du tout avant `ungetc` les appels de fonction `stream`.  
  
 Quand un fichier est ouvert pour un ajout de données, la position de fichier actuelle est déterminée par la dernière opération d’E/S, pas par l’emplacement auquel l’écriture suivante se produirait. Si aucune opération d’E/S ne s’est produite sur un fichier ouvert pour un ajout, la position de fichier correspond au début du fichier.  
  
 Pour les flux ouverts en mode texte, `fseek` et `_fseeki64` est limitée utilisation, comme des traductions chariot / sauts de ligne peuvent entraîner `fseek` et `_fseeki64` pour produire des résultats inattendus. La seule `fseek` et `_fseeki64` sont des opérations fonctionnent sur les flux ouverts en mode texte :  
  
-   Recherche avec un décalage de 0 par rapport à toute valeur d’origine.  
  
-   La recherche à partir du début du fichier avec une valeur de décalage retourné par un appel à `ftell` lors de l’utilisation `fseek` ou `_ftelli64` lors de l’utilisation `_fseeki64`.  
  
 Également en mode texte, Ctrl+Z est interprété comme un caractère de fin de fichier en entrée. Dans les fichiers ouverts en lecture/écriture, `fopen` et toutes les routines connexes recherchent un Ctrl+Z à la fin du fichier et le suppriment, si possible. En effet, l’utilisation de la combinaison des fonctions `fseek` et `ftell` ou `_fseeki64` et `_ftelli64` pour se déplacer dans un fichier qui se termine par un Ctrl+Z peut provoquer un comportement incorrect de `fseek` ou `_fseeki64` vers la fin du fichier.  
  
 Quand la bibliothèque CRT ouvre un fichier qui commence par une marque d’ordre d’octet, le pointeur de fichier est positionné après la marque (autrement dit, au début du contenu réel du fichier). Si vous devez effectuer une opération `fseek` vers le début du fichier, utilisez `ftell` pour obtenir la position initiale, puis effectuez une opération `fseek` vers cette position plutôt que vers la position 0.  
  
 Cette fonction verrouille les autres threads pendant l’exécution et est donc thread-safe. Pour une version sans verrouillage, consultez [_fseek_nolock, _fseeki64_nolock](../../c-runtime-library/reference/fseek-nolock-fseeki64-nolock.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fseek`|\<stdio.h>|  
|`_fseeki64`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_fseek.c  
// This program opens the file FSEEK.OUT and  
// moves the pointer to the file's beginning.  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char line[81];  
   int  result;  
  
   if ( fopen_s( &stream, "fseek.out", "w+" ) != 0 )  
   {  
      printf( "The file fseek.out was not opened\n" );  
      return -1;  
   }  
   fprintf( stream, "The fseek begins here: "  
                    "This is the file 'fseek.out'.\n" );  
   result = fseek( stream, 23L, SEEK_SET);  
   if( result )  
      perror( "Fseek failed" );  
   else  
   {  
      printf( "File pointer is set to middle of first line.\n" );  
      fgets( line, 80, stream );  
      printf( "%s", line );  
    }  
   fclose( stream );  
}  
```  
  
```Output  
File pointer is set to middle of first line.  
This is the file 'fseek.out'.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [ftell, _ftelli64](../../c-runtime-library/reference/ftell-ftelli64.md)   
 [_lseek, _lseeki64](../../c-runtime-library/reference/lseek-lseeki64.md)   
 [rewind](../../c-runtime-library/reference/rewind.md)
