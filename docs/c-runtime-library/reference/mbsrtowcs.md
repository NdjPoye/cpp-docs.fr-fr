---
title: mbsrtowcs | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- mbsrtowcs
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
- mbsrtowcs
dev_langs:
- C++
helpviewer_keywords:
- mbsrtowcs function
ms.assetid: f3a29de8-e36e-425b-a7fa-a258e6d7909d
caps.latest.revision: 20
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
ms.openlocfilehash: bec54ca0efe0f8aefabbe0c616e283b64fd22166
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="mbsrtowcs"></a>mbsrtowcs
Convertit une chaîne de caractères multioctets dans les paramètres régionaux actuels en une chaîne de caractères larges correspondante, avec la capacité de redémarrer au milieu d'un caractère multioctet. Une version plus sécurisée de cette fonction est disponible ; consultez [mbsrtowcs_s](../../c-runtime-library/reference/mbsrtowcs-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
size_t mbsrtowcs(  
   wchar_t *wcstr,  
   const char **mbstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t mbsrtowcs(  
   wchar_t (&wcstr)[size],  
   const char **mbstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `wcstr`  
 Adresse où stocker la chaîne de caractères larges convertie.  
  
 [in, out] `mbstr`  
 Pointeur indirect vers l'emplacement de la chaîne de caractères multioctets à convertir.  
  
 [in] `count`  
 Nombre maximal de caractères (et non pas d'octets) à convertir et à stocker dans `wcstr`.  
  
 [in, out] `mbstate`  
 Un pointeur vers un objet d'état de conversion `mbstate_t`. Si cette valeur est un pointeur null, un objet d'état de conversion interne statique est utilisé. Comme l'objet `mbstate_t` interne n'est pas thread-safe, nous vous recommandons de toujours passer votre propre paramètre `mbstate`.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne le nombre de caractères correctement convertis, non compris le caractère null de fin, le cas échéant. Retourne (size_t)(-1) si une erreur s'est produite et définit `errno` à EILSEQ.  
  
## <a name="remarks"></a>Notes  
 La fonction `mbsrtowcs` convertit une chaîne de caractères multioctets indirectement pointée par `mbstr` en caractères larges stockés dans la mémoire tampon pointée par `wcstr`, en utilisant l'état de conversion contenu dans `mbstate`. La conversion continue pour chaque caractère jusqu'à ce que soit rencontré un caractère multioctet null de fin ou une séquence multioctet qui ne correspond pas à un caractère valide dans les paramètres régionaux actuels, ou jusqu'à ce que `count` caractères aient été convertis. Si `mbsrtowcs` rencontre le caractère null multioctet (« \0 ») avant ou au moment où `count` est atteint, elle le convertit en un caractère null de fin sur 16 bits et s'arrête.  
  
 Par conséquent, la chaîne de caractères larges dans `wcstr` est terminée par un caractère null seulement si `mbsrtowcs` rencontre un caractère null multioctet pendant la conversion. Si les séquences pointées par `mbstr` et `wcstr` se chevauchent, le comportement de `mbsrtowcs` n'est pas défini. `mbsrtowcs` est affecté par la catégorie LC_TYPE des paramètres régionaux actuels.  
  
 La fonction `mbsrtowcs` diffère de [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) par sa capacité à redémarrer. L'état de la conversion est stocké dans `mbstate` pour les appels suivants à la même ou à d'autres fonctions redémarrables. Les résultats ne sont pas définis quand l'utilisation de fonctions redémarrables est combinée avec l'utilisation de fonctions non redémarrables.  Par exemple, une application doit utiliser `mbsrlen` au lieu de `mbslen`, si un appel ultérieur à `mbsrtowcs` est utilisé à la place de`mbstowcs.`  
  
 Si `wcstr` n'est pas un pointeur null, l'objet de pointeur pointé par `mbstr` est affecté d'un pointeur null si la conversion a été arrêtée, car un caractère null de fin a été atteint. Sinon, il est affecté de l'adresse qui se trouve juste après le dernier caractère multioctet converti, le cas échéant. Ceci permet à un appel de fonction ultérieur de redémarrer la conversion où cet appel s'est arrêté.  
  
 Si l'argument `wcstr` est un pointeur null, l'argument `count` est ignoré et `mbsrtowcs` retourne la taille requise en caractères larges pour la chaîne de destination. Si `mbstate` est un pointeur null, la fonction utilise un objet d'état de conversion `mbstate_t` interne statique qui n'est pas thread-safe. Si la séquence de caractères `mbstr` n'a pas de représentation correspondante en caractères multioctets, la valeur -1 est retournée et `errno` est défini à `EILSEQ`.  
  
 Si `mbstr` est un pointeur null, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte à `errno` la valeur `EINVAL` et retourne -1.  
  
 En C++, cette fonction a une surcharge de modèle qui appelle l'équivalent plus récent et sécurisé de cette fonction. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Exceptions  
 La fonction `mbsrtowcs` est multithread-safe tant qu'aucune fonction dans le thread actif n'appelle `setlocale` dès lors que cette fonction est en cours d'exécution et que l'argument `mbstate` n'est pas un pointeur null.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`mbsrtowcs`|\<wchar.h>|  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Paramètres régionaux](../../c-runtime-library/locale.md)   
 [Interprétation des séquences de caractères multioctets](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbrtowc](../../c-runtime-library/reference/mbrtowc.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)
