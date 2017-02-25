---
title: "setvbuf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "setvbuf"
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
  - "setvbuf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôler la mise en mémoire tampon du flux"
  - "setvbuf (fonction)"
  - "mise en mémoire tampon du flux"
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
caps.latest.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 16
---
# setvbuf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Contrôle le chargement du flux et de la taille du tampon.  
  
## Syntaxe  
  
```  
int setvbuf(  
   FILE *stream,  
   char *buffer,  
   int mode,  
   size_t size   
);  
```  
  
#### Paramètres  
 `stream`  
 Pointeur vers la structure `FILE`.  
  
 `buffer`  
 Mémoire tampon allouée par l'utilisateur.  
  
 `mode`  
 Mode de mise en mémoire tampon.  
  
 `size`  
 Taille de la mémoire tampon en octets.  Plage autorisée : 2 \<\= `size` \<\= INT\_MAX \(2147483647\).  En interne, la valeur fournie pour `size` est arrondie au multiple de 2 inférieur à cette valeur le plus proche.  
  
## Valeur de retour  
 En cas de réussite, retourne 0.  
  
 Si `stream` est `NULL`, ou si `mode` ou `size` n'est pas dans une modification valide, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction renvoie \-1 et définit `errno` à la valeur `EINVAL`.  
  
 Pour plus d'informations sur ces codes d'erreur et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `setvbuf` permet au programme de contrôler la mise en mémoire tampon et la taille de la mémoire tampon de `stream`.  `stream` doit faire référence à un fichier ouvert qui n' a pas subi d'opération d'E\/S depuis qu'il a été ouvert.  Le tableau référencé par `buffer` est utilisé comme mémoire tampon, sauf s'il s'agit de `NULL`, auquel cas `setvbuf` utilise une mémoire tampon allouée automatiquement de longueur `size`\/2 \* 2 octets.  
  
 Le mode doit être `_IOFBF`, `_IOLBF`, ou `_IONBF`.  Si `mode` est `_IOFBF` ou `_IOLBF`, alors `size` est utilisé comme taille de la mémoire tampon.  Si `mode` est `_IONBF`, le flux de données n'est pas tamponné et `size` et `buffer` sont ignorés.  Les valeurs de `mode` et leurs significations sont :  
  
 `_IOFBF`  
 Mise en mémoire tampon saturée ; autrement dit, `buffer` est utilisé en tant que tampon et `size` est utilisée comme taille de la mémoire tampon.  Si `buffer` est `NULL`, une mémoire tampon automatiquement allouée de `size` octets de long est utilisée.  
  
 `_IOLBF`  
 Pour certains systèmes, cela fournit une mémoire tampon de ligne.  Toutefois, pour Win32, le comportement est le même que `_IOFBF` \- mise en mémoire tampon saturée.  
  
 `_IONBF`  
 Aucune mémoire tampon est utilisée, indépendamment de `buffer` ou de `size`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`setvbuf`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_setvbuf.c  
// This program opens two streams: stream1  
// and stream2. It then uses setvbuf to give stream1 a  
// user-defined buffer of 1024 bytes and stream2 no buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[1024];  
   FILE *stream1, *stream2;  
  
   if( fopen_s( &stream1, "data1", "a" ) == 0 &&  
       fopen_s( &stream2, "data2", "w" ) == 0 )  
   {  
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )  
         printf( "Incorrect type or size of buffer for stream1\n" );  
      else  
         printf( "'stream1' now has a buffer of 1024 bytes\n" );  
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )  
         printf( "Incorrect type or size of buffer for stream2\n" );  
      else  
         printf( "'stream2' now has no buffer\n" );  
      _fcloseall();  
   }  
}  
```  
  
  **« stream1 » possède désormais une mémoire tampon de 1024 octets**  
**« stream2 » n'a maintenant aucune mémoire tampon**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setbuf](../../c-runtime-library/reference/setbuf.md)