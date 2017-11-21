---
title: _mbclen, mblen, _mblen_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbclen
- mblen
- _mblen_l
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
- mblen
- ftclen
- _mbclen
- tclen
- _ftclen
- _tclen
- mbclen
dev_langs: C++
helpviewer_keywords:
- tclen function
- _mblen_l function
- _tclen function
- mblen_l function
- _mbclen function
- mbclen function
- mblen function
ms.assetid: d5eb92a0-b7a3-464a-aaf7-9890a8e3ed70
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9c7d976606d292cbe7cd7ce8e8c24e20d0dfa688
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="mbclen-mblen-mblenl"></a>_mbclen, mblen, _mblen_l
Obtient la longueur et détermine la validité d’un caractère multioctet.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t _mbclen(  
   const unsigned char *c   
);  
int mblen(  
   const char *mbstr,  
   size_t count   
);  
int _mblen_l(  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `c`  
 Caractères multioctet.  
  
 `mbstr`  
 Adresse d’une séquence d’octets de caractères multioctets.  
  
 `count`  
 Nombre d'octets à vérifier.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 `_mbclen` retourne 1 ou 2, selon que la longueur du caractère multioctet `c` est de 1 ou 2 octets. Aucune erreur n’est retournée pour `_mbclen`. Si `mbstr` n’a pas la valeur `NULL`, `mblen` retourne la longueur, en octets, du caractère multioctet. Si `mbstr` a la valeur `NULL` ou désigne le caractère Null large, `mblen` retourne 0. Si l’objet qui `mbstr` pointe vers ne forment pas un caractère multioctet valide dans le premier `count` caractères, `mblen` retourne -1.  
  
## <a name="remarks"></a>Remarques  
 La fonction `_mbclen` retourne la longueur, en octets, du caractère multioctet `c`. Si `c` ne pointe pas vers l’octet de tête d’un caractère multioctet comme déterminé par un appel implicite à `_ismbblead`, le résultat de `_mbclen` est imprévisible.  
  
 `mblen` retourne la longueur en octets de `mbstr` s’il s’agit d’un caractère multioctet valide et détermine la validité des caractères multioctets associée à la page de codes. `mblen` examine `count` octets (ou moins) contenus dans `mbstr`, mais pas plus de `MB_CUR_MAX`.  
  
 La valeur de sortie est affectée par la valeur du paramètre de catégorie `LC_CTYPE` des paramètres régionaux. Pour plus d’informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). Les versions de ces fonctions sans le suffixe `_l` utilisent les paramètres régionaux pour ce comportement dépendant des paramètres régionaux ; les versions avec le suffixe `_l` sont identiques, sauf qu'elles utilisent à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tclen`|Mappe à la macro ou à la fonction inline|`_mbclen`|Mappe à la macro ou à la fonction inline|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_mbclen`|\<mbstring.h>|  
|`mblen`|\<stdlib.h>|  
|`_mblen_l`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_mblen.c  
/* illustrates the behavior of the mblen function  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
    int      i;  
    char    *pmbc = (char *)malloc( sizeof( char ) );  
    wchar_t  wc   = L'a';  
  
    printf( "Convert wide character to multibyte character:\n" );  
    wctomb_s( &i, pmbc, sizeof(char), wc );  
    printf( "  Characters converted: %u\n", i );  
    printf( "  Multibyte character: %x\n\n", *pmbc );  
  
    i = mblen( pmbc, MB_CUR_MAX );  
    printf( "Length in bytes of multibyte character %x: %u\n", *pmbc, i );  
  
    pmbc = NULL;  
    i = mblen( pmbc, MB_CUR_MAX );  
    printf( "Length in bytes of NULL multibyte character %x: %u\n", pmbc, i );  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
Convert wide character to multibyte character:  
  Characters converted: 1  
  Multibyte character: 61  
  
Length in bytes of multibyte character 61: 1  
Length in bytes of NULL multibyte character 0: 0  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Classifications des caractères](../../c-runtime-library/character-classification.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbccpy, _mbccpy_l](../../c-runtime-library/reference/mbccpy-mbccpy-l.md)   
 [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](../../c-runtime-library/reference/strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)