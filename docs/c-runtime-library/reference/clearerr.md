---
title: "clearerr | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "clearerr"
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
  - "clearerr"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "clearerr (fonction)"
  - "indicateur d'erreur pour les flux"
  - "réinitialiser l'indicateur d'erreur pour les flux"
ms.assetid: a9711cd4-3335-43d4-a018-87bbac5b3bac
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# clearerr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Réinitialise l'indicateur d'erreurs pour un flux de données.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [clearerr\_s](../../c-runtime-library/reference/clearerr-s.md).  
  
## Syntaxe  
  
```  
void clearerr(  
   FILE *stream   
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Notes  
 La fonction `clearerr` réinitialise l'indicateur et l'indicateur de fin de fichier d'erreurs pour le `stream`.  Les indicateurs d'erreur ne sont pas automatiquement désactivés ; une fois que l'indicateur d'erreurs pour un flux spécifié est défini, les opérations sur ce flux de données continuent à retourner une valeur d'erreur jusqu'à ce que `clearerr`, `fseek`, `fsetpos`, ou `rewind` soit appelé.  
  
 Si `stream` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction définit `errno` avec la valeur `EINVAL` et retourne.  Pour plus d'informations sur `errno` et les codes d'erreur, consultez [constantes d'errno](../../c-runtime-library/errno-constants.md).  
  
 Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [clearerr\_s](../../c-runtime-library/reference/clearerr-s.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`clearerr`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_clearerr.c  
// This program creates an error  
// on the standard input stream, then clears  
// it so that future reads won't fail.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int c;  
   // Create an error by writing to standard input.  
   putc( 'c', stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Write error" );  
      clearerr( stdin );  
   }  
  
   // See if read causes an error.  
   printf( "Will input cause an error? " );  
   c = getc( stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Read error" );  
      clearerr( stdin );  
   }  
   else  
      printf( "No read error\n" );  
}  
```  
  
  **`n` `n` Erreur d'écriture : Aucune erreur**  
**L'entrée provoquera\-elle une erreur ? n**  
**Aucune erreur de lecture**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Gestion des erreurs](../../c-runtime-library/error-handling-crt.md)   
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_eof](../../c-runtime-library/reference/eof.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)