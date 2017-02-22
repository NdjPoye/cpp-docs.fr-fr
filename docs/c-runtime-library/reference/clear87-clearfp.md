---
title: "_clear87, _clearfp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_clearfp"
  - "_clear87"
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
  - "api-ms-win-crt-runtime-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "clearfp"
  - "_clearfp"
  - "_clear87"
  - "clear87"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_clear87 (fonction)"
  - "_clearfp (fonction)"
  - "clear87 (fonction)"
  - "clearfp (fonction)"
  - "effacer le mot de l'état de la virgule flottante"
ms.assetid: 72d24a70-7688-4793-ae09-c96d33fcca52
caps.latest.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 17
---
# _clear87, _clearfp
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient et efface le mot d'état à virgule flottante.  
  
## Syntaxe  
  
```  
unsigned int _clear87( void );  
unsigned int _clearfp( void );  
```  
  
## Valeur de retour  
 Les bits contenus dans la valeur retournée indiquent l'état à virgule flottante avant l'appel à `_clear87` ou `_clearfp`.  Pour obtenir une définition complète des bits retournés par `_clear87`, consultez Float.h.  Une part importante des fonctions de bibliothèque mathématique modifie le mot d'état 8087\/80287, avec des résultats imprévisibles.  La fiabilité des valeurs de retour de `_clear87` et `_status87` est inversement proportionnelle au nombre d'opérations à virgule flottante exécutées entre les états connus du mot d'état à virgule flottante.  
  
## Notes  
 La fonction `_clear87` efface les indicateurs d'exception dans le mot d'état à virgule flottante, définit le bit occupé à 0 et retourne le mot d'état.  Le mot d'état à virgule flottante est une combinaison du mot d'état 8087\/80287 et d'autres conditions détectées par le gestionnaire d'exceptions 8087\/80287, telles que le dépassement de capacité positif et négatif de pile à virgule flottante.  
  
 `_clearfp` est une version portable indépendante de la plateforme de le routine `_clear87`.  Elle est identique à `_clear87` sur les plateformes Intel \(x 86\) et est aussi prise en charge par les plateformes x64 et ARM.  Pour assurer la portabilité de votre code à virgule flottante vers x64 et ARM, utilisez `_clearfp`.  Si vous ciblez uniquement les plateformes x86, vous pouvez utiliser `_clear87` ou `_clearfp`.  
  
 Ces fonctions sont déconseillées dans le cadre d'une compilation avec [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md) ou `/clr:pure`, car le common language runtime prend uniquement en charge la précision à virgule flottante par défaut.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_clear87`|\<float.h\>|  
|`_clearfp`|\<float.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_clear87.c  
// compile with: /Od  
  
// This program creates various floating-point   
// problems, then uses _clear87 to report on these problems.  
// Compile this program with Optimizations disabled (/Od).   
// Otherwise the optimizer will remove the code associated with   
// the unused floating-point values.  
//  
  
#include <stdio.h>  
#include <float.h>  
  
int main( void )  
{  
   double a = 1e-40, b;  
   float x, y;  
  
   printf( "Status: %.4x - clear\n", _clear87()  );  
  
   // Store into y is inexact and underflows:  
   y = a;  
   printf( "Status: %.4x - inexact, underflow\n", _clear87() );  
  
   // y is denormal:   
   b = y;  
   printf( "Status: %.4x - denormal\n", _clear87() );  
}  
```  
  
  **Status: 0000 \- clear**  
**Status: 0003 \- inexact, underflow**  
**Status: 80000 \- denormal**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [\_status87, \_statusfp, \_statusfp2](../../c-runtime-library/reference/status87-statusfp-statusfp2.md)