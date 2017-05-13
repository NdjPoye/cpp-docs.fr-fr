---
title: _mbsnbset, _mbsnbset_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbsnbset
- _mbsnbset_l
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
apitype: DLLExport
f1_keywords:
- mbsnbset
- mbsnbset_l
- _mbsnbset
- _mbsnbset_l
dev_langs:
- C++
helpviewer_keywords:
- tcsnset function
- _tcsnset_l function
- _mbsnbset function
- _tcsnset function
- _mbsnbset_l function
- mbsnbset_l function
- tcsnset_l function
- mbsnbset function
ms.assetid: 8e46ef75-9a56-42d2-a522-a08450c67c19
caps.latest.revision: 24
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
ms.openlocfilehash: 51b82c6a60eb8024c267e07e1327c8afd7928eea
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="mbsnbset-mbsnbsetl"></a>_mbsnbset, _mbsnbset_l
Attribue aux `n` premiers octets d'une chaîne de caractères multioctets un caractère spécifié. Des versions plus sécurisées de ces fonctions sont disponibles. Consultez [_mbsnbset_s, _mbsnbset_s_l](../../c-runtime-library/reference/mbsnbset-s-mbsnbset-s-l.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
unsigned char *_mbsnbset(  
   unsigned char *str,  
   unsigned int c,  
   size_t count   
);  
unsigned char *_mbsnbset_l(  
   unsigned char *str,  
   unsigned int c,  
   size_t count,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `str`  
 Chaîne à modifier.  
  
 `c`  
 Paramètre de caractère codé sur un octet ou multioctet.  
  
 `count`  
 Nombre d'octets à définir.  
  
 `locale`  
 Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  
 `_mbsnbset` retourne un pointeur désignant la chaîne modifiée.  
  
## <a name="remarks"></a>Notes  
 Les fonctions `_mbsnbset` et `_mbsnbset_l` attribuent, au plus, aux `count` premiers octets de `str` la valeur `c`. Si la valeur `count` est supérieure à la longueur de `str`, la longueur de `str` est utilisée à la place de `count`. Si `c` est un caractère multioctet et ne peut pas être défini entièrement dans le dernier octet spécifié par `count`, le dernier octet est rempli avec un caractère vide. `_mbsnbset`et `_mbsnbset_l` ne place pas une de fin null à la fin de `str`.  
  
 `_mbsnbset`et `_mbsnbset_l` est similaire à `_mbsnset`, sauf qu’il définit `count` octets plutôt que `count` caractères de `c`.  
  
 Si `str` a la valeur `NULL` ou que `count` est égal à zéro, cette fonction génère une exception de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, `errno` a la valeur `EINVAL` et la fonction retourne une valeur `NULL`. De même, si `c` n'est pas un caractère multioctet valide, `errno` a la valeur `EINVAL` et un espace est utilisé à la place.  
  
 La valeur de sortie est affectée par la valeur du paramètre de catégorie `LC_CTYPE` des paramètres régionaux. Pour plus d’informations, consultez [setlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md). La version `_mbsnbset` de cette fonction utilise les paramètres régionaux actuels pour ce comportement dépendant des paramètres régionaux ; la version `_mbsnbset_l` est identique, à ceci près qu’elle utilise à la place les paramètres régionaux passés. Pour plus d’informations, consultez [Paramètres régionaux](../../c-runtime-library/locale.md).  
  
 **Remarque relative à la sécurité** Cette API est exposée à une menace potentielle liée à un problème de dépassement de mémoire tampon. Les dépassements de mémoire tampon sont une méthode fréquente d'attaque du système, ce qui provoque une élévation des privilèges injustifiée. Pour plus d’informations, consultez [Solutions contre les dépassements de mémoire tampon](http://msdn.microsoft.com/library/windows/desktop/ms717795).  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine Tchar.h|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tcsnset`|`_strnset`|`_mbsnbset`|`_wcsnset`|  
|`_tcsnset_l`|`_strnset_l`|`_mbsnbset_l`|`_wcsnset_l`|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_mbsnbset`|\<mbstring.h>|  
|`_mbsnbset_l`|\<mbstring.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_mbsnbset.c  
// compile with: /W3  
#include <mbstring.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char string[15] = "This is a test";  
   /* Set not more than 4 bytes of string to be *'s */  
   printf( "Before: %s\n", string );  
   _mbsnbset( string, '*', 4 ); // C4996  
   // Note; _mbsnbset is deprecated; consider _mbsnbset_s  
   printf( "After:  %s\n", string );  
}  
```  
  
## <a name="output"></a>Sortie  
  
```  
Before: This is a test  
After:  **** is a test  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [_mbsnbcat, _mbsnbcat_l](../../c-runtime-library/reference/mbsnbcat-mbsnbcat-l.md)   
 [_strnset, _strnset_l, _wcsnset, _wcsnset_l, _mbsnset, _mbsnset_l](../../c-runtime-library/reference/strnset-strnset-l-wcsnset-wcsnset-l-mbsnset-mbsnset-l.md)   
 [_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](../../c-runtime-library/reference/strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)
