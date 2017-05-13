---
title: fflush | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- fflush
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
- fflush
dev_langs:
- C++
helpviewer_keywords:
- streams, flushing
- flushing
- fflush function
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
caps.latest.revision: 18
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
ms.openlocfilehash: f2a11a29ba0eec3c66cf23f72e8fe0e7106d5a5c
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="fflush"></a>fflush
Vide un flux.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int fflush(   
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `stream`  
 Pointeur vers la structure `FILE` .  
  
## <a name="return-value"></a>Valeur de retour  
 `fflush` retourne 0 si la mémoire tampon a été vidée correctement. La valeur 0 est également retournée si le flux spécifié n’a aucune mémoire tampon ou est ouvert en lecture seule. Une valeur de retour égale à `EOF` indique une erreur.  
  
> [!NOTE]
>  Si `fflush` retourne `EOF`, des données ont peut-être été perdues en raison d’un échec d’écriture. Quand vous configurez un gestionnaire d’erreurs critiques, la procédure la plus sûre consiste à désactiver la mise en mémoire tampon avec la fonction `setvbuf` ou à utiliser des routines E/S de bas niveau comme `_open`, `_close` et `_write` au lieu de fonctions d’E/S de flux.  
  
## <a name="remarks"></a>Notes  
 La fonction `fflush` vide le flux `stream`. Si le flux a été ouvert en mode d’écriture ou qu’il a été ouvert en mode de mise à jour et que la dernière opération était une écriture, le contenu de la mémoire tampon du flux est écrit dans le fichier ou périphérique sous-jacent et la mémoire tampon est abandonnée. Si le flux a été ouvert en mode de lecture ou qu’il n’a pas de mémoire tampon, l’appel à `fflush` n’a aucun effet, et aucune mémoire tampon n’est conservée. Un appel à `fflush` annule l’effet d’un appel antérieur à `ungetc` pour le flux. Le flux reste ouvert après l’appel.  
  
 Si `stream` est `NULL`, le comportement est identique à un appel à `fflush` sur chaque flux ouvert. Tous les flux ouverts en mode d’écriture et tous les flux ouverts en mode de mise à jour où la dernière opération était une écriture sont vidés. L’appel n’a aucun effet sur les autres flux.  
  
 Les mémoires tampons sont normalement gérées par le système d’exploitation, qui détermine à quel moment les données doivent être automatiquement écrites sur le disque : quand une mémoire tampon est saturée, quand un flux est fermé ou quand un programme se termine normalement sans fermer le flux. La fonctionnalité de validation sur disque de la bibliothèque runtime garantit que les données critiques sont écrites directement sur le disque plutôt que dans les mémoires tampons du système d’exploitation. Sans réécrire un programme existant, vous pouvez activer cette fonctionnalité en liant les fichiers objets du programme avec COMMODE.OBJ. Dans le fichier exécutable résultant, les appels à `_flushall` écrivent le contenu de toutes les mémoires tampons sur le disque. Seuls `_flushall` et `fflush` sont affectés par COMMODE.OBJ.  
  
 Pour plus d’informations sur le contrôle de la fonctionnalité de validation sur disque, consultez [E/S de flux](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md) et [_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md).  
  
 Cette fonction verrouille le thread appelant et est donc thread-safe. Pour une version sans verrouillage, voir `_fflush_nolock`.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`fflush`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_fflush.c  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int integer;  
   char string[81];  
  
   // Read each word as a string.  
   printf( "Enter a sentence of four words with scanf: " );  
   for( integer = 0; integer < 4; integer++ )  
   {  
      scanf_s( "%s", string, sizeof(string) );        
      printf( "%s\n", string );  
   }  
  
   // You must flush the input buffer before using gets.   
   // fflush on input stream is an extension to the C standard   
   fflush( stdin );     
   printf( "Enter the same sentence with gets: " );  
   gets_s( string, sizeof(string) );  
   printf( "%s\n", string );  
}  
```  
  
```Output  
  
      This is a test  
This is a test  
  
```  
  
```Output  
  
      This is a test  
This is a testEnter a sentence of four words with scanf: This is a test  
This  
is  
a  
test  
Enter the same sentence with gets: This is a test  
This is a test  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)
