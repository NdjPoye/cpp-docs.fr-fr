---
title: "fread_s | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fread_s"
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
  - "fread_s"
  - "stdio/fread_s"
dev_langs: 
  - "C++"
ms.assetid: ce735de0-f005-435d-a8f2-6f4b80ac775e
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# fread_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit les données à partir d'un flux.  Cette version de [](../../c-runtime-library/reference/fread.md "fread")[Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
size_t fread_s(   
   void *buffer,  
   size_t bufferSize,  
   size_t elementSize,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour les données.  
  
 `bufferSize`  
 Taille en octets, de la mémoire tampon désirée.  
  
 `elementSize`  
 Taille de l'élément en lecture en octets.  
  
 `count`  
 Nombre maximal d'éléments à lire.  
  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 `fread_s` retourne le nombre d'éléments \(entier\) qui ont été lu0s dans la mémoire tampon, qui peut être moins que `count` si une erreur de lecture ou la fin du fichier est rencontrée avant `count` soit atteint.  Utilisez la fonction `feof` ou `ferror` pour distinguer une erreur de lecture d'une condition de fin du fichier.  Si `size` ou `count` est 0, `fread_s` retourne 0 et le contenu de la mémoire tampon reste inchangé.  Si `stream` ou `buffer` est un pointeur null, `fread_s` appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction définit `errno` à la valeur `EINVAL` et retourne 0.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes d'erreur.  
  
## Notes  
 La fonction `fread_s` lit jusqu'à `count` les éléments des octets `elementSize` de l'entrée `stream` et les stocke dans `buffer`.  Le pointeur de fichier associé à `stream` \(s'il y en a un\) est augmenté par le nombre d'octets réellement lus.  Si le flux de données spécifié est ouvert en mode texte, les paires saut de ligne\-retour chariot sont remplacées par des caractères de saut de ligne.  Le remplacement n'a aucun effet sur le pointeur de fichier ou la valeur de retour.  La position du pointeur de fichier est indéterminée si une erreur se produit.  La valeur d'un élément partiellement lu ne peut pas être déterminée.  
  
 Cette fonction verrouille d'autres threads.  Si vous avez besoin d'une version non verrouillante, utilisez `_fread_nolock`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fread_s`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
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
  
  **Contenu de la mémoire tampon avant l'écriture\/lecture :**   
 **zyxwvutsrqponmlkjihgfe**  
 **A écrit 22 éléments**   
 **Le nombre de 11 éléments d'octets indique \= 2**   
 **Contenu de la mémoire tampon après écriture\/lecture :**   
 **zyxwvutsrqponmlkjihgfe**    
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [\_read](../../c-runtime-library/reference/read.md)