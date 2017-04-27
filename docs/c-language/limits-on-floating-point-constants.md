---
title: "Limites des constantes à virgule flottante │ Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- ranges, floating-point constants
- floating-point constants, limits
- FLOAT.H header file
- constants, floating-point
- limits, floating-point constants
- floating-point numbers, floating limits
ms.assetid: 2d975868-2af6-45d7-a8af-db79f2c6b67b
caps.latest.revision: 8
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
translationtype: Human Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 92d89d08fdcd786e665b3ad40e3317f3e24d7a75
ms.lasthandoff: 04/01/2017

---
# <a name="limits-on-floating-point-constants"></a>Limites des constantes à virgule flottante
**Section spécifique à Microsoft**  
  
 Le tableau suivant répertorie les limites applicables aux valeurs des constantes à virgule flottante. Le fichier d'en-tête FLOAT.H contient ces informations.  
  
### <a name="limits-on-floating-point-constants"></a>Limites sur les constantes à virgule flottante  
  
|Constante|Signification|Valeur|  
|--------------|-------------|-----------|  
|**FLT_DIG**<br />**DBL_DIG**<br />**LDBL_DIG**|Nombre de chiffres, *q*, de sorte qu’un nombre à virgule flottante avec *q* chiffres décimaux peut être arrondi en représentation à virgule flottante puis restauré à sa valeur initiale sans perte de précision.|6<br />15<br />15|  
|**FLT_EPSILON**<br />**DBL_EPSILON**<br />**LDBL_EPSILON**|Plus petit nombre positif *x* de sorte que *x* + 1,0 n’est pas égal à 1,0|1,192092896e-07F<br />2,2204460492503131e-016<br />2,2204460492503131e-016|  
|**FLT_GUARD**||0|  
|**FLT_MANT_DIG**<br />**DBL_MANT_DIG**<br />**LDBL_MANT_DIG**|Nombre de chiffres dans la base spécifiée par **FLT_RADIX** dans la mantisse à virgule flottante. La base est 2 ; par conséquent, ces valeurs spécifient des bits.|24<br />53<br />53|  
|**FLT_MAX**<br />**DBL_MAX**<br />**LDBL_MAX**|Nombre à virgule flottante maximal pouvant être représenté|3,402823466e+38F<br />1,7976931348623158e+308<br />1,7976931348623158e+308|  
|**FLT_MAX_10_EXP**<br />**DBL_MAX_10_EXP**<br />**LDBL_MAX_10_EXP**|Entier maximal tel que 10 élevé à la puissance de ce nombre est un nombre à virgule flottante pouvant être représenté.|38<br />308<br />308|  
|**FLT_MAX_EXP**<br />**DBL_MAX_EXP**<br />**LDBL_MAX_EXP**|Entier maximal de sorte que **FLT_RADIX** élevé à la puissance de ce nombre est un nombre à virgule flottante qui peut être représenté.|128<br />1024<br />1024|  
|**FLT_MIN**<br />**DBL_MIN**<br />**LDBL_MIN**|Valeur positive minimale.|1,175494351e-38F<br />2,2250738585072014E-308<br />2,2250738585072014E-308|  
|**FLT_MIN_10_EXP**<br />**DBL_MIN_10_EXP**<br />**LDBL_MIN_10_EXP**|Entier négatif minimal tel que 10 élevé à la puissance de ce nombre est un nombre à virgule flottante pouvant être représenté.|-37<br />-307<br />-307|  
|**FLT_MIN_EXP**<br />**DBL_MIN_EXP**<br />**LDBL_MIN_EXP**|Entier négatif minimal de sorte que **FLT_RADIX** élevé à la puissance de ce nombre est un nombre à virgule flottante qui peut être représenté.|-125<br />-1021<br />-1021|  
|**FLT_NORMALIZE**||0|  
|**FLT_RADIX**<br />**_DBL_RADIX**<br />**_LDBL_RADIX**|Base de représentation d'exposant|2<br />2<br />2|  
|**FLT_ROUNDS**<br />**_DBL_ROUNDS**<br />**_LDBL_ROUNDS**|Mode d'arrondi pour l'addition à virgule flottante|1 (arrondi)<br />1 (arrondi)<br />1 (arrondi)|  
  
 Notez que les informations fournies dans le tableau ci-dessus peuvent différer dans des implémentations futures.  
  
 **Fin de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Constantes à virgule flottante C](../c-language/c-floating-point-constants.md)
