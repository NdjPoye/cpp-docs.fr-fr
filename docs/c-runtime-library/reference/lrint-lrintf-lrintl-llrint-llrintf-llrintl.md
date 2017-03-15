---
title: "lrint, lrintf, lrintl, llrint, llrintf, llrintl | Microsoft Docs"
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
  - "lrint"
  - "lrintl"
  - "lrintf"
  - "llrint"
  - "llrintf"
  - "llrintl"
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
  - "lrint"
  - "lrintf"
  - "lrintl"
  - "llrint"
  - "llrintf"
  - "llrintl"
  - "math/lrint"
  - "math/lrintf"
  - "math/lrintl"
  - "math/llrint"
  - "math/llrintf"
  - "math/llrintl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "lrint (fonction)"
  - "lrintf (fonction)"
  - "lrintl (fonction)"
  - "llrint (fonction)"
  - "llrintf (fonction)"
  - "llrintl (fonction)"
ms.assetid: 28ccd5b3-5e6f-434f-997d-a21d51b8ce7f
caps.latest.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 13
---
# lrint, lrintf, lrintl, llrint, llrintf, llrintl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Arrondit la valeur à virgule flottante spécifiée à la valeur intégrale la plus proche, en utilisant le mode d’arrondi actuel et la direction.  
  
## Syntaxe  
  
```  
long int lrint(  
   double x  
);  
  
long int lrint(  
   float x  
); //C++ only  
  
long int lrint(  
   long double x  
); //C++ only  
  
long int lrintf(  
   float x  
);  
  
long int lrintl(  
   long double x  
);  
  
long long int llrint(  
   double x  
);  
  
long long int llrint(  
   float x  
); //C++ only  
  
long long int llrint(  
   long double x  
); //C++ only  
  
long long int llrintf(  
   float x  
);  
  
long long int llrintl(  
   long double x  
);  
  
```  
  
#### Paramètres  
 \[in\] `x`  
 la valeur à arrondir.  
  
## Valeur de retour  
 En cas de réussite, retourne la valeur intégrale arrondie du `x`.  
  
|Problème|Retourner|  
|--------------|---------------|  
|`x` est en dehors de la plage du type de retour<br /><br /> `x` \= ±∞<br /><br /> `x` \= NaN|Déclenche FE\_INVALID et renvoie zéro \(0\).|  
  
## Remarques  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `lrint` et `llrint` qui acceptent des types float et doubles long. Dans un programme C, `lrint` et `llrint` ont toujours une valeur double.  
  
 Si `x` ne représente pas l’équivalent à virgule flottante d’une valeur intégrale, ces fonctions génèrent FE\_INEXACT.  
  
 **Spécifique à Microsoft**: lorsque le résultat est en dehors de la plage du type de retour, ou lorsque le paramètre est une valeur NaN ou l’infini, la valeur de retour implémentation est définie. Le compilateur Microsoft retourne une valeur zéro \(0\).  
  
## Configuration requise  
  
|Fonction|En\-tête C|En\-tête C\+\+|  
|--------------|----------------|--------------------|  
|`lrint`, `lrintf`, `lrintl`, `llrint`, `llrintf`, `llrintl`|\<math.h\>|\<cmath\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)