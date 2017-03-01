---
title: _fcvt | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fcvt
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
- _fcvt
dev_langs:
- C++
helpviewer_keywords:
- converting floating point, to strings
- _fcvt function
- floating-point functions, converting number to string
- fcvt function
- floating-point functions
ms.assetid: 74584c88-f0dd-4907-8fca-52da5df583f5
caps.latest.revision: 24
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 9f191d64115bca85502d8fd3fbe0525c0e2be65c
ms.lasthandoff: 02/24/2017

---
# <a name="fcvt"></a>_fcvt
Convertir un nombre à virgule flottante en chaîne. Une version plus sécurisée de cette fonction est disponible. Consultez [_fcvt_s](../../c-runtime-library/reference/fcvt-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
char *_fcvt(   
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
 Nombre de chiffres après la virgule décimale.  
  
 `dec`  
 Pointeur désignant la position de la virgule décimale stockée.  
  
 `sign`  
 Pointeur désignant l’indicateur de signe stocké.  
  
## <a name="return-value"></a>Valeur de retour  
 `_fcvt` retourne un pointeur désignant la chaîne de chiffres, ou NULL en cas d’erreur.  
  
## <a name="remarks"></a>Notes  
 La fonction `_fcvt` convertit un nombre à virgule flottante en une chaîne de caractères se terminant par un caractère Null. Le paramètre `value` est le nombre à virgule flottante à convertir. `_fcvt` stocke les chiffres de `value` sous forme de chaîne et ajoute un caractère null (« \0 »). Le paramètre `count` spécifie le nombre de chiffres à stocker après la virgule décimale. Les chiffres en trop sont arrondis au niveau de `count` positions après la virgule. Si le nombre de chiffres de précision est inférieur à `count`, la chaîne est remplie de zéros.  
  
 Le nombre total de chiffres retournés par `_fcvt` ne dépasse pas `_CVTBUFSIZE`.  
  
 Seuls des chiffres sont stockés dans la chaîne. La position de la virgule décimale et le signe de `value` peuvent être obtenus à partir de `dec` et sign après l’appel. Le paramètre `dec` désigne une valeur entière ; celle-ci indique la position de la virgule décimale par rapport au début de la chaîne. Une valeur entière ou zéro indique que la virgule décimale est située à gauche du premier chiffre. Le paramètre `sign` désigne un entier indiquant le signe de `value`. L’entier est défini sur 0 si `value` est positif, et sur un nombre différent de zéro si `value` est négatif.  
  
 La différence entre `_ecvt` et `_fcvt` réside dans l’interprétation du paramètre `count`. `_ecvt` interprète `count` comme le nombre total de chiffres dans la chaîne de sortie, tandis que `_fcvt` interprète `count` en tant que nombre de chiffres après la virgule décimale.  
  
 `_ecvt` et `_fcvt` utilisent une seule mémoire tampon allouée de manière statique pour la conversion. Chaque appel à une de ces routines détruit les résultats de l’appel précédent.  
  
 Cette fonction valide ses paramètres. Si `dec` ou `sign` est NULL ou que `count` vaut 0, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `errno` prend la valeur `EINVAL` et NULL est retourné.  
  
## <a name="requirements"></a>Spécifications  
  
|Fonction|En-tête requis|  
|--------------|---------------------|  
|`_fcvt`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_fcvt.c  
// compile with: /W3  
// This program converts the constant  
// 3.1415926535 to a string and sets the pointer  
// buffer to point to that string.  
  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int  decimal, sign;  
   char *buffer;  
   double source = 3.1415926535;  
  
   buffer = _fcvt( source, 7, &decimal, &sign ); // C4996  
   // Note: _fcvt is deprecated; consider using _fcvt_s instead  
   printf( "source: %2.10f   buffer: '%s'   decimal: %d   sign: %d\n",  
            source, buffer, decimal, sign );  
}  
```  
  
```Output  
source: 3.1415926535   buffer: '31415927'   decimal: 1   sign: 0  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 [System::Convert::ToString](https://msdn.microsoft.com/en-us/library/system.convert.tostring.aspx)  
  
## <a name="see-also"></a>Voir aussi  
 [Conversion de données](../../c-runtime-library/data-conversion.md)   
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [atof, _atof_l, _wtof, _wtof_l](../../c-runtime-library/reference/atof-atof-l-wtof-wtof-l.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)
