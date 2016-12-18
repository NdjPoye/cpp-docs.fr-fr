---
title: "_fpieee_flt | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_fpieee_flt"
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
  - "fpieee_flt"
  - "_fpieee_flt"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_fpieee_flt (fonction)"
  - "gestion des exceptions, virgule flottante"
  - "gestion des exceptions à virgule flottante"
  - "fpieee_flt (fonction)"
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
caps.latest.revision: 15
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _fpieee_flt
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Appelle un gestionnaire Interruptions défini par l'utilisateur pour des exceptions de virgule flottante IEEE.  
  
## Syntaxe  
  
```  
int _fpieee_flt(   
   unsigned long excCode,  
   struct _EXCEPTION_POINTERS *excInfo,  
   int handler(_FPIEEE_RECORD *)   
);  
```  
  
#### Paramètres  
 `excCode`  
 Code d'exception.  
  
 `excInfo`  
 Pointeur à la structure d'informations sur les exceptions Windows NT.  
  
 `handler`  
 Pointeur à la routine de gestionnaire Interruptions IEEE de l'utilisateur.  
  
## Valeur de retour  
 La valeur de retour de `_fpieee_flt` est la valeur renvoyée par `handler`.  Ainsi, la routine de filtre IEEE peut être utilisée dans la clause d'un mécanisme de \(SEH\) de gestion structurée des exceptions.  
  
## Notes  
 La fonction `_fpieee_flt` appelle un gestionnaire d'interruptions défini par l'utilisateur pour des exceptions à virgule flottante IEEE et lui fournit toutes les informations pertinentes.  Cette routine sert de filtre d'exceptions dans le mécanisme, qui appelle votre propre gestionnaire d'exceptions IEEE si nécessaire.  
  
 La structure `_FPIEEE_RECORD`, définie dans Fpieee.h, contient des informations concernant une exception à virgule flottante IEEE.  Cette structure est passée au gestionnaire d'interruptions défini par l'utilisateur par `_fpieee_flt`.  
  
|champ de \_FPIEEE\_RECORD|Description|  
|-------------------------------|-----------------|  
|`unsigned int RoundingMode`, `unsigned int Precision`|Ces champs contiennent des informations sur l'environnement à virgule flottante survenant au moment où l'exception s'est produite.|  
|`unsigned int Operation`|Indique le type d'opération qui a provoqué l'interruption.  Si le type est une comparaison \(`_FpCodeCompare`\), vous pouvez fournir une des valeurs spéciales d'un `_FPIEEE_COMPARE_RESULT` \(comme défini dans Fpieee.h\) dans le champ `Result.Value`.  Le type de conversion \(`_FpCodeConvert`\) indique que l'interruption s'est produite pendant une opération à virgule flottante de conversion.  Regardez `Operand1` et les types `Result` pour déterminer le type de conversion qui est tenté.|  
|`_FPIEEE_VALUE Operand1`, `_FPIEEE_VALUE Operand2`, `_FPIEEE_VALUE Result`|Ces structures contiennent les types et les valeurs du résultat et des opérandes proposés :<br /><br /> `OperandValid` Indicateur montrant si la valeur de réponse est valide.<br /><br /> `Format` Type de données de la valeur correspondante.  Type de format peut être retourné même si la valeur correspondante n'est pas valide.<br /><br /> `Value` Valeur de données de résultat ou d'opérande.|  
|`_FPIEEE_EXCEPTION_FLAGS Cause`, `_FPIEEE_EXCEPTION_FLAGS Enable`, `_FPIEEE_EXCEPTION_FLAGS Status`|\_FPIEEE\_EXCEPTION\_FLAGS contient un champ de bits par type d'exception à virgule flottante.<br /><br /> Il existe une correspondance entre ces champs et les arguments utilisés pour masquer les exceptions fournies dans [\_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md).<br /><br /> La signification exacte de chaque bit dépend du contexte :<br /><br /> `Cause` Chaque bit d'ensemble illustre l'exception particulière qui a été déclenchée.<br /><br /> `Enable` Chaque bit d'ensemble indique que l'exception particulière est actuellement démasquée.<br /><br /> `Status` Chaque bit d'ensemble indique que l'exception particulière est actuellement en attente.  Cela inclut les exceptions qui n'étaient pas déclenchées car elles ont été masquées par `_controlfp`.|  
  
 Les exceptions en attentes qui sont désactivé sont déclenchés lorsque vous l'extrayez.  Cela peut entraîner un comportement non défini en utilisant `_fpieee_flt` comme filtre d'exceptions.  Appelez toujours [\_clearfp](../../c-runtime-library/reference/clear87-clearfp.md) avant d'extraire les exceptions à virgule flottante.  
  
## Configuration requise  
  
|Fonction|En\-tête requis|  
|--------------|---------------------|  
|`_fpieee_flt`|\<fpieee.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_fpieee.c  
// This program demonstrates the implementation of  
// a user-defined floating-point exception handler using the  
// _fpieee_flt function.  
  
#include <fpieee.h>  
#include <excpt.h>  
#include <float.h>  
#include <stddef.h>  
  
int fpieee_handler( _FPIEEE_RECORD * );  
  
int fpieee_handler( _FPIEEE_RECORD *pieee )  
{  
   // user-defined ieee trap handler routine:  
   // there is one handler for all   
   // IEEE exceptions  
  
   // Assume the user wants all invalid   
   // operations to return 0.  
  
   if ((pieee->Cause.InvalidOperation) &&   
       (pieee->Result.Format == _FpFormatFp32))   
   {  
        pieee->Result.Value.Fp32Value = 0.0F;  
  
        return EXCEPTION_CONTINUE_EXECUTION;  
   }  
   else  
      return EXCEPTION_EXECUTE_HANDLER;  
}  
  
#define _EXC_MASK    \  
    _EM_UNDERFLOW  + \  
    _EM_OVERFLOW   + \  
    _EM_ZERODIVIDE + \  
    _EM_INEXACT  
  
int main( void )  
{  
   // ...  
  
   __try {  
      // unmask invalid operation exception  
      _controlfp_s(NULL, _EXC_MASK, _MCW_EM);   
  
      // code that may generate   
      // fp exceptions goes here  
   }  
   __except ( _fpieee_flt( GetExceptionCode(),  
                GetExceptionInformation(),  
                fpieee_handler ) ){  
  
      // code that gets control   
  
      // if fpieee_handler returns  
      // EXCEPTION_EXECUTE_HANDLER goes here  
  
   }  
  
   // ...  
}  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [\_control87, \_controlfp, \_\_control87\_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [\_controlfp\_s](../../c-runtime-library/reference/controlfp-s.md)