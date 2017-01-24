---
title: "fread | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "fread"
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
  - "fread"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "données (C++), lire à partir d'un flux d'entrée"
  - "fread (fonction)"
  - "lire des données (C++), à partir de flux d'entrée"
  - "flux (C++), lire des données à partir de"
ms.assetid: 9a3c1538-93dd-455e-ae48-77c1e23c53f0
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fread
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Lit les données à partir d'un flux.  
  
## Syntaxe  
  
```  
size_t fread(   
   void *buffer,  
   size_t size,  
   size_t count,  
   FILE *stream   
);  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour les données.  
  
 `size`  
 Taille d'élément en octets.  
  
 `count`  
 Nombre maximal d'éléments à lire.  
  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 `fread` retourne le nombre d'éléments complets lus réellement, qui peuvent être moins que `count` si une erreur se produit ou si la fin du fichier est rencontrée avant d'atteindre `count`d*.* Utilisez la fonction `feof` ou `ferror` pour distinguer une erreur de lecture d'une condition de fin du fichier.  Si `size` ou `count` est 0, `fread` retourne 0 et le contenu de la mémoire tampon reste inchangé.  Si `stream` ou `buffer` est un pointeur null, `fread` appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction définit `errno` à la valeur `EINVAL` et retourne 0.  
  
 Consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) pour plus d'informations sur ces éléments et autres codes d'erreur.  
  
## Notes  
 La fonction `fread` lit jusqu'à `count` les éléments des octets `size` de l'entrée `stream` et les stocke dans `buffer`*.* Le pointeur de fichier associé à `stream` \(s'il y en a un\) est augmenté par le nombre d'octets réellement lus.  Si le flux de données spécifié est ouvert en mode texte, les paires saut de ligne\-retour chariot sont remplacées par des caractères de saut de ligne.  Le remplacement n'a aucun effet sur le pointeur de fichier ou la valeur de retour.  La position du pointeur de fichier est indéterminée si une erreur se produit.  La valeur d'un élément partiellement lu ne peut pas être déterminée.  
  
 Cette fonction verrouille d'autres threads.  Si vous avez besoin d'une version non verrouillante, utilisez `_fread_nolock`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fread`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
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
  
  **A écrit 25 éléments**  
**Nombre d'éléments lus \= 25**  
**Contenu de la mémoire tampon \= zyxwvutsrqponmlkjihgfedcb**   
## Équivalent .NET Framework  
 [System::IO::FileStream::Read](https://msdn.microsoft.com/en-us/library/system.io.filestream.read.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fwrite](../../c-runtime-library/reference/fwrite.md)   
 [\_read](../../c-runtime-library/reference/read.md)