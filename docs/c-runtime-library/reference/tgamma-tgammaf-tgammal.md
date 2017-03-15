---
title: "tgamma, tgammaf, tgammal | Microsoft Docs"
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
  - "tgamma"
  - "tgammaf"
  - "tgammal"
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
  - "tgamma"
  - "tgammaf"
  - "tgammal"
  - "math/tgamma"
  - "math/tgammaf"
  - "math/tgammal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "tgamma (fonction)"
  - "tgammaf (fonction)"
  - "tgammal (fonction)"
ms.assetid: f1bd2681-8af2-48a9-919d-5358fd068acd
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# tgamma, tgammaf, tgammal
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine la fonction gamma de la valeur spécifiée.  
  
## Syntaxe  
  
```  
double tgamma(  
   double x  
);  
  
float tgamma(  
   float x  
); //C++ only  
  
long double tgamma(  
   long double x  
); //C++ only  
  
float tgammaf(  
   float x  
);  
  
long double tgammal(  
   long double x  
);  
  
```  
  
#### Paramètres  
 \[in\] `x`  
 La valeur à rechercher la valeur gamma de.  
  
## Valeur de retour  
 En cas de réussite, retourne la valeur de gamma de `x`.  
  
 Une erreur de plage peut se produire si la grandeur de `x` est trop grande ou trop petite pour le type de données. Une erreur de domaine ou plage peut se produire si `x` \< \= 0.  
  
|Problème|Retourner|  
|--------------|---------------|  
|x \= ±0|±INFINITY|  
|x \= entier négatif|NaN|  
|x \= \- INFINITY|NaN|  
|x \= \+ infini|\+ INFINI|  
|x \= NaN|NaN|  
|Erreur de domaine|NaN|  
|Erreur de pôle|±HUGE\_VAL, ±HUGE\_VALF ou ±HUGE\_VALL|  
|Erreur de plage de dépassement de capacité|±HUGE\_VAL, ±HUGE\_VALF ou ±HUGE\_VALL|  
|Erreur de dépassement de plage|la valeur correcte après arrondi.|  
  
 Les erreurs sont signalées comme spécifié dans [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Remarques  
 C\+\+ autorisant la surcharge, vous pouvez appeler de tgamma des surcharges qui acceptent et retournent des types float et doubles long. Dans un programme C, tgamma toujours prend et retourne une valeur double.  
  
 Si x est un nombre, cette fonction retourne la factorielle de \(x\-1\).  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`tgamma`, `tgammaf`,  `tgammal`|\<math.h\>|\<cmath\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [lgamma, lgammaf, lgammal](../../c-runtime-library/reference/lgamma-lgammaf-lgammal.md)