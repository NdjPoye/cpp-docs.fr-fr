---
title: "setbuf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "setbuf"
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
  - "setbuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "setbuf (fonction)"
  - "mise en mémoire tampon du flux"
ms.assetid: 13beda22-7b56-455d-8a6c-f2eb636885b9
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# setbuf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Contrôle du chargement du flux  Cette fonction est déconseillée ; utilisez [setvbuf](../../c-runtime-library/reference/setvbuf.md) à la place.  
  
## Syntaxe  
  
```  
void setbuf(  
   FILE *stream,  
   char *buffer   
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
 `buffer`  
 Mémoire tampon allouée par l'utilisateur.  
  
## Notes  
 La fonction d'`setbuf` contrôle la mise en mémoire tampon pour `stream`.  L'argument `stream` doit faire référence à un fichier ouvert qui n'a pas été lu ou n'a pas été écrit.  Si l'argument `buffer` est `NULL`, le flux de données n'est pas tamponné.  Sinon, la mémoire tampon doit afficher un tableau de caractères de longueur `BUFSIZ`, où `BUFSIZ` est la taille du tampon comme défini dans. STDIO.H.  La mémoire tampon spécifiée par l'utilisateur, au lieu de la mémoire tampon allouée système par défaut pour le flux de données spécifié, est utilisé pour la mise en mémoire tampon d'E\/S.  Le flux d'`stderr` n'est pas tamponné par défaut, mais vous pouvez utiliser `setbuf` pour affecter des tampons à `stderr`.  
  
 `setbuf` a été remplacé par [setvbuf](../../c-runtime-library/reference/setvbuf.md), qui est une routine par défaut pour un nouveau code.  `setbuf` est fourni pour la compatibilité avec le code existant.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`setbuf`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_setbuf.c  
// compile with: /W3  
// This program first opens files named DATA1 and  
// DATA2. Then it uses setbuf to give DATA1 a user-assigned  
// buffer and to change DATA2 so that it has no buffer.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[BUFSIZ];  
   FILE *stream1, *stream2;  
  
   fopen_s( &stream1, "data1", "a" );  
   fopen_s( &stream2, "data2", "w" );  
  
   if( (stream1 != NULL) && (stream2 != NULL) )  
   {  
      // "stream1" uses user-assigned buffer:  
      setbuf( stream1, buf ); // C4996  
      // Note: setbuf is deprecated; consider using setvbuf instead  
      printf( "stream1 set to user-defined buffer at: %Fp\n", buf );  
  
      // "stream2" is unbuffered  
      setbuf( stream2, NULL ); // C4996  
      printf( "stream2 buffering disabled\n" );  
      _fcloseall();  
   }  
}  
```  
  
  **stream1 à la mémoire tampon définie par l'utilisateur à : 0012FCDC**  
**mise en mémoire tampon stream2 désactivée**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)