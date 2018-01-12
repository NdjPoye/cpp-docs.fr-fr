---
title: _stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _stricmp_l
- _mbsicmp
- _wcsicmp
- _mbsicmp_l
- _stricmp
- _wcsicmp_l
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
- ntoskrnl.exe
- ucrtbase.dll
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _ftcsicmp
- _stricmp
- wcsicmp_l
- _wcsicmp
- _tcsicmp
- _strcmpi
- stricmp_l
- _mbsicmp
- _fstricmp
- mbsicmp_l
- mbsicmp
dev_langs: C++
helpviewer_keywords:
- _wcsicmp function
- _stricmp_l function
- fstricmp function
- _tcsicmp function
- ftcsicmp function
- string comparison [C++], lowercase
- _wcsicmp_l function
- _fstricmp function
- strings [C++], comparing
- mbsicmp function
- _ftcsicmp function
- _mbsicmp_l function
- wcsicmp_l function
- _stricmp function
- _mbsicmp function
- tcsicmp function
- stricmp_l function
- mbsicmp_l function
- _strcmpi function
ms.assetid: 0e1ee515-0d75-435a-a445-8875d4669b50
caps.latest.revision: "28"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 15b581d0d47da824f1faaade1214d1320e29bb03
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="stricmp-wcsicmp-mbsicmp-stricmpl-wcsicmpl-mbsicmpl"></a>_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l
Effectue une comparaison de chaînes sans tenir compte de la casse.  
  
> [!IMPORTANT]
>  `_mbsicmp` et `_mbsicmp_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _stricmp(  
   const char *string1,  
   const char *string2   
);  
int _wcsicmp(  
   const wchar_t *string1,  
   const wchar_t *string2   
);  
int _mbsicmp(  
   const unsigned char *string1,  
   const unsigned char *string2   
);  
int _stricmp_l(  
   const char *string1,  
   const char *string2,  
   _locale_t locale  
);  
int _wcsicmp_l(  
   const wchar_t *string1,  
   const wchar_t *string2,  
   _locale_t locale  
);  
int _mbsicmp_l(  
   const unsigned char *string1,  
   const unsigned char *string2,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `string1, string2`  
 Chaîne terminée par Null à comparer.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 La valeur de retour indique la relation de `string1` avec `string2` comme suit.  
  
|Valeur de retour|Description|  
|------------------|-----------------|  
|< 0|`string1` inférieure à `string2`|  
|0|`string1` identique à `string2`|  
|> 0|`string1` supérieur à `string2`|  
  
 En cas d’erreur, `_mbsicmp` retourne `_NLSCMPERROR`, qui est défini dans \<string.h> et \<mbstring.h>.  
  
## <a name="remarks"></a>Notes  
 La fonction `_stricmp` effectue une comparaison ordinale de `string1` et de `string2` après la conversion de chaque caractère en minuscule, et retourne une valeur qui indique leur relation. `_stricmp` diffère de `_stricoll` en cela que la comparaison de `_stricmp` est affectée seulement par `LC_CTYPE`, qui détermine quels caractères sont en majuscule et en minuscule. La fonction `_stricoll` compare des chaînes en fonction à la fois des catégories `LC_CTYPE` et `LC_COLLATE` des paramètres régionaux, ce qui comprend la casse et l'ordre de classement. Pour plus d’informations sur la catégorie `LC_COLLATE`, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) et[Catégories de paramètres régionaux](../../c-runtime-library/locale-categories.md). Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux actuels pour le comportement dépendant des paramètres régionaux. Les versions avec le suffixe sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux passés en entrée. Si les paramètres régionaux n'ont pas été définis, les paramètres régionaux C sont utilisés. Pour plus d’informations, consultez [Locale](../../c-runtime-library/locale.md).  
  
> [!NOTE]
>  `_stricmp` équivaut à `_strcmpi`. Elles peuvent être utilisés indifféremment, mais `_stricmp` est la norme préférée.  
  
 La fonction `_strcmpi` est équivalente à `_stricmp` et elle est fournie seulement à des fins de compatibilité descendante.  
  
 Comme `_stricmp` effectue des comparaisons de minuscules, elle peut aboutir à un comportement inattendu.  
  
 Pour illustrer la façon dont la conversion de la casse par `_stricmp` affecte le résultat d'une comparaison, supposons que vous avez les deux chaînes JOHNSTON et JOHN_HENRY. La chaîne JOHN_HENRY est considérée comme inférieure à JOHNSTON, car le caractère « _ » a une valeur ASCII inférieure à un S minuscule. En fait, tout caractère dont la valeur ASCII est comprise entre 91 et 96 est considérée comme inférieure à n’importe quelle lettre.  
  
 Si la fonction [strcmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md) est utilisée à la place de `_stricmp`, la chaîne JOHN_HENRY est supérieure à JOHNSTON.  
  
 `_wcsicmp` et `_mbsicmp` sont des versions à caractères larges et à caractères multioctets de `_stricmp`. Les arguments et la valeur de retour de `_wcsicmp` sont des chaînes de caractères larges ; ceux de `_mbsicmp` sont des chaînes de caractères multioctets. `_mbsicmp` reconnaît les séquences de caractères multioctets selon la page de codes multioctets active et retourne `_NLSCMPERROR` en cas d'erreur. Pour plus d’informations, consultez [Pages de codes](../../c-runtime-library/code-pages.md). Ces trois fonctions se comportent sinon de façon identique.  
  
 `_wcsicmp` et `wcscmp` se comportent de façon identique, sauf que `wcscmp` ne convertit pas ses arguments en minuscules avant de les comparer. `_mbsicmp` et `_mbscmp` se comportent de façon identique, sauf que `_mbscmp` ne convertit pas ses arguments en minuscules avant de les comparer.  
  
 Vous devez appeler [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md) pour que `_wcsicmp` fonctionne avec des caractères Latin 1. Les paramètres régionaux C sont appliqués par défaut et par exemple, « ä » n'est pas considéré comme étant égal à « Ä ». Appelez `setlocale` avec n'importe quels paramètres régionaux autres que les paramètres régionaux C avant d'appeler `_wcsicmp`. L'exemple suivant montre comment `_wcsicmp` est sensible aux paramètres régionaux :  
  
```  
// crt_stricmp_locale.c  
#include <string.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main() {  
   setlocale(LC_ALL,"C");   // in effect by default  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare fails  
   setlocale(LC_ALL,"");  
   printf("\n%d",_wcsicmp(L"ä", L"Ä"));   // compare succeeds  
}  
```  
  
 Une autre solution consiste à appeler [_create_locale, _wcreate_locale](../../c-runtime-library/reference/create-locale-wcreate-locale.md) et à passer l’objet de paramètres régionaux retourné en tant que paramètre à `_wcsicmp_l`.  
  
 Toutes ces fonctions valident leurs paramètres. Si `string1` ou `string2` sont des pointeurs Null, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `_NLSCMPERROR` et définissent `errno` avec la valeur `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsicmp`|`_stricmp`|`_mbsicmp`|`_wcsicmp`|  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_stricmp`, `_stricmp_l`|\<string.h>|  
