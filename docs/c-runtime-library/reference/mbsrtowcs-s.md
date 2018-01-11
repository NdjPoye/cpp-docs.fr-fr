---
title: mbsrtowcs_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: mbsrtowcs_s
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
f1_keywords: mbsrtowcs_s
dev_langs: C++
helpviewer_keywords: mbsrtowcs_s function
ms.assetid: 4ee084ec-b15d-4e5a-921d-6584ec3b5a60
caps.latest.revision: "24"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b701362fd8ed19575f5de34f998bc8fd4f7e6de1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mbsrtowcss"></a>mbsrtowcs_s
Convertir une chaîne de caractères multioctets correspondant aux paramètres régionaux actuels en sa représentation sous forme de chaîne de caractères larges. Version de [mbsrtowcs](../../c-runtime-library/reference/mbsrtowcs.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t * wcstr,  
   size_t sizeInWords,  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
);  
template <size_t size>  
errno_t mbsrtowcs_s(  
   size_t * pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char ** mbstr,  
   size_t count,  
   mbstate_t * mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `pReturnValue`  
 Nombre de caractères convertis.  
  
 [out] `wcstr`  
 Adresse de la mémoire tampon où stocker la chaîne de caractères larges convertie.  
  
 [out] `sizeInWords`  
 La taille de `wcstr` en mots (caractères étendus).  
  
 [in, out] `mbstr`  
 Pointeur indirect vers l'emplacement de la chaîne de caractères multioctets à convertir.  
  
 [in] `count`  
 Nombre maximal de caractères larges à stocker dans la mémoire tampon `wcstr`, à l’exclusion du caractère Null de fin, ou [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in, out] `mbstate`  
 Un pointeur vers un objet d'état de conversion `mbstate_t`. Si cette valeur est un pointeur null, un objet d'état de conversion interne statique est utilisé. Comme l'objet `mbstate_t` interne n'est pas thread-safe, nous vous recommandons de toujours passer votre propre paramètre `mbstate`.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si la conversion est réussie, ou un code d'erreur en cas d'échec.  
  
|Condition d'erreur|Valeur de retour et `errno`|  
|---------------------|------------------------------|  
|`wcstr` est un pointeur Null et `sizeInWords` > 0|`EINVAL`|  
|`mbstr` est un pointeur Null|`EINVAL`|  
|La chaîne indirectement pointée par `mbstr` contient une séquence multioctets qui n'est pas valide pour les paramètres régionaux actuels.|`EILSEQ`|  
|La mémoire tampon de destination est trop petite pour contenir la chaîne convertie (à moins que `count` ait la valeur `_TRUNCATE` ; pour plus d'informations, consultez les notes ci-dessous).|`ERANGE`|  
  
 Si l’une de ces conditions se produit, l’exception de paramètre non valide est appelée, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à continuer, la fonction retourne un code d'erreur et définit `errno`, comme indiqué dans le tableau.  
  
## <a name="remarks"></a>Notes  
 La fonction `mbsrtowcs_s` convertit une chaîne de caractères multioctets indirectement pointée par `mbstr` en caractères larges stockés dans la mémoire tampon pointée par `wcstr`, en utilisant l'état de conversion contenu dans `mbstate`. La conversion se poursuit pour chaque caractère jusqu'à ce qu'une des conditions suivantes soit remplie :  
  
-   Un caractère multioctet de null est rencontré.  
  
-   Un caractère multioctet non valide est rencontré.  
  
-   Le nombre caractères larges stockés dans la mémoire tampon de `wcstr` est égal à `count`.  
  
 La chaîne de destination `wcstr` est toujours terminée par un caractère Null, même en cas d'erreur, sauf si `wcstr` est un pointeur Null.  
  
 Si `count` correspond à la valeur spéciale [_TRUNCATE](../../c-runtime-library/truncate.md), `mbsrtowcs_s` convertit la plus grande partie possible de la chaîne en fonction de la capacité de la mémoire tampon de destination, tout en laissant de l’espace pour une marque de fin Null.  
  
 Si `mbsrtowcs_s` convertit correctement la chaîne source, elle place la taille en caractères larges de la chaîne convertie et la marque de fin Null dans `*pReturnValue`, à condition que `pReturnValue` ne soit pas un pointeur Null. Cela se produit même si l'argument `wcstr` est un pointeur Null et vous laisse déterminer la taille de mémoire tampon requise. Notez que si `wcstr` est un pointeur Null, `count` est ignoré.  
  
 Si `wcstr` n'est pas un pointeur Null, l'objet de pointeur pointé par `mbstr` est affecté d'un pointeur Null si la conversion a été arrêtée, car un caractère Null de fin a été atteint. Sinon, il est affecté de l'adresse qui se trouve juste après le dernier caractère multioctet converti, le cas échéant. Ceci permet à un appel de fonction ultérieur de redémarrer la conversion où cet appel s'est arrêté.  
  
 Si `mbstate` est un pointeur Null, l'objet statique d'état de la conversion `mbstate_t` interne de la bibliothèque est utilisé. Comme cet objet statique interne n'est pas thread-safe, nous vous recommandons de passer votre propre valeur de `mbstate`.  
  
 Si `mbsrtowcs_s` rencontre un caractère multioctet qui n’est pas valide dans les paramètres régionaux actuels, il place -1 dans `*pReturnValue`, définit la mémoire tampon de destination `wcstr` avec une chaîne vide, définit `errno` à `EILSEQ` et retourne `EILSEQ`.  
  
 Si les séquences pointées par `mbstr` et `wcstr` se chevauchent, le comportement de `mbsrtowcs_s` n'est pas défini. `mbsrtowcs_s` est affecté par la catégorie LC_TYPE des paramètres régionaux actuels.  
  
> [!IMPORTANT]
>  Vérifiez que `wcstr` et `mbstr` ne se chevauchent pas, et que `count` reflète correctement le nombre de caractères multioctets à convertir.  
  
 La fonction `mbsrtowcs_s` diffère de [mbstowcs_s, _mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md) par sa capacité à redémarrer. L'état de la conversion est stocké dans `mbstate` pour les appels suivants à la même ou à d'autres fonctions redémarrables. Les résultats ne sont pas définis quand l'utilisation de fonctions redémarrables est combinée avec l'utilisation de fonctions non redémarrables. Par exemple, une application doit utiliser `mbsrlen` au lieu de `mbslen`, si un appel ultérieur à `mbsrtowcs_s` est utilisé à la place de`mbstowcs_s.`  
  
 En C++, l’utilisation de cette fonction est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement (ce qui évite d’avoir à spécifier un argument de taille) et elles peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalents plus récents et sécurisés. Pour plus d'informations, consultez [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Exceptions  
 La fonction `mbsrtowcs_s` est multithread-safe si aucune fonction du thread actif n'appelle `setlocale` aussi longtemps que cette fonction s'exécute et que l'argument `mbstate` n'est pas un pointeur Null.  
  
## <a name="requirements"></a>Configuration requise  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`mbsrtowcs_s`|\<wchar.h>|  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [mbstowcs_s, _mbstowcs_s_l](../../c-runtime-library/reference/mbstowcs-s-mbstowcs-s-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)