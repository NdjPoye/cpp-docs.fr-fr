---
title: "_heapchk | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_heapchk"
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
  - "api-ms-win-crt-heap-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_heapchk"
  - "heapchk"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_heapchk (fonction)"
  - "vérifier la cohérence des tas"
  - "déboguer (CRT), problèmes liés au tas"
  - "heapchk (fonction)"
  - "tas, vérifier la cohérence"
ms.assetid: 859619a5-1e35-4f02-9e09-11d9fa266ec0
caps.latest.revision: 13
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _heapchk
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Effectue des vérifications de cohérence sur le tas.  
  
## Syntaxe  
  
```  
int _heapchk( void );  
```  
  
## Valeur de retour  
 `_heapchk` retourne un des constantes de manifeste d'entiers suivantes définies dans Malloc.h.  
  
 `_HEAPBADBEGIN`  
 Les informations d'en\-tête initiales sont incorrectes ou ne peuvent pas être trouvées.  
  
 `_HEAPBADNODE`  
 Un nœud incorrect a été trouvé ou le tas est endommagé.  
  
 `_HEAPBADPTR`  
 Le pointeur vers le tas n'est pas valide.  
  
 `_HEAPEMPTY`  
 Le tas n'a pas été initialisé.  
  
 `_HEAPOK`  
 Le tas apparaît être cohérent.  
  
 En outre, si une erreur se produit, `_heapchk` définit `errno` à `ENOSYS`.  
  
## Notes  
 La fonction `_heapchk` aide au débogage des problèmes liés au tas en vérifiant la cohérence minimale du tas.  Si le système d'exploitation ne prend pas en charge `_heapchk`\(par exemple, Windows 98\), la fonction retourne `_HEAPOK` et affecte à `errno` la valeur `ENOSYS`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_heapchk`|\<malloc.h\>|\<errno.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_heapchk.c  
// This program checks the heap for  
// consistency and prints an appropriate message.  
  
#include <malloc.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  heapstatus;  
   char *buffer;  
  
   // Allocate and deallocate some memory  
   if( (buffer = (char *)malloc( 100 )) != NULL )  
      free( buffer );  
  
   // Check heap status  
   heapstatus = _heapchk();  
   switch( heapstatus )  
   {  
   case _HEAPOK:  
      printf(" OK - heap is fine\n" );  
      break;  
   case _HEAPEMPTY:  
      printf(" OK - heap is empty\n" );  
      break;  
   case _HEAPBADBEGIN:  
      printf( "ERROR - bad start of heap\n" );  
      break;  
   case _HEAPBADNODE:  
      printf( "ERROR - bad node in heap\n" );  
      break;  
   }  
}  
```  
  
  **OK \- le tas est bien.**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)   
 [\_heapadd](../../c-runtime-library/heapadd.md)   
 [\_heapmin](../../c-runtime-library/reference/heapmin.md)   
 [\_heapset](../../c-runtime-library/heapset.md)   
 [\_heapwalk](../../c-runtime-library/reference/heapwalk.md)