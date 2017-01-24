---
title: "rand | Microsoft Docs"
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
  - "rand"
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
  - "api-ms-win-crt-utility-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "rand"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "générer des nombres pseudo-aléatoires"
  - "nombres, générer pseudo-aléatoires"
  - "nombres, pseudo-aléatoire"
  - "nombres pseudo-aléatoires"
  - "rand (fonction)"
  - "nombres aléatoires, générer"
ms.assetid: 75d9df25-7aaf-4a88-b940-2775559634e8
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rand
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Génère un nombre pseudo\-aléatoire.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [rand\_s](../../c-runtime-library/reference/rand-s.md).  
  
## Syntaxe  
  
```  
int rand( void );  
```  
  
## Valeur de retour  
 `rand` retourne une valeur pseudo\-aléatoire, comme décrit ci\-dessus.  Aucun retour d'erreur.  
  
## Notes  
 La fonction `rand` retourne un entier pseudo\-aléatoire compris entre \-0 et `RAND_MAX` \(32767\).  Utilisez la fonction [srand](../../c-runtime-library/reference/srand.md) pour lancer le générateur de nombre pseudo\-aléatoire avant d'appeler `rand`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`rand`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_rand.c  
// This program seeds the random-number generator  
// with the time, then exercises the rand function.  
//  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <time.h>  
  
void SimpleRandDemo( int n )  
{  
   // Print n random numbers.  
   int i;  
   for( i = 0; i < n; i++ )  
      printf( "  %6d\n", rand() );  
}  
  
void RangedRandDemo( int range_min, int range_max, int n )  
{  
   // Generate random numbers in the half-closed interval  
   // [range_min, range_max). In other words,  
   // range_min <= random number < range_max  
   int i;  
   for ( i = 0; i < n; i++ )  
   {  
      int u = (double)rand() / (RAND_MAX + 1) * (range_max - range_min)  
            + range_min;  
      printf( "  %6d\n", u);  
   }  
}  
  
int main( void )  
{  
   // Seed the random-number generator with the current time so that  
   // the numbers will be different every time we run.  
   srand( (unsigned)time( NULL ) );  
  
   SimpleRandDemo( 10 );  
   printf("\n");  
   RangedRandDemo( -100, 100, 10 );  
}  
```  
  
  **22036**  
 **18330**  
 **11651**  
 **27464**  
 **18093**  
 **3284**  
 **11785**  
 **14686**  
 **11447**  
 **11285**  
 **74**  
 **48**  
 **27**  
 **65**  
 **96**  
 **64**  
 **\-5**  
 **\-42**  
 **\-55**  
 **66**   
## Équivalent .NET Framework  
 [System::Random Class](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [srand](../../c-runtime-library/reference/srand.md)   
 [rand\_s](../../c-runtime-library/reference/rand-s.md)