---
title: wcstombs_s, _wcstombs_s_l | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstombs_s_l
- wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
dev_langs: C++
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
caps.latest.revision: "31"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b5c57a82bef1a56925b414302fe2017df255ce2d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="wcstombss-wcstombssl"></a>wcstombs_s, _wcstombs_s_l

Convertit une séquence de caractères larges en une séquence correspondante de caractères multioctets. Version de [wctombs, _wctombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count   
);  

errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  

template <size_t size>  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  

template <size_t size>  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  

[out] *pReturnValue*  
Nombre de caractères convertis.  
  
[out] *mbstr*  
Adresse d'une mémoire tampon pour la chaîne de caractères multioctets convertie résultante.  
  
[in] *sizeInBytes*  
La taille en octets de la *mbstr* mémoire tampon.  
  
[in] *wcstr*  
Pointe vers la chaîne de caractères larges à convertir.  
  
[in] *nombre*  
Le nombre maximal d’octets à stocker dans le *mbstr* tampon, ne pas y compris le caractère null de fin, ou [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
[in] *paramètres régionaux*  
Paramètres régionaux à utiliser.  
  
## <a name="return-value"></a>Valeur de retour  

Zéro si l'opération a réussi, un code d'erreur en cas d'échec.  
  
|Condition d'erreur|Valeur de retour et `errno`|  
|---------------------|------------------------------|  
|*mbstr* est `NULL` et *sizeInBytes* > 0|`EINVAL`|  
|*wcstr* est`NULL`|`EINVAL`|  
|La mémoire tampon de destination est trop petite pour contenir la chaîne convertie (à moins que *nombre* est `_TRUNCATE`; consultez la section Notes ci-dessous)|`ERANGE`|  
  
Si l’une de ces conditions se présente, l’exception de paramètre non valide est appelée, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à continuer, la fonction retourne un code d'erreur et définit `errno`, comme indiqué dans le tableau.  
  
## <a name="remarks"></a>Notes  

Le `wcstombs_s` fonction convertit une chaîne de caractères larges pointés par *wcstr* en caractères multioctets stockés dans la mémoire tampon vers laquelle pointée *mbstr*. La conversion se poursuit pour chaque caractère jusqu'à ce qu'une des conditions suivantes soit remplie :  
  
-   Un caractère large null est rencontré  
  
-   Un caractère large qui ne peut pas être converti est rencontré  
  
-   Le nombre d’octets stockés dans le *mbstr* est égale à la mémoire tampon *nombre*.  
  
La chaîne de destination est toujours terminée par null (même en cas d'erreur).  
  
Si *nombre* est la valeur spéciale [_TRUNCATE](../../c-runtime-library/truncate.md), puis `wcstombs_s` convertit la majeure partie de la chaîne en tenir dans la mémoire tampon de destination, tout en laissant la place pour un terminateur null. Si la chaîne est tronquée, la valeur de retour est `STRUNCATE`, et la conversion est considérée comme réussie.  
  
Si `wcstombs_s` convertit correctement la chaîne source, elle place la taille en octets de la chaîne convertie, y compris la marque de fin null, en `*pReturnValue` (fourni *pReturnValue* n’est pas `NULL`). Cela se produit même si le *mbstr* argument est `NULL` et fournit un moyen de déterminer la taille de la mémoire tampon requise. Notez que si *mbstr* est `NULL`, *nombre* est ignoré.  
  
Si la fonction `wcstombs_s` rencontre un caractère large qu’elle ne peut pas convertir en caractère multioctet, elle place la valeur 0 dans `*pReturnValue`, définit la mémoire tampon de destination comme étant une chaîne vide, affecte à `errno` la valeur `EILSEQ` et retourne `EILSEQ`.  
  
Si les séquences pointées par *wcstr* et *mbstr* se chevauchent, le comportement de `wcstombs_s` n’est pas défini.  
  
> [!IMPORTANT]
>  Vérifiez que *wcstr* et *mbstr* ne se chevauchent pas et que *nombre* reflète fidèlement le nombre de caractères larges à convertir.  
  
La fonction `wcstombs_s` utilise les paramètres régionaux actuels pour tout comportement dépendant des paramètres régionaux ; la fonction `_wcstombs_s_l` est identique à `wcstombs` sauf qu'elle utilise les paramètres régionaux passés à la place. Pour plus d’informations, consultez [Locale](../../c-runtime-library/locale.md).  
  
En C++, l’utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement (ce qui évite d’avoir à spécifier un argument taille) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées. Pour plus d'informations, consultez [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`wcstombs_s`|\<stdlib.h>|  
  
Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Exemple  

Ce programme illustre le comportement de la fonction `wcstombs_s`.  
  
```C  
// crt_wcstombs_s.c  
// This example converts a wide character  
// string to a multibyte character string.  
#include <stdio.h>  
#include <stdlib.h>  
#include <assert.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t   i;  
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t*pWCBuffer = L"Hello, world.";  
  
    printf( "Convert wide-character string:\n" );  
  
    // Conversion  
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,   
               pWCBuffer, (size_t)BUFFER_SIZE );  
  
    // Output  
    printf("   Characters converted: %u\n", i);  
    printf("    Multibyte character: %s\n\n",  
     pMBBuffer );  
  
    // Free multibyte character buffer  
    if (pMBBuffer)  
    {  
    free(pMBBuffer);  
    }  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 14  
    Multibyte character: Hello, world.  
```  
  
## <a name="see-also"></a>Voir aussi  

[Conversion de données](../../c-runtime-library/data-conversion.md)   
[Paramètres régionaux](../../c-runtime-library/locale.md)   
[_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
[mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
[mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
[wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)   
[WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)