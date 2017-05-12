---
title: _ecvt_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ecvt_s
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
- ecvt_s
- _ecvt_s
dev_langs:
- C++
helpviewer_keywords:
- _ecvt_s function
- ecvt_s function
- numbers, converting
- converting double numbers
ms.assetid: d52fb0a6-cb91-423f-80b3-952a8955d914
caps.latest.revision: 25
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
ms.openlocfilehash: 81bcb9fe1306f5affa49672269890d6f5888a3ac
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="ecvts"></a>_ecvt_s
Convertit un nombre `double` en chaîne. Il s’agit d’une version de [_ecvt](../../c-runtime-library/reference/ecvt.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _ecvt_s(   
   char * _Buffer,  
   size_t _SizeInBytes,  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
);  
template <size_t size>  
errno_t _ecvt_s(   
   char (&_Buffer)[size],  
   double _Value,  
   int _Count,  
   int *_Dec,  
   int *_Sign  
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `_Buffer`  
 Rempli avec le pointeur désignant la chaîne de chiffres, le résultat de la conversion.  
  
 [in] `_SizeInBytes`  
 Taille, en octets, de la mémoire tampon.  
  
 [in] `_Value`  
 Nombre à convertir.  
  
 [in] `_Count`  
 Nombre de chiffres stockés.  
  
 [out] `_Dec`  
 Position de la virgule décimale stockée.  
  
 [out] `_Sign`  
 Signe du nombre converti.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l’opération réussit. En cas d’échec, la valeur de retour est un code d’erreur. Les codes d’erreur sont définis dans Errno.h. Pour plus d’informations, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 En cas de paramètre non valide, comme indiqué dans le tableau suivant, cette fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `EINVAL`.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`_Buffer`|`_SizeInBytes`|_Value|_Count|_Dec|_Sign|Valeur de retour|Valeur dans `buffer`|  
|---------------|--------------------|-------------|-------------|-----------|------------|------------------|-----------------------|  
|`NULL`|any|any|any|any|any|`EINVAL`|Non modifiée.|  
|Pas `NULL` (pointe vers une mémoire valide)|<=0|any|any|any|any|`EINVAL`|Non modifiée.|  
|any|any|any|any|`NULL`|any|`EINVAL`|Non modifiée.|  
|any|any|any|any|any|`NULL`|`EINVAL`|Non modifiée.|  
  
 **Problèmes de sécurité**  
  
 `_ecvt_s` peut générer une violation d’accès si `buffer` ne désigne pas une mémoire valide et n’est pas `NULL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_ecvt_s` convertit un nombre à virgule flottante en une chaîne de caractères. Le paramètre `_Value` est le nombre à virgule flottante à convertir. Cette fonction stocke jusqu’à `count` chiffres de `_Value` sous forme de chaîne et ajoute un caractère null (« \0 »). Si le nombre de chiffres dans `_Value` dépasse `_Count`, le chiffre de poids faible est arrondi. S’il y a moins de `count` chiffres, la chaîne est remplie de zéros.  
  
 Seuls des chiffres sont stockés dans la chaîne. La position de la virgule décimale et le signe de `_Value` peuvent être obtenus à partir de `_Dec` et `_Sign` après l’appel. Le paramètre `_Dec` pointe vers une valeur entière indiquant la position de la virgule décimale par rapport au début de la chaîne. Une valeur entière ou 0 indique que la virgule décimale est située à gauche du premier chiffre. Le paramètre `_Sign` pointe vers un entier qui indique le signe du nombre converti. Si la valeur entière est 0, le nombre est positif. Sinon, le nombre est négatif.  
  
 Une mémoire tampon de longueur `_CVTBUFSIZE` est suffisante pour n’importe quelle valeur à virgule flottante.  
  
 La différence entre `_ecvt_s` et `_fcvt_s` réside dans l’interprétation du paramètre `_Count`. `_ecvt_s` interprète `_Count` comme le nombre total de chiffres dans la chaîne de sortie, tandis que `_fcvt_s` interprète `_Count` en tant que nombre de chiffres après la virgule décimale.  
  
 En C++, l’utilisation de cette fonction est simplifiée par une surcharge de modèle ; la surcharge peut déduire automatiquement la longueur de la mémoire tampon, ce qui évite d’avoir à spécifier un argument de taille. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 La version de débogage de cette fonction remplit d’abord la mémoire tampon avec 0xFD. Pour désactiver ce comportement, utilisez [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|En-tête facultatif|  
|--------------|---------------------|---------------------|  
|`_ecvt_s`|\<stdlib.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// ecvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( )  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _ecvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_ecvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 12000  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)
