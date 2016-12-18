---
title: "log1p, log1pf, log1pl | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "log1p"
  - "log1pf"
  - "log1pl"
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
  - "api-ms-win-crt-math-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "log1p"
  - "log1pf"
  - "log1pl"
  - "math/log1p"
  - "math/log1pf"
  - "math/log1pl"
helpviewer_keywords: 
  - "log1p (fonction)"
  - "log1pf (fonction)"
  - "log1pl (fonction)"
ms.assetid: a40d965d-b4f6-42f4-ba27-2395546f7c12
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# log1p, log1pf, log1pl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Calcule le logarithme népérien de 1 et la valeur spécifiée.  
  
## Syntaxe  
  
```  
double log1p(  
   double x  
);  
  
float log1p(  
   float x  
); //C++ only  
  
long double log1p(  
   long double x  
); //C++ only  
  
float log1pf(  
   float x  
);  
  
long double log1pl(  
   long double x  
);  
  
```  
  
#### Paramètres  
 `x`  
 L’argument à virgule flottante.  
  
## Valeur de retour  
 En cas de réussite, retourne le logarithme naturel \(base e\) de \(`x`\+ 1\).  
  
 Dans le cas contraire, peut retourner l’une des valeurs suivantes :  
  
|Entrée|Résultat|Exception SEH|errno|  
|------------|--------------|-------------------|-----------|  
|\+ inf|\+ inf|||  
|Nombres dénormalisés|Identique à l’entrée|DÉPASSEMENT DE CAPACITÉ NÉGATIF||  
|±0|Identique à l’entrée|||  
|\-1|\-inf|DIVBYZERO|ERANGE|  
|\< \-1|NaN|NON VALIDE|EDOM|  
|\-inf|NaN|NON VALIDE|EDOM|  
|±SNaN|Identique à l’entrée|NON VALIDE||  
|±QNaN, indéterminée|Identique à l’entrée|||  
  
 Le `errno` a la valeur ERANGE si `x` \= \-1. Le `errno` a la valeur EDOM si `x` \< −1.  
  
## Notes  
 Le `log1p` les fonctions peuvent être plus précises que l’utilisation de journaux \(`x`\+ 1\) si x est proche de 0.  
  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `log1p` qui acceptent et retournent des types float et doubles long. Dans un programme C, `log1p` toujours prend et retourne une valeur double.  
  
 Si `x` est un nombre, cette fonction renvoie le logarithme de la factorielle de \(`x`\-1\).  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`log1p`, `log1pf`,  `log1pl`|\<math.h\>|\<cmath\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [LOG2, log2f, log2l](../../c-runtime-library/reference/log2-log2f-log2l.md)   
 [log, logf, log10, log10f](../../c-runtime-library/reference/log-logf-log10-log10f.md)