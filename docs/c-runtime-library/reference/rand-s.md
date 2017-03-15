---
title: "rand_s | Microsoft Docs"
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
  - "rand_s"
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
  - "rand_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "nombres aléatoires sécurisés par chiffrement"
  - "générer des nombres pseudo-aléatoires"
  - "nombres, générer pseudo-aléatoires"
  - "nombres, pseudo-aléatoire"
  - "nombres pseudo-aléatoires"
  - "rand_s (fonction)"
  - "nombres aléatoires, sécurisés par chiffrement"
  - "nombres aléatoires, générer"
ms.assetid: d6a0be60-997d-4904-8411-8aea6839cc94
caps.latest.revision: 24
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# rand_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Génère un nombre pseudo\-aléatoire.  Il s'agit de versions de [rand](../../c-runtime-library/reference/rand.md) avec des améliorations de sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t rand_s(   unsigned int* randomValue);  
```  
  
## Valeur de retour  
 Zéro dans le cas d'une opération réussie, sinon affiche un code d'erreur.  Si le paramètre d'entrée `randomValue` est un pointeur null ou si la fonction appelle un gestionnaire de paramètre non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, la fonction retourne `EINVAL` et définit `errno` à la valeur `EINVAL`.  Si la fonction échoue pour toute autre raison, \*`randomValue` est défini à la valeur 0.  
  
## Notes  
 La fonction `rand_s` écrit un entier pseudo\-aléatoire comprise entre 0 et `UINT_MAX` au pointeur d'entrée.  La fonction `rand_s` utilise le système d'exploitation pour générer des nombres aléatoires sécurisés cryptographiquement.  Il n'utilise pas la valeur générée par la fonction [srand](../../c-runtime-library/reference/srand.md), ni n'affecte la séquence de nombres aléatoires utilisée par `rand`.  
  
 La fonction `rand_s` nécessite que la constante`_CRT_RAND_S` soit définie avant que l'instruction d'inclusion pour la fonction ne soit déclarée, comme dans l'exemple suivant :  
  
```  
#define _CRT_RAND_S  
#include <stdlib.h>  
```  
  
 `rand_s` dépend de l'API [RtlGenRandom](http://msdn.microsoft.com/library/windows/desktop/aa387694), qui est disponible dans Windows XP ou ses versions ultérieures.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`rand_s`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_rand_s.c  
// This program illustrates how to generate random  
// integer or floating point numbers in a specified range.  
  
// Remembering to define _CRT_RAND_S prior  
// to inclusion statement.  
#define _CRT_RAND_S  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <limits.h>  
  
int main( void )  
{  
    int             i;  
    unsigned int    number;  
    double          max = 100.0;  
    errno_t         err;  
  
    // Display 10 random integers in the range [ 1,10 ].  
    for( i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %u\n", (unsigned int) ((double)number /  
                       ((double) UINT_MAX + 1 ) * 10.0) + 1);  
    }  
  
    printf_s("\n");  
  
    // Display 10 random doubles in [0, max).  
    for (i = 0; i < 10;i++ )  
    {  
        err = rand_s( &number );  
        if (err != 0)  
        {  
            printf_s("The rand_s function failed!\n");  
        }  
        printf_s( "  %g\n", (double) number /   
                          ((double) UINT_MAX + 1) * max );  
    }  
}  
```  
  
## Résultat de l'exemple  
  
```  
10  
4  
5  
2  
8  
2  
5  
6  
1  
1  
  
32.6617  
29.4471  
11.5413  
6.41924  
20.711  
60.2878  
61.0094  
20.1222  
80.9192  
65.0712  
```  
  
## Équivalent .NET Framework  
 [System::Random Class](https://msdn.microsoft.com/en-us/library/system.random.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [srand](../../c-runtime-library/reference/srand.md)