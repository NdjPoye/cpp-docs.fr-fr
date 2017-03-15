---
title: wctob | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wctob
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
- wctob
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wctob function
- characters, converting
ms.assetid: 46aec98b-c2f2-4e9d-9d89-7db99ba8a9a6
caps.latest.revision: 14
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
ms.openlocfilehash: 6c72cc32c5bd48bc6b7fc9c9187797f056ec7712
ms.lasthandoff: 02/24/2017

---
# <a name="wctob"></a>wctob
Détermine si un caractère large correspond à un caractère multioctet et retourne sa représentation de caractère multioctet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int wctob(  
   wint_t wchar  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `wchar`  
 Valeur à traduire.  
  
## <a name="return-value"></a>Valeur de retour  
 Si la fonction `wctob` convertit correctement un caractère large, elle retourne sa représentation de caractère multioctet, uniquement si la longueur du caractère multioctet est d’un octet exactement. Si la fonction `wctob` rencontre un caractère large qu’elle ne peut pas convertir en caractère multioctet ou si le caractère multioctet ne fait pas exactement un octet de long, elle retourne -1.  
  
## <a name="remarks"></a>Notes  
 La fonction `wctob` convertit un caractère large contenu dans `wchar` en caractère multioctet correspondant qui est passé par la valeur de retour `int`, dans la mesure où la longueur du caractère multioctet est d’un octet exactement.  
  
 Si `wctob` a échoué et qu’aucun caractère multioctet correspondant n’a été trouvé, la fonction affecte à `errno` la valeur `EILSEQ` et retourne -1.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`wctob`|\<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Ce programme illustre le comportement de la fonction `wcstombs`.  
  
```  
// crt_wctob.c  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    int     bChar = 0;  
    wint_t  wChar = 0;  
  
    // Set the corresponding wide character to exactly one byte.  
    wChar = (wint_t)'A';  
  
    bChar = wctob( wChar );  
    if (bChar == WEOF)  
    {  
        printf( "No corresponding multibyte character was found.\n");  
    }  
    else  
    {  
        printf( "Determined the corresponding multibyte character to"  
                " be \"%c\".\n", bChar);  
    }  
}  
  
```  
  
```Output  
Determined the corresponding multibyte character to be "A".  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
