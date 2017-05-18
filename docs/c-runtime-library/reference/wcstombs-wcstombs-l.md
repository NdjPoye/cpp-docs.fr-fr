---
title: wcstombs, _wcstombs_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcstombs
- _wcstombs_l
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
- wcstombs
- _wcstombs_l
dev_langs:
- C++
helpviewer_keywords:
- _wcstombs_l function
- wcstombs function
- string conversion, wide characters
- wide characters, converting
- wcstombs_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 91234252-9ea1-423a-af99-e9d0ce4a40e3
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
ms.openlocfilehash: 200337a53155b27b76a944d025c8fb013c29c4e6
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="wcstombs-wcstombsl"></a>wcstombs, _wcstombs_l
Convertit une séquence de caractères larges en une séquence correspondante de caractères multioctets. Il existe des versions plus sécurisées de ces fonctions. Consultez [wcstombs_s, _wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t wcstombs(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count   
);  
size_t _wcstombs_l(  
   char *mbstr,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
size_t wcstombs(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
size_t _wcstombs_l(  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 `mbstr`  
 Adresse d’une séquence de caractères multioctets.  
  
 `wcstr`  
 Adresse d’une séquence de caractères larges.  
  
 `count`  
 Nombre maximal d’octets pouvant être stockés dans la chaîne de sortie multioctet.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Si la fonction `wcstombs` convertit correctement la chaîne multioctet, elle retourne le nombre d’octets écrits dans la chaîne de sortie multioctet, à l’exclusion du caractère `NULL` de fin (le cas échéant). Si l’argument `mbstr` a la valeur `NULL`, `wcstombs` retourne la taille requise de la chaîne de destination en octets. Si `wcstombs` rencontre un caractère large, elle ne peut pas convertir en un caractère multioctet, elle retourne -1 castée en type `size_t` et définit `errno` à `EILSEQ`.  
  
## <a name="remarks"></a>Remarques  
 La fonction `wcstombs` convertit la chaîne de caractères larges vers laquelle pointe `wcstr` en caractères multioctets correspondants et stocke les résultats dans le tableau `mbstr`. Le paramètre `count` indique le nombre maximal d’octets qui peuvent être stockés dans la chaîne de sortie multioctet (c’est-à-dire, la taille de `mbstr`). En général, le nombre d’octets exigé au moment de la conversion d’une chaîne de caractères larges n’est pas connu. Certains caractères larges peuvent en exiger un seul dans la chaîne de sortie, alors que d’autres peuvent en exiger deux. Si la chaîne de sortie multioctet contient deux octets pour chaque caractère large présent dans la chaîne d’entrée (en incluant le caractère large `NULL`), le résultat est assuré de s’intégrer.  
  
 Si la fonction `wcstombs` rencontre le caractère null à caractère large (L'\0') avant ou quand `count` est atteint, elle le convertit en 0 de 8 bits et s’arrête. Par conséquent, la chaîne de caractères multioctets au niveau de `mbstr` se termine par un caractère null seulement si `wcstombs` rencontre un caractère null de caractère large pendant la conversion. Si les séquences pointées par `wcstr` et `mbstr` se chevauchent, le comportement de `wcstombs` n'est pas défini.  
  
 Si l’argument `mbstr` a la valeur `NULL`, `wcstombs` retourne la taille requise en octets de la chaîne de destination.  
  
 `wcstombs` valide ses paramètres. Si `wcstr` est `NULL`, ou si `count` est supérieur à `INT_MAX`, cette fonction appelle le Gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md) . Si l’exécution est autorisée à se poursuivre, la fonction définit `errno` avec la valeur `EINVAL` et retourne -1.  
  
 La fonction `wcstombs` utilise les paramètres régionaux actifs pour tout comportement dépendant des paramètres régionaux ; la fonction `_wcstombs_l` est identique sauf qu’elle utilise à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 En C++, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`wcstombs`|\<stdlib.h>|  
|`_wcstombs_l`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Ce programme illustre le comportement de la fonction `wcstombs`.  
  
```  
// crt_wcstombs.c  
// compile with: /W3  
// This example demonstrates the use  
// of wcstombs, which converts a string  
// of wide characters to a string of   
// multibyte characters.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t  count;  
    char    *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t *pWCBuffer = L"Hello, world.";  
  
    printf("Convert wide-character string:\n" );  
  
    count = wcstombs(pMBBuffer, pWCBuffer, BUFFER_SIZE ); // C4996  
    // Note: wcstombs is deprecated; consider using wcstombs_s instead  
    printf("   Characters converted: %u\n",  
            count );  
    printf("    Multibyte character: %s\n\n",  
           pMBBuffer );  
  
    free(pMBBuffer);  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 13  
    Multibyte character: Hello, world.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
