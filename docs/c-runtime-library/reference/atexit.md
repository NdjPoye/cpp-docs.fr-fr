---
title: "atexit | Microsoft Docs"
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
  - "atexit"
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
  - "atexit"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "atexit (fonction)"
  - "traiter, en sortie"
ms.assetid: 92c156d2-8052-4e58-96dc-00128baac6f9
caps.latest.revision: 12
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# atexit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Traite la fonction spécifiée à la sortie.  
  
## Syntaxe  
  
```  
int atexit(  
   void (__cdecl *func )( void )  
);  
```  
  
#### Paramètres  
 `func`  
 Fonction à appeler.  
  
## Valeur de retour  
 `atexit` retourne 0 si a réussi, ou une valeur différente de zéro si une erreur se produit.  
  
## Notes  
 La fonction `atexit` se voit passer l'adresse d'une fonction \(`func`\) à appeler lorsque le programme se termine normalement.  Les appels successifs à `atexit` créent un registre des fonctions exécutées dans l'ordre dernier entré premier sorti \(LIFO\).  Les fonctions transmises à `atexit` ne peuvent pas prendre de paramètres.  `atexit` et `_onexit` utilisent le tas pour tenir le registre des fonctions.  Par conséquent, le nombre de fonctions qui peuvent être stockées n'est limité que par la mémoire de tas.  
  
 Le code de la fonction `atexit` ne doit pas contenir de dépendance sur aucun DLL qui peut avoir déjà été déchargé quand la fonction `atexit` a été appelée.  
  
 Pour générer une application conforme à l'ANSI, utilisez la fonction ANSI standard `atexit` \(plutôt que la fonction similaire `_onexit` \).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`atexit`|\<stdlib.h\>|  
  
## Exemple  
 Ce programme place quatre fonctions sur la pile de fonctions à exécuter lorsque `atexit` est appelé.  Lorsque le programme sort, ces programmes sont exécutées sur une base dernier entré premier sorti.  
  
```  
// crt_atexit.c  
#include <stdlib.h>  
#include <stdio.h>  
  
void fn1( void ), fn2( void ), fn3( void ), fn4( void );  
  
int main( void )  
{  
   atexit( fn1 );  
   atexit( fn2 );  
   atexit( fn3 );  
   atexit( fn4 );  
   printf( "This is executed first.\n" );  
}  
  
void fn1()  
{  
   printf( "next.\n" );  
}  
  
void fn2()  
{  
   printf( "executed " );  
}  
  
void fn3()  
{  
   printf( "is " );  
}  
  
void fn4()  
{  
   printf( "This " );  
}  
```  
  
  **Cela est effectué en premier.**  
**Cela est exécuté après.**   
## Équivalent .NET Framework  
 [System::Diagnostics::Process::Exited](https://msdn.microsoft.com/en-us/library/system.diagnostics.process.exited.aspx)  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [abort](../../c-runtime-library/reference/abort.md)   
 [exit, \_Exit, \_exit](../../c-runtime-library/reference/exit-exit-exit.md)   
 [\_onexit, \_onexit\_m](../../c-runtime-library/reference/onexit-onexit-m.md)