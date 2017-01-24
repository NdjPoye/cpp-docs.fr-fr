---
title: "clearerr_s | Microsoft Docs"
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
  - "clearerr_s"
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
  - "clearerr_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "clearerr_s (fonction)"
  - "indicateur d'erreur pour les flux"
  - "réinitialiser l'indicateur d'erreur pour les flux"
ms.assetid: b74d014d-b7a8-494a-a330-e5ffd5614772
caps.latest.revision: 19
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# clearerr_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Réinitialise l'indicateur d'erreurs pour un flux de données.  Il s'agit de versions de [](../../c-runtime-library/reference/clearerr.md "clearerr")[Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t clearerr_s(  
   FILE *stream   
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
## Valeur de retour  
 Zéro en cas de réussite ; `EINVAL` si `stream` est NULL.  
  
## Notes  
 La fonction `clearerr_s` réinitialise l'indicateur et l'indicateur de fin de fichier d'erreurs pour le `stream`.  Les indicateurs d'erreur ne sont pas automatiquement désactivés ; une fois que l'indicateur d'erreurs pour un flux a été spécifié, les opérations sur ce flux de données continuent à retourner une valeur d'erreur jusqu'à que`clearerr_s`, `clearerr`, `fseek`, `fsetpos`, ou `rewind` soit appelé.  
  
 Si `stream` a la valeur NULL, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction paramètre `errno` à `EINVAL` et renvoie `EINVAL`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`clearerr_s`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_clearerr_s.c  
// This program creates an error  
// on the standard input stream, then clears  
// it so that future reads won't fail.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int c;  
   errno_t err;  
  
   // Create an error by writing to standard input.  
   putc( 'c', stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Write error" );  
      err = clearerr_s( stdin );  
      if (err != 0)  
      {  
         abort();  
      }  
   }  
  
   // See if read causes an error.  
   printf( "Will input cause an error? " );  
   c = getc( stdin );  
   if( ferror( stdin ) )  
   {  
      perror( "Read error" );  
      err = clearerr_s( stdin );  
      if (err != 0)  
      {  
         abort();  
      }  
   }  
}  
```  
  
  **`n` `n` Erreur d'écriture : Mauvais descripteur de fichier**  
**L'entrée provoquera\-elle une erreur ? n**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Gestion des erreurs](../../c-runtime-library/error-handling-crt.md)   
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [clearerr](../../c-runtime-library/reference/clearerr.md)   
 [\_eof](../../c-runtime-library/reference/eof.md)   
 [feof](../../c-runtime-library/reference/feof.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [perror, \_wperror](../../c-runtime-library/reference/perror-wperror.md)