---
title: "ilogb, ilogbf, ilogbl | Microsoft Docs"
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
  - "ilogb"
  - "ilogbf"
  - "ilogbl"
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
  - "ilogb"
  - "ilogbf"
  - "ilogbl"
  - "math/ilogb"
  - "math/ilogbf"
  - "math/ilogbl"
helpviewer_keywords: 
  - "ilogb (fonction)"
  - "ilogbf (fonction)"
  - "ilogbl (fonction)"
ms.assetid: 9ef19d57-1caa-41d5-8233-2faad3562fcb
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ilogb, ilogbf, ilogbl
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère un entier qui représente l’exposant de base 2 non biaisée de la valeur spécifiée.  
  
## Syntaxe  
  
```  
int ilogb(  
   double x  
);  
  
int ilogb(  
   float x  
); //C++ only  
  
int ilogb(  
   long double x  
); //C++ only  
  
int ilogbf(  
   float x  
);  
  
int ilogbl(  
   long double x  
);  
  
```  
  
#### Paramètres  
 \[in\] `x`  
 Valeur spécifiée.  
  
## Valeur de retour  
 En cas de réussite, retourne l’exposant de base 2 de `x` une signature `int` valeur.  
  
 Sinon, retourne l’une des valeurs suivantes, définies dans \< math.h \> :  
  
|Entrée|Résultat|  
|------------|--------------|  
|±0|FP\_ILOGB0|  
|±inf, ±nan, indéterminée|FP\_ILOGBNAN|  
  
 Les erreurs sont signalées comme spécifié dans [\_matherr](../../c-runtime-library/reference/matherr.md).  
  
## Remarques  
 C\+\+ autorisant la surcharge, vous pouvez appeler des surcharges de `ilogb` qui acceptent et retournent des types float et doubles long. Dans un programme C, `ilogb` toujours prend et retourne une valeur double.  
  
 Appel de cette fonction est similaire à l’appel de l’équivalent `logb` \(fonction\), puis effectuer un cast de la valeur de retour pour `int`.  
  
## Configuration requise  
  
|Routine|En\-tête C|En\-tête C\+\+|  
|-------------|----------------|--------------------|  
|`ilogb`, `ilogbf`,  `ilogbl`|\<math.h\>|\<cmath\>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Référence alphabétique des fonctions](../../c-runtime-library/reference/crt-alphabetical-function-reference.md)   
 [frexp](../../c-runtime-library/reference/frexp.md)   
 [logb, logbf, logbl, \_logb, \_logbf](../../c-runtime-library/reference/logb-logbf-logbl-logb-logbf.md)