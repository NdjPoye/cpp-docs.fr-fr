---
title: "_isatty | Microsoft Docs"
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
  - "_isatty"
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
  - "_isatty"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_isatty (fonction)"
  - "vérification du périphérique"
  - "vérifier les périphériques"
  - "isatty (fonction)"
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
caps.latest.revision: 18
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _isatty
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si un descripteur de fichier est associé à un périphérique de caractères.  
  
## Syntaxe  
  
```  
  
      int _isatty(  
int fd   
);  
```  
  
#### Paramètres  
 `fd`  
 Descripteur de fichier qui fait référence au périphérique à tester.  
  
## Valeur de retour  
 `_isatty` retourne une valeur différente de zéro si le descripteur est associé à un périphérique de caractères.  Sinon, `_isatty` retourne zéro.  
  
## Notes  
 La fonction `_isatty` détermine si `fd` est associé à un périphérique de caractères \(un terminal, une console, une imprimante, ou un port série\).  
  
 Cette fonction valide le paramètre `fd` .  Si `fd` est un pointeur vers un mauvais fichier, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md) .  Si l'exécution est autorisée à se poursuivre, la fonction retourne 0 et définit `errno` avec la valeur `EBADF`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_isatty`|\<io.h,\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_isatty.c  
/* This program checks to see whether  
 * stdout has been redirected to a file.  
 */  
  
#include <stdio.h>  
#include <io.h>  
  
int main( void )  
{  
   if( _isatty( _fileno( stdout ) ) )  
      printf( "stdout has not been redirected to a file\n" );  
   else  
      printf( "stdout has been redirected to a file\n");  
}  
```  
  
## Résultat de l'exemple  
  
```  
stdout has not been redirected to a file  
```  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)