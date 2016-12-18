---
title: "mbstowcs, _mbstowcs_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "mbstowcs"
  - "_mbstowcs_l"
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
  - "api-ms-win-crt-convert-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "mbstowcs"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_mbstowcs_l (fonction)"
  - "mbstowcs (fonction)"
  - "mbstowcs_l (fonction)"
ms.assetid: 96696b27-e068-4eeb-8006-3f7a0546ae6d
caps.latest.revision: 30
caps.handback.revision: 28
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# mbstowcs, _mbstowcs_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Convertit une séquence de caractères multioctets en une séquence correspondante de caractères larges.  Des versions plus sécurisées de ces fonctions sont disponibles ; consultez [mbstowcs\_s, \_mbstowcs\_s\_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md).  
  
## Syntaxe  
  
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
  
#### Paramètres  
 \[out\] `wcstr`  
 L'adresse d'une séquence de caractères larges.  
  
 \[in\] `mbstr`  
 L'adresse d'une séquence de caractères multioctets terminés par null.  
  
 \[in\] `count`  
 Nombre maximal de caractères multioctets à convertir.  
  
 \[in\] `locale`  
 Paramètres régionaux à utiliser.  
  
## Valeur de retour  
 Si `mbstowcs` convertit correctement la chaîne source, elle retourne le nombre de caractères multioctets convertis.  Si l'argument `wcstr` est `NULL`, la fonction retourne la taille requise \(en caractères larges\) de la chaîne de destination.  Si `mbstowcs` rencontre un caractère multioctets non valide, il retourne – 1.  Si la valeur de retour est `count`, la chaîne de caractères larges n'est pas terminée par le caractère NULL.  
  
> [!IMPORTANT]
>  Vérifiez que `wcstr` et `mbstr` ne se chevauchent pas, et que `count` reflète fidèlement le nombre de caractères multioctets à convertir.  
  
## Notes  
 La fonction `mbstowcs` convertit jusqu'à un nombre maximal de caractères multioctets `count` référencés par `mbstr` vers une chaîne de caractères correspondants qui sont déterminés par les paramètres régionaux actuels.  Il enregistre la chaîne de caractères larges générée à l'adresse représentée par `wcstr`*.* Le résultat est similaire à une série d'appels à `mbtowc`.  Si `mbstowcs` rencontre le caractère NULL codé sur un octet \("\\0 "\) avant ou lorsque `count` se produit, elle convertit le caractère NULL en un caractère Null de caractères étendus \(" L "\\0 "\) et s'arrête.  Par conséquent, la chaîne de caractères larges à `wcstr` se termine par null uniquement si un caractère NULL est rencontré lors de la conversion.  Si les séquences désignées par `wcstr` et `mbstr` se chevauchent, le comportement n'est pas défini.  
  
 Si l'argument `wcstr` est `NULL`, `mbstowcs` retourne le nombre de caractères larges qui résulteraient d'une conversion, à l'exclusion d'une marque de fin null.  La chaîne source doit se terminer par null pour que la valeur correcte soit retournée.  Si vous avez besoin qu'une chaîne de caractères larges résultante se termine par null, ajoutez un à la valeur retournée.  
  
 Si l'argument `mbstr` est `NULL`, ou si `count` est \> `INT_MAX`, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md) .  Si l'exécution est autorisée à se poursuivre, errno est défini à `EINVAL` et la fonction retourne \-1.  
  
 `mbstowcs` utilise les paramètres régionaux actuels pour tout comportement dépend des paramètres régionaux ; `_mbstowcs_l`  est identique à la différence qu'il utilise les paramètres régionaux transmis à la place.  Pour plus d'informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`mbstowcs`|\<stdlib.h\>|  
|`_mbstowcs_l`|\<stdlib.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
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
  
  **Les informations relatives aux paramètres régionaux sont définies comme Japanese\_Japan.932**  
**Convertit en une chaîne multioctets:**  
 **Taille requise : 4**  
 **Nombre d'octets écrits dans la chaîne de caractères multioctets : 4**  
 **Valeurs hexadécimales des caractères multioctets : 0x82 0xa0 0x82 0xa1**  
 **La page de codes 932 utilise 0x81 à 0x9f comme octets de tête.**  
**Reconvertit en une chaîne à caractères élargis:**  
 **Caractères convertis : 2**  
 **Valeur hexadécimale des 2 premiers caractères larges : 0x3042 0x3043**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [\_mbclen, mblen, \_mblen\_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, \_mbtowc\_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, \_wcstombs\_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, \_wctomb\_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)