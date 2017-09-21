---
title: wcrtomb | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcrtomb
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
- wcrtomb
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
caps.latest.revision: 26
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 599802a3038305dd09fafb4b6fb278d05c13afa4
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="wcrtomb"></a>wcrtomb
Convertit un caractère large dans sa représentation de caractère multioctet. Il existe une version plus sécurisée de cette fonction. Consultez [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t wcrtomb(  
   char *mbchar,  
   wchar_t wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcrtomb(  
   char (&mbchar)[size],  
   wchar_t wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `mbchar`  
 Résultat de la conversion du caractère multioctet.  
  
 [in] `wchar`  
 Caractère large à convertir.  
  
 [in] `mbstate`  
 Pointeur vers un objet `mbstate_t` .  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le nombre d’octets nécessaire pour représenter le caractère multioctet converti ou -1 si une erreur se produit.  
  
## <a name="remarks"></a>Notes  
 La fonction `wcrtomb` convertit un caractère large, en commençant dans l’état de conversion spécifié dans `mbstate`, à partir de la valeur contenue dans `wchar`, en adresse représentée par `mbchar`. La valeur de retour correspond au nombre d’octets nécessaires pour représenter le caractère multioctet correspondant, mais elle ne retourne pas plus de `MB_CUR_MAX` octets.  
  
 Si `mbstate` a la valeur Null, l’objet `mbstate_t` interne contenant l’état de conversion `mbchar` est utilisé. Si la séquence de caractères `wchar` n'a pas de représentation correspondante en caractères multioctets, la valeur -1 est retournée et `errno` est défini à `EILSEQ`.  
  
 La fonction `wcrtomb` se distingue de [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) par sa capacité à redémarrer. L'état de la conversion est stocké dans `mbstate` pour les appels suivants à la même ou à d'autres fonctions redémarrables. Les résultats ne sont pas définis quand l'utilisation de fonctions redémarrables est combinée avec l'utilisation de fonctions non redémarrables. Par exemple, une application utiliserait `wcsrlen` plutôt que `wcsnlen` si un appel ultérieur à `wcsrtombs` était utilisé à la place de `wcstombs`.  
  
 En C++, cette fonction a une surcharge de modèle qui appelle les équivalents plus récents et sécurisés de cette fonction. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Exceptions  
 La fonction `wcrtomb` est multithread-safe tant qu’aucune fonction du thread actif n’appelle `setlocale` pendant l’exécution de cette fonction et que `mbstate` a la valeur Null.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_wcrtomb.c  
// compile with: /W3  
// This program converts a wide character  
// to its corresponding multibyte character.  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    size_t      sizeOfCovertion = 0;  
    mbstate_t   mbstate;  
    char        mbStr = 0;  
    wchar_t*    wcStr = L"Q";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996  
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead  
    if (sizeOfCovertion > 0)  
    {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wcStr);  
        printf(" was converted to the \"%c\" ", mbStr);  
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
The corresponding wide character "Q" was converted to the "Q" multibyte character.  
```  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`wcrtomb`|\<wchar.h>|  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)