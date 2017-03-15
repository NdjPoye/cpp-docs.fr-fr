---
title: _set_printf_count_output | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _set_printf_count_output
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
- set_printf_count_output
- _set_printf_count_output
dev_langs:
- C++
helpviewer_keywords:
- '%n format'
- set_printf_count_output function
- _set_printf_count_output function
ms.assetid: d8259ec5-764e-42d0-9169-72172e95163b
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
ms.openlocfilehash: dfb86b7d6e52168fda5ec28bd66edc29b24432e4
ms.lasthandoff: 02/24/2017

---
# <a name="setprintfcountoutput"></a>_set_printf_count_output
Active ou désactive la prise en charge du format `%n` dans les fonctions de famille [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _set_printf_count_output(  
   int enable  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `enable`  
 Valeur différente de zéro pour activer la prise en charge de `%n`, 0 pour désactiver la prise en charge de `%n`.  
  
## <a name="property-valuereturn-value"></a>Valeur de propriété/valeur de retour  
 État de la prise en charge de `%n` avant l’appel de cette fonction : valeur différente de zéro si la prise en charge de `%n` était activée, 0 si elle était désactivée.  
  
## <a name="remarks"></a>Notes  
 Pour des raisons de sécurité, la prise en charge du spécificateur de format `%n` est désactivée par défaut dans `printf` et toutes ses variantes. Si `%n` est rencontré dans une spécification de format `printf`, le comportement par défaut est d’appeler le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Le fait d’appeler `_set_printf_count_output` avec un argument différent de zéro conduit les fonctions de famille `printf` à interpréter `%n` comme décrit dans [Caractères du champ de type printf](../../c-runtime-library/printf-type-field-characters.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_set_printf_count_output`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_set_printf_count_output.c  
#include <stdio.h>  
  
int main()  
{  
   int e;  
   int i;  
   e = _set_printf_count_output( 1 );  
   printf( "%%n support was %sabled.\n",  
        e ? "en" : "dis" );  
   printf( "%%n support is now %sabled.\n",  
        _get_printf_count_output() ? "en" : "dis" );  
   printf( "12345%n6789\n", &i ); // %n format should set i to 5  
   printf( "i = %d\n", i );  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
%n support was disabled.  
%n support is now enabled.  
123456789  
i = 5  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [_get_printf_count_output](../../c-runtime-library/reference/get-printf-count-output.md)
