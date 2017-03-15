---
title: _get_printf_count_output | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _get_printf_count_output
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- get_printf_count_output
- _get_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- get_printf_count_output function
- _get_printf_count_output function
ms.assetid: 850f9f33-8319-433e-98d8-6a694200d994
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9f45a13d9911e82b2b624689fa6b9e5eb4b20d97
ms.lasthandoff: 02/24/2017

---
# <a name="getprintfcountoutput"></a>_get_printf_count_output
Indique si les fonctions de la famille [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) prennent en charge le format `%n`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _get_printf_count_output();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro si `%n` est pris en charge, 0 si `%n` n’est pas pris en charge.  
  
## <a name="remarks"></a>Notes  
 Si `%n` n’est pas pris en charge (paramétrage par défaut), la présence de `%n` dans la chaîne de format d’une des fonctions `printf` entraîne l’appel du gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si la prise en charge de `%n` est activée (voir [_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md)), `%n` se comporte comme décrit dans [Caractères du champ de type printf](../../c-runtime-library/printf-type-field-characters.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_get_printf_count_output`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [_set_printf_count_output](../../c-runtime-library/reference/set-printf-count-output.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).
