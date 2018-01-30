---
title: "Limites d’entier | Documents Microsoft"
ms.custom: 
ms.date: 01/29/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- integral limits
- limits, integer
- limits.h header file
- integer limits
ms.assetid: 6922bdbf-0f49-443b-bc03-ee182e4cbd57
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a5fc79f225d340777751ca513c0fb47dd33e17ad
ms.sourcegitcommit: 185e11ab93af56ffc650fe42fb5ccdf1683e3847
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2018
---
# <a name="integer-limits"></a>Limites d'entier

**Section spécifique à Microsoft**

Les limites pour les types d'entiers sont répertoriées dans le tableau ci-dessous. Ces limites sont également définies dans le fichier d’en-tête standard < limits.h >.

## <a name="limits-on-integer-constants"></a>Limites appliquées aux constantes entières

|Constante|Signification|Value|
|--------------|-------------|-----------|
|**CHAR_BIT**|Nombre de bits dans la plus petite variable qui n'est pas un champ de bits|8|
|**SCHAR_MIN**|Valeur minimale d'une variable de type **signed char**.|-128|
|**SCHAR_MAX**|Valeur maximale d'une variable de type **signed char**.|127|
|**UCHAR_MAX**|Valeur maximale d’une variable de type **unsigned char**.|255 (0xff)|
|**CHAR_MIN**|Valeur minimale d’une variable de type **char**.|-128 ; 0 si l'option /J est utilisée|
|**CHAR_MAX**|Valeur maximale d’une variable de type **char**.|127 ; 255 si l'option /J est utilisée|
|**MB_LEN_MAX**|Nombre maximal d'octets dans une constante à multiples caractères|5|
|**SHRT_MIN**|Valeur minimale d'une variable de type **short**.|-32768|
|**SHRT_MAX**|Valeur maximale d'une variable de type **short**.|32767|
|**USHRT_MAX**|Valeur maximale d'une variable de type **unsigned short**.|65535 (0xffff)|
|**INT_MIN**|Valeur minimale d’une variable de type **int**.|-2147483648|
|**INT_MAX**|Valeur maximale d’une variable de type **int**.|2147483647|
|**UINT_MAX**|Valeur maximale d’une variable de type **int non signées**.|4294967295 (0xffffffff)|
|**LONG_MIN**|Valeur minimale d'une variable de type **long**.|-2147483648|
|**LONG_MAX**|Valeur maximale d'une variable de type **long**.|2147483647|
|**ULONG_MAX**|Valeur maximale d’une variable de type **long non signé**.|4294967295 (0xffffffff)|
|**LLONG_MIN**|Valeur minimale d’une variable de type **long**|-9223372036854775808|
|**LLONG_MAX**|Valeur maximale d’une variable de type **long**|9223372036854775807|
|**ULLONG_MAX**|Valeur maximale d’une variable de type **long long non signé**|18446744073709551615 (0xffffffffffffffff)|

Si une valeur dépasse la plus grande représentation d'entier, le compilateur Microsoft génère une erreur.

**FIN de la section spécifique à Microsoft**

## <a name="see-also"></a>Voir aussi

[Limites des valeurs à virgule flottante](../cpp/floating-limits.md)  
