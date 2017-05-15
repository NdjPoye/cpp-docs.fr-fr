---
title: strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsncpy_s_l
- wcsncpy_s
- _strncpy_s_l
- strncpy_s
- _mbsncpy_s
- _wcsncpy_s_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tcsncpy_s
- _wcsncpy_s_l
- strncpy_s
- _strncpy_s_l
- wcsncpy_s
- _tcsncpy_s_l
dev_langs:
- C++
helpviewer_keywords:
- _wcsncpy_s_l function
- _mbsnbcpy_s function
- _tcsncpy_s_l function
- mbsncpy_s function
- strncpy_s_l function
- _strncpy_s_l function
- strncpy_s function
- mbsncpy_s_l function
- wcsncpy_s function
- copying strings
- strings [C++], copying
- _mbsnbcpy_s_l function
- _tcsncpy_s function
- wcsncpy_s_l function
ms.assetid: a971c800-94d1-4d88-92f3-a2fe236a4546
caps.latest.revision: 47
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
ms.openlocfilehash: 3d0d2f76b88f1518b24860b3e8efb7c2214c2845
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="strncpys-strncpysl-wcsncpys-wcsncpysl-mbsncpys-mbsncpysl"></a>strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l
Copie les caractères d’une chaîne dans une autre.  Ces versions de [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
> [!IMPORTANT]
>  `_mbsncpy_s` et `_mbsncpy_s_l` ne peuvent pas être utilisées dans les applications qui s'exécutent dans Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t strncpy_s(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count  
);  
errno_t _strncpy_s_l(  
   char *strDest,  
   size_t numberOfElements,  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t wcsncpy_s(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count   
);  
errno_t _wcsncpy_s_l(  
   wchar_t *strDest,  
   size_t numberOfElements,  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
);  
errno_t _mbsncpy_s(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count   
);  
errno_t _mbsncpy_s_l(  
   unsigned char *strDest,  
   size_t numberOfElements,  
   const unsigned char *strSource,  
   size_t count,  
   locale_t locale  
);  
template <size_t size>  
errno_t strncpy_s(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count  
); // C++ only  
template <size_t size>  
errno_t _strncpy_s_l(  
   char (&strDest)[size],  
   const char *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t wcsncpy_s(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcsncpy_s_l(  
   wchar_t (&strDest)[size],  
   const wchar_t *strSource,  
   size_t count,  
   _locale_t locale  
); // C++ only  
template <size_t size>  
errno_t _mbsncpy_s(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbsncpy_s_l(  
   unsigned char (&strDest)[size],  
   const unsigned char *strSource,  
   size_t count,  
   locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 `strDest`  
 Chaîne de destination.  
  
 `numberOfElements`  
 Taille de la chaîne de destination, en caractères.  
  
 `strSource`  
 Chaîne source.  
  
 `count`  
 Nombre de caractères à copier, ou [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l’opération réussit, `STRUNCATE` si une troncation s’est produite, code d’erreur dans tout autre cas.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`strDest`|`numberOfElements`|`strSource`|Valeur de retour|Contenu de `strDest`|  
|---------------|------------------------|-----------------|------------------|---------------------------|  
|`NULL`|any|any|`EINVAL`|non modifié|  
|any|any|`NULL`|`EINVAL`|`strDest`[0] a la valeur 0|  
|indifférent|0|any|`EINVAL`|non modifié|  
|non `NULL`|trop petit|indifférent|`ERANGE`|`strDest`[0] a la valeur 0|  
  
## <a name="remarks"></a>Notes  
 Ces fonctions essaient de copier les `D` premiers caractères de `strSource` dans `strDest`, `D` représentant la valeur la plus petite de `count` et la longueur de `strSource`. Si ces `D` caractères tiennent dans `strDest` (dont la taille est indiquée par `numberOfElements`) et s’il reste de l’espace pour un terminateur null, ces caractères sont copiés et un caractère null de fin est ajouté ; sinon, `strDest`[0] est défini avec le caractère null et le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Il existe une exception au paragraphe ci-dessus. Si `count` a la valeur `_TRUNCATE`, un maximum de caractères de `strSource` sont copiés dans `strDest` tout en laissant de l’espace pour le caractère null de fin, qui est toujours ajouté.  
  
 Par exemple :  
  
 `char dst[5];`  
  
 `strncpy_s(dst, 5, "a long string", 5);`  
  
 signifie que nous demandons à `strncpy_s` de copier cinq caractères dans une mémoire tampon d’une longueur de cinq octets, ce qui ne permet pas d’accueillir le terminateur null. De ce fait, `strncpy_s` remet la chaîne à zéro et appelle le gestionnaire de paramètre non valide.  
  
 Si le comportement de la troncation est nécessaire, utilisez `_TRUNCATE` ou (`size` - 1) :  
  
 `strncpy_s(dst, 5, "a long string", _TRUNCATE);`  
  
 `strncpy_s(dst, 5, "a long string", 4);`  
  
 Contrairement à `strncpy`, si la valeur de `count` est supérieure à la longueur de `strSource`, notez que la chaîne de destination n’est PAS remplie de caractères null sur toute la longueur de `count`.  
  
 Le comportement de `strncpy_s` n'est pas défini si les chaînes source et de destination se chevauchent.  
  
 Si `strDest` ou `strSource` a la valeur `NULL`, ou si `numberOfElements` a la valeur 0, le gestionnaire de paramètre non valide est appelé. Si l'exécution est autorisée à continuer, cette fonction retourne `EINVAL` et définit à `errno` à `EINVAL`.  
  
 `wcsncpy_s` et `_mbsncpy_s` sont des versions à caractères larges et à caractères multioctets de `strncpy_s`. Les arguments et la valeur de retour de `wcsncpy_s` et `mbsncpy_s` varient en conséquence. Sinon, ces six fonctions se comportent à l'identique.  
  
 La valeur de sortie est affectée par la valeur du paramètre de catégorie `LC_CTYPE` des paramètres régionaux. Pour plus d’informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement (ce qui évite d’avoir à spécifier un argument taille) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 Les versions debug de ces fonctions remplissent d'abord la mémoire tampon avec 0xFD. Pour désactiver ce comportement, utilisez [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tcsncpy_s`|`strncpy_s`|`_mbsnbcpy_s`|`wcsncpy_s`|  
|`_tcsncpy_s_l`|`_strncpy_s_l`|`_mbsnbcpy_s_l`|`_wcsncpy_s_l`|  
  
> [!NOTE]
>  Les fonctions _strncpy_s_l, `_wcsncpy_s_l` et `_mbsncpy_s_l` n’ont aucune dépendance vis-à-vis des paramètres régionaux ; elles sont uniquement fournies pour `_tcsncpy_s_l` et ne sont pas destinées à être appelées directement.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`strncpy_s`, `_strncpy_s_l`|\<string.h>|  
|`wcsncpy_s`, `_wcsncpy_s_l`|\<string.h> ou \<wchar.h>|  
|`_mbsncpy_s`, `_mbsncpy_s_l`|\<mbstring.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_strncpy_s_1.cpp  
// compile with: /MTd  
  
// these #defines enable secure template overloads  
// (see last part of Examples() below)  
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1   
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <string.h>  
#include <crtdbg.h>  // For _CrtSetReportMode  
#include <errno.h>  
  
// This example uses a 10-byte destination buffer.  
  
errno_t strncpy_s_tester( const char * src,  
                          int count )  
{  
   char dest[10];  
  
   printf( "\n" );  
  
   if ( count == _TRUNCATE )  
      printf( "Copying '%s' to %d-byte buffer dest with truncation semantics\n",  
               src, _countof(dest) );  
   else  
      printf( "Copying %d chars of '%s' to %d-byte buffer dest\n",  
              count, src, _countof(dest) );  
  
   errno_t err = strncpy_s( dest, _countof(dest), src, count );  
  
   printf( "    new contents of dest: '%s'\n", dest );  
  
   return err;  
}  
  
void Examples()  
{  
   strncpy_s_tester( "howdy", 4 );  
   strncpy_s_tester( "howdy", 5 );  
   strncpy_s_tester( "howdy", 6 );  
  
   printf( "\nDestination buffer too small:\n" );  
   strncpy_s_tester( "Hi there!!", 10 );  
  
   printf( "\nTruncation examples:\n" );  
  
   errno_t err = strncpy_s_tester( "How do you do?", _TRUNCATE );  
   printf( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   err = strncpy_s_tester( "Howdy.", _TRUNCATE );  
   printf( "    truncation %s occur\n", err == STRUNCATE ? "did"  
                                                       : "did not" );  
  
   printf( "\nSecure template overload example:\n" );  
  
   char dest[10];  
   strncpy( dest, "very very very long", 15 );  
   // With secure template overloads enabled (see #defines at  
   // top of file), the preceding line is replaced by  
   //    strncpy_s( dest, _countof(dest), "very very very long", 15 );  
   // Instead of causing a buffer overrun, strncpy_s invokes  
   // the invalid parameter handler.  
   // If secure template overloads were disabled, strncpy would  
   // copy 15 characters and overrun the dest buffer.  
   printf( "    new contents of dest: '%s'\n", dest );  
}  
  
void myInvalidParameterHandler(  
   const wchar_t* expression,  
   const wchar_t* function,   
   const wchar_t* file,   
   unsigned int line,   
   uintptr_t pReserved)  
{  
   wprintf(L"Invalid parameter handler invoked: %s\n", expression);  
}  
  
int main( void )  
{  
   _invalid_parameter_handler oldHandler, newHandler;  
  
   newHandler = myInvalidParameterHandler;  
   oldHandler = _set_invalid_parameter_handler(newHandler);  
   // Disable the message box for assertions.  
   _CrtSetReportMode(_CRT_ASSERT, 0);  
  
   Examples();  
}  
```  
  
```Output  
Copying 4 chars of 'howdy' to 10-byte buffer dest  
    new contents of dest: 'howd'  
  
Copying 5 chars of 'howdy' to 10-byte buffer dest  
    new contents of dest: 'howdy'  
  
Copying 6 chars of 'howdy' to 10-byte buffer dest  
    new contents of dest: 'howdy'  
  
Destination buffer too small:  
  
Copying 10 chars of 'Hi there!!' to 10-byte buffer dest  
Invalid parameter handler invoked: (L"Buffer is too small" && 0)  
    new contents of dest: ''  
  
Truncation examples:  
  
Copying 'How do you do?' to 10-byte buffer dest with truncation semantics  
    new contents of dest: 'How do yo'  
    truncation did occur  
  
Copying 'Howdy.' to 10-byte buffer dest with truncation semantics  
    new contents of dest: 'Howdy.'  
    truncation did not occur  
  
Secure template overload example:  
Invalid parameter handler invoked: (L"Buffer is too small" && 0)  
    new contents of dest: ''  
```  
  
## <a name="example"></a>Exemple  
  
```  
// crt_strncpy_s_2.c  
// contrasts strncpy and strncpy_s  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   char a[20] = "test";  
   char s[20];  
  
   // simple strncpy usage:  
  
   strcpy_s( s, 20, "dogs like cats" );  
   printf( "Original string:\n   '%s'\n", s );  
  
   // Here we can't use strncpy_s since we don't   
   // want null termination  
   strncpy( s, "mice", 4 );  
   printf( "After strncpy (no null-termination):\n   '%s'\n", s );  
   strncpy( s+5, "love", 4 );  
   printf( "After strncpy into middle of string:\n   '%s'\n", s );  
  
   // If we use strncpy_s, the string is terminated   
   strncpy_s( s, _countof(s), "mice", 4 );  
   printf( "After strncpy_s (with null-termination):\n   '%s'\n", s );  
  
}  
```  
  
```Output  
Original string:  
   'dogs like cats'  
After strncpy (no null-termination):  
   'mice like cats'  
After strncpy into middle of string:  
   'mice love cats'  
After strncpy_s (with null-termination):  
   'mice'  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbsnbcpy, _mbsnbcpy_l](../../c-runtime-library/reference/mbsnbcpy-mbsnbcpy-l.md)   
 [strcat_s, wcscat_s, _mbscat_s](../../c-runtime-library/reference/strcat-s-wcscat-s-mbscat-s.md)   
 [strcmp, wcscmp, _mbscmp](../../c-runtime-library/reference/strcmp-wcscmp-mbscmp.md)   
 [strcpy_s, wcscpy_s, _mbscpy_s](../../c-runtime-library/reference/strcpy-s-wcscpy-s-mbscpy-s.md)   
 [strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](../../c-runtime-library/reference/strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md)   
 [strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](../../c-runtime-library/reference/strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)   
 [_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](../../c-runtime-library/reference/strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)   
 [strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](../../c-runtime-library/reference/strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)   
 [strspn, wcsspn, _mbsspn, _mbsspn_l](../../c-runtime-library/reference/strspn-wcsspn-mbsspn-mbsspn-l.md)
