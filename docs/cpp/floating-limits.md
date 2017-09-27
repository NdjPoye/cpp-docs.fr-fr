---
title: Flottante limites | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- FLOAT.H header file
- limits, floating-point constants
- floating-point numbers, floating limits
ms.assetid: fc718652-1f4c-4ed8-af60-0e769637459c
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: a19ed24e7765c9b0042831fc2eda9df937be42b3
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="floating-limits"></a>Limites des valeurs à virgule flottante
**Section spécifique à Microsoft**  
  
 Le tableau suivant répertorie les limites applicables aux valeurs des constantes à virgule flottante. Ces limites sont également définies dans le fichier d'en-tête standard FLOAT.H.  
  
### <a name="limits-on-floating-point-constants"></a>Limites sur les constantes à virgule flottante  
  
|Constante|Signification|Valeur|  
|--------------|-------------|-----------|  
|FLT_DIG DBL_DIG LDBL_DIG|Nombre de chiffres, q, tel qu'un nombre à virgule flottante avec q chiffres décimaux peut être arrondi en une représentation à virgule flottante puis restauré à sa valeur initiale sans perte de précision.|6 15 15|  
|FLT_EPSILON DBL_EPSILON LDBL_EPSILON|Plus petit nombre positif x tel que x + 1,0 n'est pas égal à 1,0.|1, 192092896e-07F 2, 2204460492503131e-016 2, 2204460492503131e-016|  
|FLT_GUARD||0|  
|FLT_MANT_DIG DBL_MANT_DIG LDBL_MANT_DIG|Nombre de chiffres dans la base spécifiée par FLT_RADIX dans la mantisse à virgule flottante. La base est 2 ; Par conséquent, ces valeurs spécifient des bits.|24 53 53|  
|FLT_MAX DBL_MAX LDBL_MAX|Nombre à virgule flottante maximal pouvant être représenté.|3,402823466e+38F 1,7976931348623158e+308 1,7976931348623158e+308|  
|FLT_MAX_10_EXP DBL_MAX_10_EXP LDBL_MAX_10_EXP|Entier maximal tel que 10 élevé à ce nombre est un nombre à virgule flottante pouvant être représenté.|38 308 308|  
|FLT_MAX_EXP DBL_MAX_EXP LDBL_MAX_EXP|Entier maximal tel que FLT_RADIX élevé à la puissance de ce nombre est un nombre à virgule flottante qui peut être représenté.|128 1024 1024|  
|FLT_MIN DBL_MIN LDBL_MIN|Valeur positive minimale.|1,175494351e-38F 2,2250738585072014E-308 2,2250738585072014E-308|  
|FLT_MIN_10_EXP DBL_MIN_10_EXP LDBL_MIN_10_EXP|Entier négatif minimal tel que 10 élevé à ce nombre est un nombre à virgule flottante pouvant être représenté.|-37<br /><br /> -307<br /><br /> -307|  
|FLT_MIN_EXP DBL_MIN_EXP LDBL_MIN_EXP|Entier négatif minimal tel que FLT_RADIX élevé à la puissance de ce nombre est un nombre à virgule flottante qui peut être représenté.|-125<br /><br /> -1021<br /><br /> -1021|  
|FLT_NORMALIZE||0|  
|FLT_RADIX _DBL_RADIX _LDBL_RADIX|Base de représentation d'exposant|2 2 2|  
|FLT_ROUNDS _DBL_ROUNDS _LDBL_ROUNDS|Mode d’arrondi pour l’addition à virgule flottante.|1 (environ) 1 (environ) 1 (environ)|  
  
> [!NOTE]
>  Les informations contenues dans le tableau peuvent différer dans les versions ultérieures du produit.  
  
**FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Limites d’entier](../cpp/integer-limits.md)