|`_wcsicmp`, `_wcsicmp_l`|\<string.h> ou \<wchar.h>|  
|`_mbsicmp`, `_mbsicmp_l`|\<mbstring.h>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_stricmp.c  
  
#include <string.h>  
#include <stdio.h>  
#include <stdlib.h>  
  
char string1[] = "The quick brown dog jumps over the lazy fox";  
char string2[] = "The QUICK brown dog jumps over the lazy fox";  
  
int main( void )  
{  
   char tmp[20];  
   int result;  
  
   // Case sensitive  
   printf( "Compare strings:\n   %s\n   %s\n\n", string1, string2 );  
   result = strcmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   strcmp:   String 1 is %s string 2\n", tmp );  
  
   // Case insensitive (could use equivalent _stricmp)  
   result = _stricmp( string1, string2 );  
   if( result > 0 )  
      strcpy_s( tmp, _countof(tmp), "greater than" );  
   else if( result < 0 )  
      strcpy_s( tmp, _countof(tmp), "less than" );  
   else  
      strcpy_s( tmp, _countof(tmp), "equal to" );  
   printf( "   _stricmp:  String 1 is %s string 2\n", tmp );  
}  
```  
  
```Output  
Compare strings:  
   The quick brown dog jumps over the lazy fox  
   The QUICK brown dog jumps over the lazy fox  
  
   strcmp:   String 1 is greater than string 2  
   _stricmp:  String 1 is equal to string 2  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [_memicmp, _memicmp_l](../../c-runtime-library/reference/memicmp-memicmp-l.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcoll, fonctions](../../c-runtime-library/strcoll-functions.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)