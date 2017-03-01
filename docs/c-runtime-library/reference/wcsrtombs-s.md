---
title: wcsrtombs_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcsrtombs_s
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
- wcsrtombs_s
dev_langs:
- C++
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: 27
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
ms.openlocfilehash: 52f3395cc878c1f051867d81ee12d0c9b3de619d
ms.lasthandoff: 02/24/2017

---
# <a name="wcsrtombss"></a>wcsrtombs_s
Convertit une chaîne de caractères larges dans sa représentation de chaîne de caractères multioctets. Version de [wcsrtombs](../../c-runtime-library/reference/wcsrtombs.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `pReturnValue`  
 Nombre de caractères convertis.  
  
 [out] `mbstr`  
 Adresse d'une mémoire tampon pour la chaîne de caractères multioctets convertie résultante.  
  
 [out] `sizeInBytes`  
 Taille en octets de la mémoire tampon `mbstr`.  
  
 [in] `wcstr`  
 Pointe vers la chaîne de caractères larges à convertir.  
  
 [in] `count`  
 Nombre maximal d’octets devant être stockés dans la mémoire tampon `mbstr` ou [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in] `mbstate`  
 Un pointeur vers un objet d'état de conversion `mbstate_t`.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l'opération a réussi, un code d'erreur en cas d'échec.  
  
|Condition d'erreur|Valeur de retour et `errno`|  
|---------------------|------------------------------|  
|`mbstr` a la valeur `NULL` et `sizeInBytes` > 0|`EINVAL`|  
|`wcstr` a la valeur `NULL`.|`EINVAL`|  
|La mémoire tampon de destination est trop petite pour contenir la chaîne convertie (à moins que `count` ait la valeur `_TRUNCATE` ; consultez les notes ci-dessous)|`ERANGE`|  
  
 Si l’une de ces conditions se présente, l’exception de paramètre non valide est appelée, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à continuer, la fonction retourne un code d'erreur et définit `errno`, comme indiqué dans le tableau.  
  
## <a name="remarks"></a>Notes  
 La fonction `wcsrtombs_s` convertit une chaîne de caractères larges vers laquelle pointe `wcstr` en caractères multioctets stockés dans la mémoire tampon vers laquelle pointe `mbstr`, en utilisant l’état de conversion indiqué dans `mbstate`. La conversion se poursuit pour chaque caractère jusqu'à ce qu'une des conditions suivantes soit remplie :  
  
-   Un caractère large null est rencontré  
  
-   Un caractère large qui ne peut pas être converti est rencontré  
  
-   Le nombre d'octets stockés dans la mémoire tampon `mbstr` est égal à `count`.  
  
 La chaîne de destination est toujours terminée par null (même en cas d'erreur).  
  
 Si `count` correspond à la valeur spéciale [_TRUNCATE](../../c-runtime-library/truncate.md), `wcsrtombs_s` convertit autant de caractères de la chaîne que la mémoire tampon de destination peut en accueillir, tout en laissant de l’espace pour un terminateur Null.  
  
 Si la fonction `wcsrtombs_s` convertit correctement la chaîne source, elle indique la taille en octets de la chaîne convertie, terminateur Null inclus, dans `*``pReturnValue` (à condition que `pReturnValue` n’a pas la valeur `NULL`). Cela se produit même si l'argument `mbstr` a la valeur `NULL`, et permet de déterminer la taille de mémoire tampon requise. Notez que si `mbstr` a la valeur `NULL`, le paramètre `count` est ignoré.  
  
 Si la fonction `wcsrtombs_s` rencontre un caractère large qu’elle ne peut pas convertir en caractère multioctet, elle affecte la valeur -1 à `*``pReturnValue`, définit la mémoire tampon de destination en tant que chaîne vide, affecte à `errno` la valeur `EILSEQ`, puis retourne `EILSEQ`.  
  
 Si les séquences pointées par `wcstr` et `mbstr` se chevauchent, le comportement de `wcsrtombs_s` n'est pas défini. `wcsrtombs_s` est affecté par la catégorie LC_TYPE des paramètres régionaux actuels.  
  
> [!IMPORTANT]
>  Vérifiez que `wcstr` et `mbstr` ne se chevauchent pas, et que `count` reflète fidèlement le nombre de caractères larges à convertir.  
  
 La fonction `wcsrtombs_s` se distingue de [wcstombs_s, _wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md) par sa capacité à redémarrer. L'état de la conversion est stocké dans `mbstate` pour les appels suivants à la même ou à d'autres fonctions redémarrables. Les résultats ne sont pas définis quand l'utilisation de fonctions redémarrables est combinée avec l'utilisation de fonctions non redémarrables. Par exemple, une application utiliserait `wcsrlen` plutôt que `wcslen` si un appel ultérieur à `wcsrtombs_s` était utilisé à la place de `wcstombs_s.`.  
  
 En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement (ce qui évite d’avoir à spécifier un argument taille) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Exceptions  
 La fonction `wcsrtombs_s` est multithread-safe tant qu’aucune fonction du thread actif n’appelle `setlocale` pendant l’exécution de cette fonction et que `mbstate` a la valeur Null.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_wcsrtombs_s.cpp  
//   
// This code example converts a wide  
// character string into a multibyte  
// character string.  
//  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
void main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    errno_t         err;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,  
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);  
    if (err == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfully converted.\n" );  
    }  
}  
```  
  
```Output  
The string was successfully converted.  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`wcsrtombs_s`|\<wchar.h>|  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)
