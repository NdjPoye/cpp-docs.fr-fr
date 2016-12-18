---
title: "fflush | Microsoft Docs"
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
  - "fflush"
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
  - "fflush"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fflush (fonction)"
  - "vider"
  - "flux, vider"
ms.assetid: 8bbc753f-dc74-4e77-b563-74da2835e92b
caps.latest.revision: 18
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# fflush
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vide un flux de données.  
  
## Syntaxe  
  
```  
int fflush(   
   FILE *stream   
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 `fflush` retourne 0 si la mémoire tampon a été vidée.  La valeur 0 est également retournée dans les cas où le flux de données spécifié n'a aucune mémoire tampon ou est ouvert en lecture seule.  Une valeur de retour de `EOF` indique une erreur.  
  
> [!NOTE]
>  Si `fflush` retourne `EOF`, les données peuvent avoir été perdues en raison d'une erreur d'écriture.  En installant un gestionnaire d'erreurs critiques, il est plus sécurisé de désactiver la mise en mémoire tampon avec la fonction `setvbuf` ou d'utiliser les routines de bas niveau d'E\/S telles que `_open` `_close`, et `_write` au lieu des fonctions d'E\/S de flux de données.  
  
## Notes  
 La fonction `fflush` vide un flux de données.  Si le fichier associé à `stream` est ouvert pour la sortie, `fflush` écrit sur ce fichier le contenu de la mémoire tampon associée au flux de données.  Si le flux est ouvert pour l'entrée, `fflush` efface le contenu de la mémoire tampon.  `fflush` inverse l'effet de tout appel antérieur à `ungetc` sur `stream`.  En outre, `fflush(NULL)` vide tous les flux de données ouverts pour la sortie.  Le flux de données reste ouvert après l'appel.  `fflush` n'a aucun effet sur un flux de données non tamponné.  
  
 Les mémoires tampons sont normalement conservées par le système d'exploitation, qui détermine l'heure optimale pour écrire les données automatiquement sur le disque : lorsqu'une mémoire tampon est complète, lorsqu'un flux est fermé, ou lorsqu'un programme se termine normalement sans fermer le flux.  La fonctionnalité validée sur disque de la bibliothèque runtime vous permet de garantir que les données critique est écrite directement sur le disque plutôt que sur les mémoires tampons du système d'exploitation.  Sans réécrire un programme existant, vous pouvez activer cette fonctionnalité en liant les fichiers objets du programme avec COMMODE.OBJ.  Dans le fichier exécutable obtenu, les appels à `_flushall` lisent le contenu de toutes les mémoires tampons sur le disque.  Seuls `_flushall` et `fflush` sont affectés par COMMODE.OBJ.  
  
 Pour plus d'informations sur le contrôle de la fonctionnalité validée sur disque, consultez [Flux E\/S](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md), et [\_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md).  
  
 Cette fonction verrouille le thread appelant et est par conséquent thread\-safe.  Pour une version non verrouillante, consultez `_fflush_nolock`.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`fflush`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
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
  
  **`Il s'agit d'un test. Il s'agit d'un test`  `Il s'agit d'un test Il s'agit d'un test`entrez une phrase de quatre mots avec scanf : Il s'agit d'un test \(This is a test en anglais\)**  
**Cet objet .**  
**est**  
**a**  
**tester**  
**Entrez la même phrase avec obtient : Il s'agit d'un test**  
**Il s'agit d'un test.**   
## Équivalent .NET Framework  
 [System::IO::FileStream::Flush](https://msdn.microsoft.com/en-us/library/2bw4h516.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_flushall](../../c-runtime-library/reference/flushall.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)