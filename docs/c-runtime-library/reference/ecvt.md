---
title: _ecvt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _ecvt
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
- _ecvt
dev_langs:
- C++
helpviewer_keywords:
- _ecvt function
- numbers, converting
- converting double numbers
- ecvt function
ms.assetid: a916eb05-92d1-4b5c-8563-093acdb49dc8
caps.latest.revision: 21
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
ms.openlocfilehash: c3992066b5b305a7b9de6ef47c6ba42e15da2518
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="ecvt"></a>_ecvt
Convertit un nombre `double` en chaîne. Une version plus sécurisée de cette fonction est disponible. Consultez [_ecvt_s](../../c-runtime-library/reference/ecvt-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *_ecvt(   
   double value,  
   int count,  
   int *dec,  
   int *sign   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `value`  
 Nombre à convertir.  
  
 `count`  
 Nombre de chiffres stockés.  
  
 `dec`  
 Position de la virgule décimale stockée.  
  
 `sign`  
 Signe du nombre converti.  
  
## <a name="return-value"></a>Valeur de retour  
 `_ecvt` retourne un pointeur désignant la chaîne de chiffres, ou NULL si une erreur s’est produite.  
  
## <a name="remarks"></a>Notes  
 La fonction `_ecvt` convertit un nombre à virgule flottante en une chaîne de caractères. Le paramètre `value` est le nombre à virgule flottante à convertir. Cette fonction stocke jusqu’à `count` chiffres de `value` sous forme de chaîne et ajoute un caractère null (« \0 »). Si le nombre de chiffres dans `value` dépasse `count`, le chiffre de poids faible est arrondi. S’il y a moins de `count` chiffres, la chaîne est remplie de zéros.  
  
 Le nombre total de chiffres retournés par `_ecvt` ne dépasse pas `_CVTBUFSIZE`.  
  
 Seuls des chiffres sont stockés dans la chaîne. La position de la virgule décimale et le signe de `value` peuvent être obtenus à partir de `dec` et `sign` après l’appel. Le paramètre `dec` pointe vers une valeur entière indiquant la position de la virgule décimale par rapport au début de la chaîne. Une valeur entière ou 0 indique que la virgule décimale est située à gauche du premier chiffre. Le paramètre `sign` pointe vers un entier qui indique le signe du nombre converti. Si la valeur entière est 0, le nombre est positif. Sinon, le nombre est négatif.  
  
 La différence entre `_ecvt` et `_fcvt` réside dans l’interprétation du paramètre `count`. `_ecvt` interprète `count` comme le nombre total de chiffres dans la chaîne de sortie, tandis que `_fcvt` interprète `count` en tant que nombre de chiffres après la virgule décimale.  
  
 `_ecvt` et `_fcvt` utilisent une seule mémoire tampon allouée de manière statique pour la conversion. Chaque appel à une de ces routines détruit le résultat de l’appel précédent.  
  
 Cette fonction valide ses paramètres. Si `dec` ou `sign` est NULL ou que `count` vaut 0, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `errno` prend la valeur `EINVAL` et NULL est retourné.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`_ecvt`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_ecvt.c  
// compile with: /W3  
// This program uses _ecvt to convert a  
// floating-point number to a character string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int     decimal,   sign;  
   char    *buffer;  
   int     precision = 10;  
   double  source = 3.1415926535;  
  
   buffer = _ecvt( source, precision, &decimal, &sign ); // C4996  
   // Note: _ecvt is deprecated; consider using _ecvt_s instead  
   printf( "source: %2.10f   buffer: '%s'  decimal: %d  sign: %d\n",  
           source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '3141592654'  decimal: 1  sign: 0  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)
