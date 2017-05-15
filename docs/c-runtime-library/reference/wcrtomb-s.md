---
title: wcrtomb_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcrtomb_s
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
- wcrtomb_s
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: d80bcc1bfda2fa5b7495b9ea0fb92a99056494b6
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="wcrtombs"></a>wcrtomb_s
Convertit un caractère large dans sa représentation de caractère multioctet. Version de [wcrtomb](../../c-runtime-library/reference/wcrtomb.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char *mbchar,  
   size_t sizeOfmbchar,  
   wchar_t *wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char (&mbchar)[size],  
   wchar_t *wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `pReturnValue`  
 Retourne le nombre de caractères écrits ou -1 si une erreur s’est produite.  
  
 [out] `mbchar`  
 Résultat de la conversion du caractère multioctet.  
  
 [in] `sizeOfmbchar`  
 Taille de la variable `mbchar` en octets.  
  
 [in] `wchar`  
 Caractère large à convertir.  
  
 [in] `mbstate`  
 Pointeur vers un objet `mbstate_t` .  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne zéro ou une valeur `errno` si une erreur se produit.  
  
## <a name="remarks"></a>Notes  
 La fonction `wcrtomb_s` convertit un caractère large, en commençant dans l’état de conversion spécifié dans `mbstate`, à partir de la valeur contenue dans `wchar`, en adresse représentée par `mbchar`. La valeur `pReturnValue` correspond au nombre d’octets convertis, mais pas plus de `MB_CUR_MAX` octets, ou -1 si une erreur s’est produite.  
  
 Si `mbstate` a la valeur null, l’état de conversion `mbstate_t` interne est utilisé. Si le caractère contenu dans `wchar` ne correspond à aucun caractère multioctet, la valeur de `pReturnValue` est égale à -1 et la fonction retourne la valeur `errno` de `EILSEQ`.  
  
 La fonction `wcrtomb_s` se distingue de [wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md) par sa capacité à redémarrer. L'état de la conversion est stocké dans `mbstate` pour les appels suivants à la même ou à d'autres fonctions redémarrables. Les résultats ne sont pas définis quand l'utilisation de fonctions redémarrables est combinée avec l'utilisation de fonctions non redémarrables. Par exemple, une application utiliserait `wcsrlen` plutôt que `wcslen` si un appel ultérieur à `wcsrtombs_s` était utilisé à la place de `wcstombs_s.`.  
  
 En C++, l’utilisation de cette fonction est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement (ce qui évite d’avoir à spécifier un argument de taille) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalents plus récents et sécurisés. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Exceptions  
 La fonction `wcrtomb_s` est multithread-safe tant qu’aucune fonction du thread actif n’appelle `setlocale` pendant l’exécution de cette fonction et que `mbstate` a la valeur Null.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_wcrtomb_s.c  
// This program converts a wide character  
// to its corresponding multibyte character.  
//  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    errno_t     returnValue;  
    size_t      pReturnValue;  
    mbstate_t   mbstate;  
    size_t      sizeOfmbStr = 1;  
    char        mbchar = 0;  
    wchar_t*    wchar = L"Q\0";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),  
                            *wchar, &mbstate);  
    if (returnValue == 0) {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wchar);  
        printf(" was converted to a the \"%c\" ", mbchar);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
```Output  
The corresponding wide character "Q" was converted to a the "Q" multibyte character.  
```  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`wcrtomb_s`|\<wchar.h>|  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)
