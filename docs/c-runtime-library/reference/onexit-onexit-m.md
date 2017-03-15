---
title: "_onexit, _onexit_m | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_onexit"
  - "_onexit_m"
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
apitype: "DLLExport"
f1_keywords: 
  - "_onexit"
  - "onexit_m"
  - "onexit"
  - "_onexit_m"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "onexit, fonction"
  - "registre, inscrire des routines de sortie"
  - "_onexit_m, fonction"
  - "onexit_m, fonction"
  - "_onexit, fonction"
  - "inscrire des routines de sortie"
  - "inscription à appeler à la sortie"
ms.assetid: 45743298-0e2f-46cf-966d-1ca44babb443
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# _onexit, _onexit_m
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Enregistre une routine à appeler au moment de la sortie.  
  
## Syntaxe  
  
```  
_onexit_t _onexit(  
   _onexit_t function  
);  
_onexit_t_m _onexit_m(  
   _onexit_t_m function  
);  
```  
  
#### Paramètres  
 `function`  
 Pointeur vers la fonction à appeler dans la sortie.  
  
## Valeur de retour  
 `_onexit` retourne un pointeur vers la fonction en cas de réussite ou `NULL` s'il n'y a pas d'espace pour stocker le pointeur fonction.  
  
## Notes  
 La fonction `_onexit` se voit passer l'adresse d'une fonction \(`function`\) à appeler lorsque le programme se termine normalement.  Les appels successifs à `_onexit` créent un registre des fonctions exécutées dans l'ordre dernier entré premier sorti \(LIFO\).  Les fonctions transmises à `_onexit` ne peuvent pas prendre de paramètres.  
  
 Dans le cas où `_onexit` est appelé dans une DLL, les routines stockées avec `_onexit` executent dans les déchargements de la DLL après que `DllMain` soit appelé avec DLL\_PROCESS\_DETACH.  
  
 `_onexit` est une extension Microsoft.  Pour la portabilité ANSI, utilisez [atexit](../../c-runtime-library/reference/atexit.md).  La version `_onexit_m` de la fonction est pour un mode mixe.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_onexit`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_onexit.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
/* Prototypes */  
int fn1(void), fn2(void), fn3(void), fn4 (void);  
  
int main( void )  
{  
   _onexit( fn1 );  
   _onexit( fn2 );  
   _onexit( fn3 );  
   _onexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
int fn1()  
{  
   printf( "next.\n" );  
   return 0;  
}  
  
int fn2()  
{  
   printf( "executed " );  
   return 0;  
}  
  
int fn3()  
{  
   printf( "is " );  
   return 0;  
}  
  
int fn4()  
{  
   printf( "This " );  
   return 0;  
}  
```  
  
## Sortie  
  
```  
This is executed first.  
This is executed next.  
```  
  
## Équivalent .NET Framework  
 [System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [atexit](../../c-runtime-library/reference/atexit.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_\_dllonexit](../../c-runtime-library/dllonexit.md)