---
title: wcsrtombs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcsrtombs
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
- wcsrtombs
dev_langs:
- C++
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
caps.latest.revision: 26
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 6dfe7e2293f9544b64a0dfd7dfaa1889e65a64dc
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="wcsrtombs"></a>wcsrtombs
Convertit une chaîne de caractères larges dans sa représentation de chaîne de caractères multioctets. Il existe une version plus sécurisée de cette fonction. Consultez [wcsrtombs_s](../../c-runtime-library/reference/wcsrtombs-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t wcsrtombs(  
   char *mbstr,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcsrtombs(  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `mbstr`  
 Emplacement adresse de la chaîne de caractères multioctets convertie obtenue.  
  
 [in] `wcstr`  
 Pointe indirectement vers l’emplacement de la chaîne de caractères larges à convertir.  
  
 [in] `count`  
 Nombre de caractères à convertir.  
  
 [in] `mbstate`  
 Un pointeur vers un objet d'état de conversion `mbstate_t`.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le nombre d’octets correctement convertis, sans l’octet Null de fin (le cas échéant) ou -1 si une erreur s’est produite.  
  
## <a name="remarks"></a>Notes  
 La fonction `wcsrtombs` convertit une chaîne de caractères larges, en commençant dans l’état de conversion spécifié dans `mbstate`, à partir des valeurs pointées indirectement dans `wcstr`, en adresse de `mbstr`. La conversion se poursuit pour chaque caractère jusqu’à ce qu’un caractère large de fin Null ou un caractère non correspondant soit rencontré ou dès que le caractère suivant dépasse la limite contenue dans `count`. Si la fonction `wcsrtombs` rencontre le caractère Null de caractère large (L'\0') avant ou quand `count` est atteint, elle le convertit en 0 de 8 bits et s’arrête.  
  
 Par conséquent, la chaîne de caractères multioctets au niveau de `mbstr` se termine par un caractère Null seulement si `wcsrtombs` rencontre un caractère Null de caractère large pendant la conversion. Si les séquences pointées par `wcstr` et `mbstr` se chevauchent, le comportement de `wcsrtombs` n'est pas défini. `wcsrtombs` est affecté par la catégorie LC_TYPE des paramètres régionaux actuels.  
  
 La fonction `wcsrtombs` se distingue de [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) par sa capacité à redémarrer. L'état de la conversion est stocké dans `mbstate` pour les appels suivants à la même ou à d'autres fonctions redémarrables. Les résultats ne sont pas définis quand l'utilisation de fonctions redémarrables est combinée avec l'utilisation de fonctions non redémarrables.  Par exemple, une application utiliserait `wcsrlen` plutôt que `wcsnlen` si un appel ultérieur à `wcsrtombs` était utilisé à la place de `wcstombs`.  
  
 Si l’argument `mbstr` a la valeur `NULL`, `wcsrtombs` retourne la taille requise de la chaîne de destination en octets. Si `mbstate` a la valeur Null, l’état de conversion `mbstate_t` interne est utilisé. Si la séquence de caractères `wchar` n'a pas de représentation correspondante en caractères multioctets, la valeur -1 est retournée et `errno` est défini à `EILSEQ`.  
  
 En C++, cette fonction a une surcharge de modèle qui appelle l'équivalent plus récent et sécurisé de cette fonction. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Exceptions  
 La fonction `wcsrtombs` est multithread-safe tant qu’aucune fonction du thread actif n’appelle `setlocale` pendant l’exécution de cette fonction et que `mbstate` n’a pas la valeur Null.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_wcsrtombs.cpp  
// compile with: /W3  
// This code example converts a wide  
// character string into a multibyte  
// character string.  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
int main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    countConverted = wcsrtombs(mbString, &wcsIndirectString,  
                               MB_BUFFER_SIZE, &mbstate); // C4996  
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s  
    if (errno == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfuly converted.\n" );  
    }  
}  
```  
  
```Output  
The string was successfuly converted.  
```  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`wcsrtombs`|\<wchar.h>|  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)
