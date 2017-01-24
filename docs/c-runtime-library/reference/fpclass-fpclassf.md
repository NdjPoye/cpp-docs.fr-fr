---
title: "_fpclass, _fpclassf | Microsoft Docs"
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
  - "_fpclass"
  - "_fpclassf"
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
  - "fpclass"
  - "_fpclass"
  - "_fpclassf"
  - "math/_fpclass"
  - "float/_fpclass"
  - "math/_fpclassf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fpclass (fonction)"
  - "chiffres à virgule flottante, représentation IEEE"
  - "_fpclass (fonction)"
  - "_fpclassf (fonction)"
ms.assetid: 2774872d-3543-446f-bc72-db85f8b95a6b
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fpclass, _fpclassf
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Retourne une valeur indiquant la classification de l’argument à virgule flottante.  
  
## Syntaxe  
  
```  
int _fpclass(   
   double x   
);  
  
int _fpclassf(   
   float x   
); /* x64 only */  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante à tester.  
  
## Valeur de retour  
 Le `_fpclass` et `_fpclassf` fonctions retournent une valeur entière qui indique le classement de l’argument à virgule flottante `x`. La classification peut avoir une des valeurs suivantes, définies dans \< float.h \>.  
  
|Valeur|Description|  
|------------|-----------------|  
|`_FPCLASS_SNAN`|NaN de signalisation|  
|`_FPCLASS_QNAN`|Valeur NaN silencieuse|  
|`_FPCLASS_NINF`|Infini négatif \(\-INF\)|  
|`_FPCLASS_NN`|Négatif normalisées non nulle|  
|`_FPCLASS_ND`|Négatif dénormalisé|  
|`_FPCLASS_NZ`|Un zéro négatif \(\-0\)|  
|`_FPCLASS_PZ`|0 positif \(\+ 0\)|  
|`_FPCLASS_PD`|Positif dénormalisé|  
|`_FPCLASS_PN`|Positif normalisées non nulle|  
|`_FPCLASS_PINF`|Infini positif \(\+ INF\)|  
  
## Notes  
 Le `_fpclass` et `_fpclassf` les fonctions sont spécifiques de Microsoft. Ils sont similaires aux [fpclassify](../../c-runtime-library/reference/fpclassify.md), mais retourne des informations détaillées sur l’argument. Le `_fpclassf` fonction est uniquement disponible lors de la compilation pour le x64 plate\-forme.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fpclass`|\<float.h\>|  
  
 Pour plus d’informations de compatibilité et de la conformité, consultez [compatibilité](../../c-runtime-library/compatibility.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [isNaN, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [fpclassify](../../c-runtime-library/reference/fpclassify.md)