---
title: "logb, logbf, logbl, _logb, _logbf | Microsoft Docs"
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
  - "logb"
  - "_logb"
  - "_logbl"
  - "logbf"
  - "logbl"
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
  - "logb"
  - "logbl"
  - "_logb"
  - "_logbf"
  - "logbf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_logb (fonction)"
  - "_logbf (fonction)"
  - "exposant, chiffres à virgule flottante"
  - "exposants et mantisses"
  - "fonctions en virgule flottante"
  - "fonctions en virgule flottante, mantisse et exposant"
  - "logb (fonction)"
  - "logbf (fonction)"
  - "logbl (fonction)"
  - "mantisses, variables à virgule flottante"
ms.assetid: 780c4daa-6fe6-4fbc-9412-4c1ba1a1766f
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# logb, logbf, logbl, _logb, _logbf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Extrait la valeur d'exposant d'un argument à virgule flottante.  
  
## Syntaxe  
  
```  
double logb(  
   double x   
);  
float logb(  
   float x   
); // C++ only  
long double logb(  
   long double x   
); // C++ only   
float logbf(  
   float x   
);  
long double logbl(  
   long double x   
);  
double _logb(  
   double x   
);  
float _logbf(  
   float x   
);  
```  
  
#### Paramètres  
 x  
 Valeur à virgule flottante.  
  
## Valeur de retour  
 `logb` renvoie la valeur impartiale d'exposant de `x` comme un entier signé représenté comme valeur à virgule flottante.  
  
## Notes  
 Les fonctions `logb` récupèrent la valeur exponentielle de l'argument à virgule flottante `x`, comme si `x` était représentés avec la plage infinie.  Si l'argument `x` n'est plus normalisé, il est traité comme s'il était normalisé.  
  
 Comme C\+\+ permet la surcharge, vous pouvez appeler les surcharges de `logb` qui acceptent et retournent les valeurs `float` ou `long double`.  Dans un programme C, `logb` prend et retourne toujours `double`.  
  
|Entrée|Exception SEH|Exception Matherr|  
|------------|-------------------|-----------------------|  
|± QNAN,IND|Aucun|\_DOMAIN|  
|± 0|ZERODIVIDE|\_SING|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_logb`|\<float.h\>|  
|`logb`, `logbf`, `logbl`, `_logbf`|\<math.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)