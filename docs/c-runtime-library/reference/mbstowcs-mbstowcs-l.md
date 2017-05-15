---
title: mbstowcs, _mbstowcs_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbstowcs
- _mbstowcs_l
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbstowcs
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_l function
- mbstowcs_l function
- mbstowcs function
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
caps.latest.revision: 30
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
ms.openlocfilehash: 436e581907e3b651716e819a9c82a24eed2e4b8e
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="mbstowcs-mbstowcsl"></a>mbstowcs, _mbstowcs_l
Convertit une séquence de caractères multioctets en séquence correspondante de caractères larges. Des versions plus sécurisées de ces fonctions sont disponibles. Consultez [mbstowcs_s, _mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t mbstowcs(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count   
);  
size_t _mbstowcs_l(  
   wchar_t *wcstr,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t mbstowcs(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _mbstowcs_l(  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `wcstr`  
 Adresse d’une séquence de caractères larges.  
  
 [in] `mbstr`  
 Adresse d’une séquence de caractères multioctets se terminant par un caractère Null.  
  
 [in] `count`  
 Nombre maximal de caractères multioctets à convertir.  
  
 [in] `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Si `mbstowcs` convertit correctement la chaîne source, elle retourne le nombre de caractères multioctets convertis. Si l’argument `wcstr` a la valeur `NULL`, la fonction retourne la taille exigée, en caractères larges, de la chaîne de destination. Si `mbstowcs` rencontre un caractère multioctet non valide, elle retourne -1. Si la valeur de retour est `count`, la chaîne de caractères larges ne se termine pas par un caractère Null.  
  
> [!IMPORTANT]
>  Vérifiez que `wcstr` et `mbstr` ne se chevauchent pas, et que `count` reflète correctement le nombre de caractères multioctets à convertir.  
  
## <a name="remarks"></a>Notes  
 La fonction `mbstowcs` convertit un nombre maximal de `count` caractères multioctets désignés par `mbstr` en une chaîne de caractères larges correspondants qui sont déterminés par les paramètres régionaux actuels. Il stocke la chaîne de caractères larges obtenue à l’adresse représentée par `wcstr`. Le résultat est similaire à une série d’appels à `mbtowc`. Si `mbstowcs` rencontre le caractère Null codé sur un octet ('\0') quand `count` se produit ou avant, elle convertit le caractère Null en un caractère Null large (L'\0') et s’arrête. Ainsi, la chaîne de caractères larges dans `wcstr` n’est terminée par un caractère Null que si un caractère Null est rencontré pendant la conversion. Si les séquences pointées par `wcstr` et `mbstr` se chevauchent, le comportement n’est pas défini.  
  
 Si l’argument `wcstr` a la valeur `NULL`, `mbstowcs` retourne le nombre de caractères larges qui résulterait de la conversion, sans inclure une marque de fin Null. La chaîne source doit se terminer par un caractère Null pour que la valeur correcte soit retournée. S’il est nécessaire que la chaîne de caractères larges résultante se termine par un caractère Null, ajoutez un à la valeur retournée.  
  
 Si l’argument `mbstr` a la valeur `NULL` ou que `count` est supérieur à `INT_MAX`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, errno a la valeur `EINVAL` et la fonction retourne -1.  
  
 La fonction `mbstowcs` utilise les paramètres régionaux actuels pour tout comportement dépendant des paramètres régionaux ; la fonction `_mbstowcs_l` est identique, à ceci près qu’elle utilise à la place les paramètres régionaux qui ont été passés. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 En C++, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`mbstowcs`|\<stdlib.h>|  
|`_mbstowcs_l`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_mbstowcs.c  
// compile with: /W3  
// illustrates the behavior of the mbstowcs function  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <locale.h>  
  
int main( void )  
{  
    size_t size;  
    int nChar = 2; // number of characters to convert  
    int requiredSize;  
  
    unsigned char    *pmbnull  = NULL;  
    unsigned char    *pmbhello = NULL;  
    char* localeInfo;  
  
    wchar_t *pwchello = L"\x3042\x3043"; // 2 Hiragana characters  
    wchar_t *pwc;  
  
    /* Enable the Japanese locale and codepage */  
    localeInfo = setlocale(LC_ALL, "Japanese_Japan.932");  
    printf("Locale information set to %s\n", localeInfo);  
  
    printf( "Convert to multibyte string:\n" );  
  
    requiredSize = wcstombs( NULL, pwchello, 0); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    printf("  Required Size: %d\n", requiredSize);  
  
    /* Add one to leave room for the null terminator. */  
    pmbhello = (unsigned char *)malloc( requiredSize + 1);  
    if (! pmbhello)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = wcstombs( pmbhello, pwchello, requiredSize + 1); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s  
    if (size == (size_t) (-1))  
    {  
        printf("Couldn't convert string. Code page 932 may"  
                " not be available.\n");  
        return 1;  
    }  
    printf( "  Number of bytes written to multibyte string: %u\n",  
            (unsigned int) size );  
    printf( "  Hex values of the " );  
    printf( " multibyte characters: %#.2x %#.2x %#.2x %#.2x\n",  
            pmbhello[0], pmbhello[1], pmbhello[2], pmbhello[3] );  
    printf( "  Codepage 932 uses 0x81 to 0x9f as lead bytes.\n\n");  
  
    printf( "Convert back to wide-character string:\n" );  
  
    /* Assume we don't know the length of the multibyte string.  
     Get the required size in characters, and allocate enough space. */  
  
    requiredSize = mbstowcs(NULL, pmbhello, 0); // C4996  
    /* Add one to leave room for the NULL terminator */  
    pwc = (wchar_t *)malloc( (requiredSize + 1) * sizeof( wchar_t ));  
    if (! pwc)  
    {  
        printf("Memory allocation failure.\n");  
        return 1;  
    }  
    size = mbstowcs( pwc, pmbhello, requiredSize + 1); // C4996  
    if (size == (size_t) (-1))  
    {  
       printf("Couldn't convert string--invalid multibyte character.\n");  
    }  
    printf( "  Characters converted: %u\n", (unsigned int)size );  
    printf( "  Hex value of first 2" );  
    printf( " wide characters: %#.4x %#.4x\n\n", pwc[0], pwc[1] );  
    free(pwc);  
    free(pmbhello);  
}  
```  
  
```Output  
Locale information set to Japanese_Japan.932  
Convert to multibyte string:  
  Required Size: 4  
  Number of bytes written to multibyte string: 4  
  Hex values of the  multibyte characters: 0x82 0xa0 0x82 0xa1  
  Codepage 932 uses 0x81 to 0x9f as lead bytes.  
  
Convert back to wide-character string:  
  Characters converted: 2  
  Hex value of first 2 wide characters: 0x3042 0x3043  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)
