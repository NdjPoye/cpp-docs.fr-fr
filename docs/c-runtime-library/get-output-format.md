---
title: _get_output_format | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_output_format
apilocation:
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcrt.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
apitype: DLLExport
f1_keywords:
- get_output_format
- _get_output_format
dev_langs:
- C++
helpviewer_keywords:
- output formatting
- get_output_format function
- _get_output_format function
ms.assetid: 0ce42f3b-3479-41c4-bcbf-1d21f7ee37e7
caps.latest.revision: 13
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 389704142fe6d6f5806542cd2bdf6cdd4482172b
ms.lasthandoff: 03/29/2017

---
# <a name="getoutputformat"></a>_get_output_format
Obtient la valeur actuelle de l’indicateur de format de sortie.  
  
> [!IMPORTANT]
>  Cette fonction est obsolète. Depuis Visual Studio 2015, elle n’est pas disponible dans la bibliothèque CRT.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned int _get_output_format();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 La valeur actuelle de l’indicateur de format de sortie.  
  
## <a name="remarks"></a>Notes  
 L’indicateur de format de sortie contrôle les fonctionnalités de l’E/S mise en forme. Pour l’instant, l’indicateur a deux valeurs possibles : 0 et `_TWO_DIGIT_EXPONENT`. Si `_TWO_DIGIT_EXPONENT` est défini, les nombres à virgule flottante sont générés avec seulement deux chiffres dans l’exposant, sauf si un troisième chiffre est requis par la taille de l’exposant. Si l’indicateur est défini sur zéro, la virgule flottante générée affiche trois chiffres dans l’exposant, en utilisant si nécessaire des zéros pour compléter la valeur sur trois chiffres.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_get_output_format`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="see-also"></a>Voir aussi  
[Syntaxe de spécification de format : fonctions printf et wprintf](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)  
 [printf, _printf_l, wprintf, _wprintf_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [printf_s, _printf_s_l, wprintf_s, _wprintf_s_l](../c-runtime-library/reference/printf-s-printf-s-l-wprintf-s-wprintf-s-l.md)   
 [_set_output_format](../c-runtime-library/set-output-format.md)  

