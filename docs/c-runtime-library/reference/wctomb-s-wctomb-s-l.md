---
title: wctomb_s, _wctomb_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wctomb_s_l
- wctomb_s
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
- wctomb_s
- _wctomb_s_l
dev_langs:
- C++
helpviewer_keywords:
- wctomb_s function
- wctomb_s_l function
- string conversion, wide characters
- wide characters, converting
- _wctomb_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 7e94a888-deed-4dbd-b5e9-d4a0455538b8
caps.latest.revision: 18
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
ms.openlocfilehash: 94973bf59580354aed75b8c7a3a154f415060163
ms.lasthandoff: 02/24/2017

---
# <a name="wctombs-wctombsl"></a>wctomb_s, _wctomb_s_l
Convertit un caractère large en caractère multioctet correspondant. Version de [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t wctomb_s(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar   
);  
errno_t _wctomb_s_l(  
   int *pRetValue,  
   char *mbchar,  
   size_t sizeInBytes,  
   wchar_t wchar,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `pRetValue`  
 Nombre d’octets ou code indiquant le résultat.  
  
 [out] `mbchar`  
 Adresse d’un caractère multioctet.  
  
 [in] `sizeInBytes`  
 Taille de la mémoire tampon `mbchar`.  
  
 [in] `wchar`  
 Caractère large.  
  
 [in] `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l'opération a réussi, un code d'erreur en cas d'échec.  
  
 Conditions d’erreur  
  
|`mbchar`|`sizeInBytes`|Valeur de retour|`pRetValue`|  
|--------------|-------------------|------------------|-----------------|  
|`NULL`|>0|`EINVAL`|non modifié|  
|indifférent|>`INT_MAX`|`EINVAL`|non modifié|  
|indifférent|trop petite|`EINVAL`|non modifié|  
  
 Si l’une des conditions d’erreur ci-dessus se présente, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à continuer, `wctomb` retourne `EINVAL` et définit `errno` à `EINVAL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `wctomb_s` convertit son argument `wchar` en caractère multioctet correspondant et stocke le résultat au niveau de `mbchar`. Vous pouvez appeler la fonction de n’importe quel endroit dans n’importe quel programme.  
  
 Si `wctomb_s` convertit le caractère large en caractère multioctet, elle place le nombre d’octets (qui n’est jamais supérieure à `MB_CUR_MAX`) figurant dans le caractère large dans l’entier vers lequel pointe `pRetValue`. Si `wchar` correspond au caractère Null à caractère large (L'\0'), `wctomb_s` complète `pRetValue` avec la valeur 1. Si le pointeur cible `mbchar` a la valeur NULL, `wctomb_s` affecte à `pRetValue` la valeur 0. Si la conversion n’est pas possible dans les paramètres régionaux actifs, `wctomb_s` affecte à `pRetValue` la valeur -1.  
  
 `wctomb_s` utilise les paramètres régionaux actifs pour les informations dépendantes des paramètres régionaux ; la fonction `_wctomb_s_l` est identique à ceci près qu’elle utilise à la place les paramètres régionaux transmis. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`wctomb_s`|\<stdlib.h>|  
|`_wctomb_s_l`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Ce programme illustre le comportement de la fonction `wctomb`.  
  
```  
// crt_wctomb_s.cpp  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
    int i;  
    wchar_t wc = L'a';  
    char *pmb = (char *)malloc( MB_CUR_MAX );  
  
    printf_s( "Convert a wide character:\n" );  
    wctomb_s( &i, pmb, MB_CUR_MAX, wc );  
    printf_s( "   Characters converted: %u\n", i );  
    printf_s( "   Multibyte character: %.1s\n\n", pmb );  
}  
```  
  
```Output  
Convert a wide character:  
   Characters converted: 1  
   Multibyte character: a  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)