---
title: _gcvt_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _gcvt_s
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
- _gcvt_s
- gcvt_s
dev_langs:
- C++
helpviewer_keywords:
- _gcvt_s function
- _CVTBUFSIZE
- floating-point functions, converting number to string
- gcvt_s function
- numbers, converting to strings
- conversions, floating point to strings
- strings [C++], converting from floating point
- CVTBUFSIZE
ms.assetid: 0a8d8a26-5940-4ae3-835e-0aa6ec1b0744
caps.latest.revision: 30
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
ms.openlocfilehash: cc1f34eae067f0d2cc0781c9001af550b291006f
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="gcvts"></a>_gcvt_s
Convertit une valeur à virgule flottante en chaîne. Il s’agit d’une version de [_gcvt](../../c-runtime-library/reference/gcvt.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _gcvt_s(   
   char *buffer,  
   size_t sizeInBytes,  
   double value,  
   int digits   
);  
template <size_t cchStr>  
errno_t _gcvt_s(   
   char (&buffer)[cchStr],  
   double value,  
   int digits   
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `buffer`  
 Mémoire tampon pour stocker le résultat de la conversion.  
  
 [in] `sizeInBytes`  
 Taille de la mémoire tampon.  
  
 [in] `value`  
 Valeur à convertir.  
  
 [in] `digits`  
 Nombre de chiffres significatifs stockés.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l’opération réussit. En cas d’échec en raison d’un paramètre non valide (voir le tableau ci-après pour découvrir les valeurs non valides), le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, un code d’erreur est retourné. Les codes d’erreur sont définis dans Errno.h. Pour obtenir la liste de ces erreurs, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`buffer`|`sizeInBytes`|`value`|`digits`|Retourner|Valeur dans `buffer`|  
|--------------|-------------------|-------------|--------------|------------|-----------------------|  
|`NULL`|any|any|any|`EINVAL`|Non modifiée.|  
|Pas `NULL` (pointe vers une mémoire valide)|zéro|any|any|`EINVAL`|Non modifiée.|  
|Pas `NULL` (pointe vers une mémoire valide)|any|any|>= `sizeInBytes`|`EINVAL`|Non modifiée.|  
  
 **Problèmes de sécurité**  
  
 `_gcvt_s` peut générer une violation d’accès si `buffer` ne désigne pas une mémoire valide et n’est pas `NULL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_gcvt_s` convertit une `value` à virgule flottante en une chaîne de caractères (qui inclut une virgule décimale et, éventuellement, un octet de signe) et stocke la chaîne dans `buffer`. `buffer` doit être assez grand pour contenir la valeur convertie, plus un caractère Null de fin, qui est ajouté automatiquement. Une mémoire tampon de longueur `_CVTBUFSIZE` est suffisante pour n’importe quelle valeur à virgule flottante. Si la taille de mémoire tampon utilisée est `digits` + 1, la fonction ne remplace pas la fin de la mémoire tampon ; veillez donc à fournir une mémoire tampon suffisante pour cette opération. `_gcvt_s` tente de produire `digits` chiffres au format décimal. Si elle n’y parvient pas, elle génère `digits` chiffres au format exponentiel. Les zéros de fin peuvent être supprimés pendant la conversion.  
  
 En C++, l’utilisation de cette fonction est simplifiée par une surcharge de modèle ; la surcharge peut déduire automatiquement la longueur de la mémoire tampon, ce qui évite d’avoir à spécifier un argument de taille. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 La version de débogage de cette fonction remplit d’abord la mémoire tampon avec 0xFD. Pour désactiver ce comportement, utilisez [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|En-tête facultatif|  
|-------------|---------------------|---------------------|  
|`_gcvt_s`|\<stdlib.h>|\<error.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_gcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char buf[_CVTBUFSIZE];  
  int decimal;  
  int sign;  
  int err;  
  
  err = _gcvt_s(buf, _CVTBUFSIZE, 1.2, 5);  
  
  if (err != 0)  
  {  
     printf("_gcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 1.2  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)
