---
title: mbrlen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords: mbrlen
dev_langs: C++
helpviewer_keywords: mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d8276f716049915d1cd3b8c98074255d3327144c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="mbrlen"></a>mbrlen
Déterminer le nombre d'octets requis pour terminer un caractère multioctet dans les paramètres régionaux actuels, avec la capacité de redémarrer au milieu d'un caractère multioctet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t mbrlen(  
   const char * str,  
   size_t count,  
   mbstate_t * mbstate  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `str`  
 Pointeur vers l'octet suivant à examiner dans une chaîne de caractères multioctets.  
  
 `count`  
 Nombre maximal d'octets à examiner.  
  
 `mbstate`  
 Pointeur vers l'état du décalage actuel de l'octet initial de `str`.  
  
## <a name="return-value"></a>Valeur de retour  
 Une des valeurs suivantes :  
  
 0  
 Les `count` (ou moins) octets suivants terminent le caractère multioctet qui représente le caractère null large.  
  
 1 à `count`, inclusivement  
 Les `count` (ou moins) octets suivants terminent un caractère multioctet valide. La valeur retournée est le nombre d'octets qui terminent le caractère multioctet.  
  
 (size_t)(-2)  
 Les `count` octets suivants contribuent à un caractère multioctets incomplet mais potentiellement valide, et tous les `count` octets ont été traités.  
  
 (size_t)(-1)  
 Une erreur d'encodage s'est produite. Les `count` (ou moins) octets suivants ne contribuent pas à un caractère multioctet complet et valide. Dans ce cas, `errno` est défini à EILSEQ et l'état de la conversion dans `mbstate` n'est pas spécifié.  
  
## <a name="remarks"></a>Notes  
 La fonction `mbrlen` examine au plus `count` octets à partir de l'octet pointé par `str` pour déterminer le nombre d'octets qui sont nécessaires pour terminer le caractère multioctet suivant, y compris les séquences de décalage. EIle est équivalente à l'appel de `mbrtowc(NULL, str, count, &mbstate)`, où `mbstate` est un objet `mbstate_t` fourni par l'utilisateur ou un objet interne statique fourni par la bibliothèque.  
  
 La fonction `mbrlen` enregistre et utilise l'état du décalage d'un caractère multioctet incomplet dans le paramètre `mbstate`. Ceci donne à `mbrlen` la capacité à redémarrer si nécessaire au milieu d'un caractère multioctet, en examinant au plus `count` octets. Si `mbstate` est un pointeur null, `mbrlen` utilise un objet `mbstate_t` statique interne pour stocker l'état du décalage. Comme l'objet `mbstate_t` interne n'est pas thread-safe, nous vous recommandons de toujours allouer et de passer votre propre paramètre `mbstate`.  
  
 La fonction `mbrlen` diffère de [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md) par sa capacité à redémarrer. L'état du décalage est stocké dans `mbstate` pour les appels suivants à la même ou à d'autres fonctions redémarrables. Les résultats ne sont pas définis quand l'utilisation de fonctions redémarrables est combinée avec l'utilisation de fonctions non redémarrables.  Par exemple, une application doit utiliser `wcsrlen` au lieu de `wcslen`, si un appel ultérieur à `wcsrtombs` est utilisé à la place de `wcstombs.`  
  
### <a name="generic-text-routine-mappings"></a>Mappages de routines de texte générique  
  
|Routine TCHAR.H|_UNICODE et _MBCS non définis|_MBCS défini|_UNICODE défini|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|non applicable|non applicable|`mbrlen`|non applicable|  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`mbrlen`|\<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Cet exemple montre comment l'interprétation des caractères multioctets dépend de la page de codes actuelle et montre la capacité de reprise de `mbrlen`.  
  
```C  
// crt_mbrlen.c  
// Compile by using: cl crt_mbrlen.c  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <locale.h>  
#include <wchar.h>  
  
size_t Example(const char * pStr)  
{  
    size_t      charLen = 0;  
    size_t      charCount = 0;  
    mbstate_t   mbState = {0};  
  
    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&  
            charLen != (size_t)-1)  
    {  
        if (charLen != (size_t)-2) // if complete mbcs char,  
        {  
            charCount++;  
        }  
    }   
    return (charCount);  
}   
  
int main( void )  
{  
    int         cp;  
    size_t      charCount = 0;  
    const char  *pSample =   
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";  
  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
  
    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale  
    _setmbcp(932); // and Japanese multibyte code page  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
}  
```  
  
```Output  
  
Code page: 0  
é╨éτé¬é╚: Shift-jis hiragana.  
Character count: 29  
  
Code page: 932  
????: Shift-jis hiragana.  
Character count: 25  
  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de chaînes](../../c-runtime-library/string-manipulation-crt.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)