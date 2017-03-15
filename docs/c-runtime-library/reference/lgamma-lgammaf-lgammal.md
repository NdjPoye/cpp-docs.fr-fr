---
title: "lgamma, lgammaf, lgammal | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "lgamma"
  - "lgammaf"
  - "lgammal"
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
  - "lgamma"
  - "lgammaf"
  - "lgammal"
  - "math/lgamma"
  - "math/lgammaf"
  - "math/lgammal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lgamma (fonction)"
  - "lgammal (fonction)"
  - "lgammaf (fonction)"
ms.assetid: 6e326c58-7077-481a-a329-c82ae56ae9e6
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# lgamma, lgammaf, lgammal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine le logarithme népérien de la valeur absolue de la fonction gamma de la valeur spécifiée.  
  
## Syntaxe  
  
```  
double lgamma(  
   double x  
);  
  
float lgamma(  
   float x  
); //C++ only  
  
long double lgamma(  
   long double x  
); //C++ only  
  
float lgammaf(  
   float x  
);  
  
long double lgammal(  
   long double x  
);  
  
```  
  
#### Paramètres  
 \[in\] `x`  
 Valeur à calculer.  
  
## Valeur de retour  
 En cas de réussite, retourne le logarithme népérien de la valeur absolue de la fonction gamma `x.`  
  
|Problème|Retourner|  
|--------------|---------------|  
|`x` \= NaN|NaN|  
|`x` \= ±0|\+ INFINI|  
|`x`\= entier négatif|\+ INFINI|  
|±INFINITY|\+ INFINI|  
|Erreur de pôle|\+ HUGE\_VAL \+ HUGE\_VALF, ou \+ HUGE\_VALL|  
|Erreur de plage de dépassement de capacité|±HUGE\_VAL, ±HUGE\_VALF ou ±HUGE\_VALL|  
  
 Les erreurs sont signalées comme spécifié dans [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Remarques  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `lgamma` qui acceptent et retournent des types float et doubles long. Dans un programme C, `lgamma` toujours prend et retourne une valeur double.  
  
 Si x est un nombre rationnel, cette fonction renvoie le logarithme de la factorielle de \(`x`\-1\).  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`lgamma`, `lgammaf`,  `lgammal`|\<math.h\>|\<cmath\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [tgamma, tgammaf, tgammal](../../c-runtime-library/reference/tgamma-tgammaf-tgammal.md)