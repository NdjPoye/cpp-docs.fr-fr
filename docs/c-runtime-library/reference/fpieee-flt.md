---
title: _fpieee_flt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _fpieee_flt
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-runtime-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- fpieee_flt
- _fpieee_flt
dev_langs:
- C++
helpviewer_keywords:
- _fpieee_flt function
- exception handling, floating-point
- floating-point exception handling
- fpieee_flt function
ms.assetid: 2bc4801e-0eed-4e73-b518-215da8cc9740
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 88d05d4d8c7f403cc2702c5a0ec3b2af840bd320
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="fpieeeflt"></a>_fpieee_flt
Appelle un gestionnaire d'interruptions défini par l'utilisateur pour les exceptions à virgule flottante IEEE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _fpieee_flt(   
   unsigned long excCode,  
   struct _EXCEPTION_POINTERS *excInfo,  
   int handler(_FPIEEE_RECORD *)   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `excCode`  
 Code d’exception.  
  
 `excInfo`  
 Pointeur désignant la structure d’informations sur les exceptions Windows NT.  
  
 `handler`  
 Pointeur vers la routine du gestionnaire d'interruptions IEEE de l'utilisateur.  
  
## <a name="return-value"></a>Valeur de retour  
 La valeur de retour de `_fpieee_flt` est la valeur retournée par `handler`. Ainsi, la routine de filtre IEEE peut être utilisée dans la clause d'exception d'un mécanisme de gestion structurée des exceptions (SEH).  
  
## <a name="remarks"></a>Notes  
 La fonction `_fpieee_flt` appelle un gestionnaire d'interruptions défini par l'utilisateur pour les exceptions à virgule flottante IEEE et lui fournit toutes les informations pertinentes. Cette routine sert de filtre d'exception dans le mécanisme SEH, qui appelle votre propre gestionnaire d'exceptions IEEE si nécessaire.  
  
 La structure `_FPIEEE_RECORD`, définie dans Fpieee.h, contient des informations concernant une exception à virgule flottante IEEE. Cette structure est passée au gestionnaire d'interruptions défini par l'utilisateur par `_fpieee_flt`.  
  
|Champ _FPIEEE_RECORD|Description|  
|----------------------------|-----------------|  
|`unsigned int RoundingMode`, `unsigned int Precision`|Ces champs contiennent des informations sur l'environnement à virgule flottante au moment où l'exception s'est produite.|  
|`unsigned int Operation`|Indique le type d'opération qui a provoqué l'interruption. Si le type est une comparaison (`_FpCodeCompare`), vous pouvez fournir une des valeurs spéciales `_FPIEEE_COMPARE_RESULT` (telles que définies dans Fpieee.h) dans le champ `Result.Value`. Le type de conversion (`_FpCodeConvert`) indique que l'interruption s'est produite pendant une opération de conversion à virgule flottante. Vous pouvez examiner les types `Operand1` et `Result` pour déterminer le type de conversion tenté.|  
|`_FPIEEE_VALUE Operand1`, `_FPIEEE_VALUE Operand2`, `_FPIEEE_VALUE Result`|Ces structures indiquent les types et les valeurs du résultat et des opérandes proposés :<br /><br /> `OperandValid` Indicateur spécifiant si la valeur de réponse est valide.<br /><br /> `Format` Type de données de la valeur correspondante. Le type de format peut être retourné même si la valeur correspondante n'est pas valide.<br /><br /> `Value` Valeur de données du résultat ou de l’opérande.|  
|`_FPIEEE_EXCEPTION_FLAGS Cause`, `_FPIEEE_EXCEPTION_FLAGS Enable`, `_FPIEEE_EXCEPTION_FLAGS Status`|_FPIEEE_EXCEPTION_FLAGS contient un champ de bits par type d'exception à virgule flottante.<br /><br /> Il existe une correspondance entre ces champs et les arguments utilisés pour masquer les exceptions fournies à [_controlfp](../../c-runtime-library/reference/control87-controlfp-control87-2.md).<br /><br /> La signification exacte de chaque bit dépend du contexte :<br /><br /> `Cause` Chaque bit d’ensemble indique l’exception particulière qui a été déclenchée.<br /><br /> `Enable` Chaque bit d’ensemble indique que l’exception particulière est démasquée.<br /><br /> `Status` Chaque bit d’ensemble indique que l’exception particulière est en attente. Cela inclut les exceptions qui n'ont pas été déclenchées, car elles ont été masquées par `_controlfp`.|  
  
 Les exceptions en attente désactivées sont déclenchées lorsque vous les activez. Cela peut entraîner un comportement non défini pendant l’utilisation de `_fpieee_flt` comme filtre d’exception. Appelez toujours [_clearfp](../../c-runtime-library/reference/clear87-clearfp.md) avant d’activer les exceptions à virgule flottante.  
  
## <a name="requirements"></a>Configuration requise  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`_fpieee_flt`|\<fpieee.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## <a name="example"></a>Exemple  
  
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
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [_control87, _controlfp, \__control87_2](../../c-runtime-library/reference/control87-controlfp-control87-2.md)   
 [_controlfp_s](../../c-runtime-library/reference/controlfp-s.md)