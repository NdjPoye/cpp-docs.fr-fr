---
title: _fcvt_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fcvt_s
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
- fcvt_s
- _fcvt_s
dev_langs:
- C++
helpviewer_keywords:
- fcvt_s function
- converting floating point, to strings
- floating-point functions, converting number to string
- _fcvt_s function
ms.assetid: 48671197-1d29-4c2b-a5d8-d2368f5f68a1
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 9c282757ae79367cdc2ee72b3f3ce8d0e50983fa
ms.contentlocale: fr-fr
ms.lasthandoff: 04/04/2017

---
# <a name="fcvts"></a>_fcvt_s
Convertir un nombre à virgule flottante en chaîne. Il s’agit d’une version de [_fcvt](../../c-runtime-library/reference/fcvt.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t _fcvt_s(   
   char* buffer,  
   size_t sizeInBytes,  
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
template <size_t size>  
errno_t _fcvt_s(   
   char (&buffer)[size],  
   double value,  
   int count,  
   int *dec,  
   int *sign   
); // C++ only  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `buffer`  
 La mémoire tampon fournie destinée à contenir le résultat de la conversion.  
  
 [in] `sizeInBytes`  
 Taille de la mémoire tampon en octets.  
  
 [in] `value`  
 Nombre à convertir.  
  
 [in] `count`  
 Nombre de chiffres après la virgule décimale.  
  
 [out] `dec`  
 Pointeur désignant la position de la virgule décimale stockée.  
  
 [out] `sign`  
 Pointeur désignant l’indicateur de signe stocké.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l’opération réussit. En cas d’échec, la valeur de retour est un code d’erreur. Les codes d’erreur sont définis dans Errno.h. Pour obtenir la liste de ces erreurs, consultez [errno, _doserrno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
 En cas de paramètre non valide, comme indiqué dans le tableau suivant, cette fonction appelle le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l'exécution est autorisée à se poursuivre, cette fonction affecte la valeur `errno` à `EINVAL` et retourne `EINVAL`.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`buffer`|`sizeInBytes`|valeur|count|dec|sign|Return|Valeur dans `buffer`|  
|--------------|-------------------|-----------|-----------|---------|----------|------------|-----------------------|  
|`NULL`|any|any|any|any|any|`EINVAL`|Non modifiée.|  
|Pas `NULL` (pointe vers une mémoire valide)|<=0|any|any|any|any|`EINVAL`|Non modifiée.|  
|any|any|any|any|`NULL`|any|`EINVAL`|Non modifiée.|  
|any|any|any|any|any|`NULL`|`EINVAL`|Non modifiée.|  
  
 **Problèmes de sécurité**  
  
 `_fcvt_s` peut générer une violation d’accès si `buffer` ne désigne pas une mémoire valide et n’est pas `NULL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_fcvt_s` convertit un nombre à virgule flottante en une chaîne de caractères se terminant par un caractère Null. Le paramètre `value` est le nombre à virgule flottante à convertir. `_fcvt_s` stocke les chiffres de `value` sous forme de chaîne et ajoute un caractère null (« \0 »). Le paramètre `count` spécifie le nombre de chiffres à stocker après la virgule décimale. Les chiffres en trop sont arrondis au niveau de `count` positions après la virgule. Si le nombre de chiffres de précision est inférieur à `count`, la chaîne est remplie de zéros.  
  
 Seuls des chiffres sont stockés dans la chaîne. La position de la virgule décimale et le signe de `value` peuvent être obtenus à partir de `dec` et `sign` après l’appel. Le paramètre `dec` désigne une valeur entière ; celle-ci indique la position de la virgule décimale par rapport au début de la chaîne. Une valeur entière ou zéro indique que la virgule décimale est située à gauche du premier chiffre. Le paramètre `sign` désigne un entier indiquant le signe de `value`. L’entier est défini sur 0 si `value` est positif, et sur un nombre différent de zéro si `value` est négatif.  
  
 Une mémoire tampon de longueur `_CVTBUFSIZE` est suffisante pour n’importe quelle valeur à virgule flottante.  
  
 La différence entre `_ecvt_s` et `_fcvt_s` réside dans l’interprétation du paramètre `count`. `_ecvt_s`interprète `count` comme le nombre total de chiffres dans la chaîne de sortie, et `_fcvt_s` interprète `count` en tant que le nombre de chiffres après la virgule décimale.  
  
 En C++, l’utilisation de cette fonction est simplifiée par une surcharge de modèle ; la surcharge peut déduire automatiquement la longueur de la mémoire tampon, ce qui évite d’avoir à spécifier un argument de taille. Pour plus d’informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
 La version de débogage de cette fonction remplit d’abord la mémoire tampon avec 0xFD. Pour désactiver ce comportement, utilisez [_CrtSetDebugFillThreshold](../../c-runtime-library/reference/crtsetdebugfillthreshold.md).  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|En-tête facultatif|  
|--------------|---------------------|---------------------|  
|`_fcvt_s`|\<stdlib.h>|\<errno.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
 **Bibliothèques :** toutes les versions des [fonctions de bibliothèque CRT](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// fcvt_s.c  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main()  
{  
  char * buf = 0;  
  int decimal;  
  int sign;  
  int err;  
  
  buf = (char*) malloc(_CVTBUFSIZE);  
  err = _fcvt_s(buf, _CVTBUFSIZE, 1.2, 5, &decimal, &sign);  
  
  if (err != 0)  
  {  
     printf("_fcvt_s failed with error code %d\n", err);  
     exit(1);  
  }  
  
  printf("Converted value: %s\n", buf);    
  
}  
```  
  
```Output  
Converted value: 120000  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md)   
 [_gcvt_s](../../c-runtime-library/reference/gcvt-s.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)
