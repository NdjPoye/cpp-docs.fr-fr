---
title: "isNaN, _isnan, _isnanf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_isnan"
  - "_isnanf"
  - "isnan"
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
  - "_isnan"
  - "isnan"
  - "math/isnan"
  - "math/_isnan"
  - "math/_isnanf"
  - "_isnanf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "NAN (non numérique)"
  - "_isnan (fonction)"
  - "représentation à virgule flottante IEEE"
  - "Non numérique (NAN)"
  - "isnan (fonction)"
ms.assetid: 391fbc5b-89a4-4fba-997e-68f1131caf82
caps.latest.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 11
---
# isNaN, _isnan, _isnanf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Teste si une valeur à virgule flottante n’est pas un nombre \(NAN\).  
  
## Syntaxe  
  
```  
int isnan(  
   /* floating-point */ x   
); /* C-only macro */  
  
int _isnan(  
   double x   
);  
  
int _isnanf(  
   float x  
); /* x64 only */  
  
template <class T>  
bool isnan(  
   T x  
) throw(); /* C++ only */  
```  
  
#### Paramètres  
 *x*  
 Valeur à virgule flottante à tester.  
  
## Valeur de retour  
 En C, les `isnan` macro et `_isnan` et `_isnanf` fonctions renvoient une valeur différente de zéro si l’argument `x` est une valeur NAN ; sinon, elles retournent 0.  
  
 En C\+\+, le `isnan` modèle fonctions retournent `true` Si l’argument `x` est une valeur NAN ; sinon, elles retournent `false`.  
  
## Notes  
 C `isnan` macro et `_isnan` et `_isnanf` fonctions testent la valeur à virgule flottante *x*, qui retourne une valeur différente de zéro si *x* n’est pas une valeur de nombre \(NAN\). Une valeur NAN est générée lorsque le résultat d’une opération en virgule flottante ne peut pas être représenté dans un format à virgule flottante IEEE\-754 pour le type spécifié. Pour plus d’informations sur la façon dont une valeur NAN est représentée pour la sortie, consultez [printf](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
 Lors de la compilation c\+\+, le `isnan` macro n’est pas définie et un `isnan` modèle de fonction est défini à la place. Elle retourne une valeur de type `bool` au lieu d’un entier.  
  
 Le `_isnan` et `_isnanf` les fonctions sont spécifiques de Microsoft. Le `_isnanf` fonction est uniquement disponible lors de la compilation pour x64.  
  
## Configuration requise  
  
|Routine|En\-tête requis \(C\)|En\-tête requis \(C\+\+\)|  
|-------------|---------------------------|-------------------------------|  
|`isnan`, `_isnanf`|\<math.h\>|\<math.h\> ou \<cmath\>|  
|`_isnan`|\<float.h\>|\< float.h \> ou \< cfloat \>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_finite, \_finitef](../../c-runtime-library/reference/finite-finitef.md)   
 [\_fpclass, \_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)