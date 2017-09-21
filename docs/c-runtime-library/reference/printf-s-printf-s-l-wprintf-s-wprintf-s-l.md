---
title: printf_s, _printf_s_l, wprintf_s, _wprintf_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _printf_s_l
- wprintf_s
- _wprintf_s_l
- printf_s
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
apitype: DLLExport
f1_keywords:
- wprintf_s
- printf_s
dev_langs:
- C++
helpviewer_keywords:
- wprintf_s function
- tprintf_s function
- _tprintf_s function
- printf_s_l function
- printf_s function
- _printf_s_l function
- printf function, format specification fields
- printf function, using
- _tprintf_s_l function
- wprintf_s_l function
- formatted text [C++]
- tprintf_s_l function
- _wprintf_s_l function
ms.assetid: 044ebb2e-5cc1-445d-bb4c-f084b405615b
caps.latest.revision: 21
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 008ecd864959078951a3671a318abfa6e593bd49
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="printfs-printfsl-wprintfs-wprintfsl"></a>printf_s, _printf_s_l, wprintf_s, _wprintf_s_l
Imprime une sortie mise en forme dans le flux de sortie standard. Ces versions de [printf, _printf_l, wprintf, _wprintf_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int printf_s(  
   const char *format [,  
   argument]...   
);  
int _printf_s_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wprintf_s(  
   const wchar_t *format [,  
   argument]...   
);  
int _wprintf_s_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `format`  
 Contrôle de format.  
  
 `argument`  
 Arguments facultatifs.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de caractères imprimés ou une valeur négative si une erreur se produit.  
  
## <a name="remarks"></a>Notes  
 La fonction `printf_s` met en forme et imprime une série de caractères et de valeurs dans le flux de sortie standard, `stdout`. Si des arguments suivent la chaîne de *format*, la chaîne `format` doit contenir des spécifications qui déterminent le format de sortie des arguments.  
  
 La principale différence entre `printf_s` et `printf` est que `printf_s` vérifie si la chaîne de format comporte des caractères de mise en forme valides, alors que `printf` vérifie uniquement si la chaîne de format est un pointeur Null. Si l’une des vérifications échoue, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, la fonction retourne -1 et définit `errno` avec la valeur `EINVAL`.  
  
 Pour plus d’informations sur `errno` et les codes d’erreur, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 `printf_s`et `fprintf_s` se comportent de façon identique, sauf que `printf_s` écrit la sortie vers `stdout` plutôt qu’à une destination de type `FILE`. Pour plus d’informations, consultez [fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](../../c-runtime-library/reference/fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md).  
  
 `wprintf_s` est une version à caractères larges de `printf_s` ; `format` est une chaîne de caractères larges. `wprintf_s` et `printf_s` se comportent de la même façon si le flux est ouvert en mode ANSI. `printf_s` ne prend actuellement pas en charge la sortie vers un flux UNICODE.  
  
 Les versions de ces fonctions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent les paramètres régionaux passés au lieu des paramètres régionaux du thread actuel.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_unicode défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tprintf_s`|`printf_s`|`printf_s`|`wprintf_s`|  
|`_tprintf_s_l`|`_printf_s_l`|`_printf_s_l`|`_wprintf_s_l`|  
  
 L’argument `format` se compose de caractères ordinaires, de séquences d’échappement et (si des arguments suivent `format`) de spécifications de format. Les caractères ordinaires et les séquences d’échappement sont copiés dans `stdout` dans leur ordre d’apparition. Par exemple, la ligne  
  
```  
printf_s("Line one\n\t\tLine two\n");   
```  
  
 génère la sortie  
  
```  
Line one  
        Line two  
```  
  
 Les [spécifications de format](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md) commencent toujours par un symbole de pourcentage (`%`) et sont lues de gauche à droite. Quand la fonction `printf_s` rencontre la première spécification de format (le cas échéant), elle convertit la valeur du premier argument après `format` et la sort en conséquence. La deuxième spécification de format entraîne la conversion et la sortie du deuxième argument, et ainsi de suite. S’il y a plus d’arguments que de spécifications de format, les arguments en trop sont ignorés. Les résultats sont indéfinis s’il n’y a pas assez d’arguments pour toutes les spécifications de format.  
  
> [!IMPORTANT]
>  Assurez-vous que `format` n'est pas une chaîne définie par l'utilisateur.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`printf_s`, `_printf_s_l`|\<stdio.h>|  
|`wprintf_s`, `_wprintf_s_l`|\<stdio.h> ou \<wchar.h>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] . Les handles de flux standard associés à la console (`stdin`, `stdout` et `stderr`) doivent être redirigés pour que les fonctions Runtime C puissent les utiliser dans les applications du [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_printf_s.c  
/* This program uses the printf_s and wprintf_s functions  
 * to produce formatted output.  
 */  
  
#include <stdio.h>  
  
int main( void )  
{  
   char   ch = 'h', *string = "computer";  
   int    count = -9234;  
   double fp = 251.7366;  
   wchar_t wch = L'w', *wstring = L"Unicode";  
  
   /* Display integers. */  
   printf_s( "Integer formats:\n"  
           "   Decimal: %d  Justified: %.6d  Unsigned: %u\n",  
           count, count, count );  
  
   printf_s( "Decimal %d as:\n   Hex: %Xh  C hex: 0x%x  Octal: %o\n",  
            count, count, count, count );  
  
   /* Display in different radixes. */  
   printf_s( "Digits 10 equal:\n   Hex: %i  Octal: %i  Decimal: %i\n",  
            0x10, 010, 10 );  
  
   /* Display characters. */  
  
   printf_s("Characters in field (1):\n%10c%5hc%5C%5lc\n", ch, ch, wch, wch);  
   wprintf_s(L"Characters in field (2):\n%10C%5hc%5c%5lc\n", ch, ch, wch, wch);  
  
   /* Display strings. */  
  
   printf_s("Strings in field (1):\n%25s\n%25.4hs\n   %S%25.3ls\n",  
   string, string, wstring, wstring);  
   wprintf_s(L"Strings in field (2):\n%25S\n%25.4hs\n   %s%25.3ls\n",  
       string, string, wstring, wstring);  
  
   /* Display real numbers. */  
   printf_s( "Real numbers:\n   %f %.2f %e %E\n", fp, fp, fp, fp );  
  
   /* Display pointer. */  
   printf_s( "\nAddress as:   %p\n", &count);  
  
}  
```  
  
## <a name="sample-output"></a>Résultat de l'exemple  
  
```  
Integer formats:  
   Decimal: -9234  Justified: -009234  Unsigned: 4294958062  
Decimal -9234 as:  
   Hex: FFFFDBEEh  C hex: 0xffffdbee  Octal: 37777755756  
Digits 10 equal:  
   Hex: 16  Octal: 8  Decimal: 10  
Characters in field (1):  
         h    h    w    w  
Characters in field (2):  
         h    h    w    w  
Strings in field (1):  
                 computer  
                     comp  
   Unicode                      Uni  
Strings in field (2):  
                 computer  
                     comp  
   Unicode                      Uni  
Real numbers:  
   251.736600 251.74 2.517366e+002 2.517366E+002  
  
Address as:   0012FF78  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [vprintf, fonctions](../../c-runtime-library/vprintf-functions.md)