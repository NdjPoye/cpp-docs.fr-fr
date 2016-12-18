---
title: "_finite, _finitef | Microsoft Docs"
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
  - "_finite"
  - "_finitef"
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
  - "finite"
  - "_finite"
  - "_finitef"
  - "math/_finite"
  - "math/_finitef"
  - "float/_finite"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "finite (fonction)"
  - "_finite (fonction)"
  - "_finitef, fonction"
ms.assetid: 5a7d7ca7-befb-4e1f-831d-28713c6eb805
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _finite, _finitef
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Détermine si une valeur à virgule flottante est finie.  
  
## Syntaxe  
  
```  
int _finite(   
   double x   
);  
  
int _finitef(   
   float x   
); /* x64 and ARM/ARM64 only */  
```  
  
#### Paramètres  
 `x`  
 Valeur à virgule flottante à tester.  
  
## Valeur de retour  
 `_finite` et `_finitef` retournent tous deux une valeur non nulle si l’argument *x* est fini, autrement dit si –INF \< `x` \< \+INF. La valeur 0 est retournée si l’argument est infini ou n’est pas un nombre.  
  
## Notes  
 Le `_finite` et `_finitef` les fonctions sont spécifiques de Microsoft. Le `_finitef` fonction est uniquement disponible lorsque compilé pour x86, ARM ou ARM64 plates\-formes.  
  
## Configuration requise  
  
|Fonction|En\-tête requis \(C\)|En\-tête requis \(C\+\+\)|  
|--------------|---------------------------|-------------------------------|  
|`_finite`|\<float.h\> ou \<math.h\>|\<float.h\>, \<math.h\>, \<cfloat\> ou \<cmath\>|  
|`_finitef`|\<math.h\>|\<math.h\> ou \<cmath\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Équivalent .NET Framework  
 [System::Double::IsInfinity](https://msdn.microsoft.com/en-us/library/system.double.isinfinity.aspx)  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [isNaN, \_isnan, \_isnanf](../../c-runtime-library/reference/isnan-isnan-isnanf.md)   
 [\_fpclass, \_fpclassf](../../c-runtime-library/reference/fpclass-fpclassf.md)