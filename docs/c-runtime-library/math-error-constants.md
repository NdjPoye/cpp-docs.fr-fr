---
title: "Constantes d&quot;erreur mathématique | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _PLOSS
- _UNDERFLOW
- _TLOSS
- _SING
- _DOMAIN
- _OVERFLOW
dev_langs:
- C++
helpviewer_keywords:
- _TLOSS constant
- _SING constant
- PLOSS constant
- UNDERFLOW constant
- _UNDERFLOW constant
- _OVERFLOW constant
- DOMAIN constant
- OVERFLOW constant
- TLOSS constant
- SING constant
- _DOMAIN constant
- _PLOSS constant
- math error constants
ms.assetid: 4be933a6-674e-45a5-8ac9-090023542f5b
caps.latest.revision: 6
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 8dd5321d924d02ef7669166a210b193329abc13a
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="math-error-constants"></a>Constantes d'erreur mathématique
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <math.h>  
  
```  
  
## <a name="remarks"></a>Remarques  
 Les routines mathématiques de la bibliothèque Runtime peuvent générer des constantes d’erreur mathématique.  
  
 Ces erreurs, comme indiqué ci-dessous, correspondent aux types d’exception définis dans les MATH.H et sont retournées par la fonction `_matherr` en cas d’erreur mathématique.  
  
|Constante|Signification|  
|--------------|-------------|  
|`_DOMAIN`|L’argument de fonction est en dehors du domaine de la fonction.|  
|`_OVERFLOW`|Le résultat est trop grand pour être représenté dans le type de retour de la fonction.|  
|`_PLOSS`|Perte partielle de précision survenue.|  
|`_SING`|Singularité de l’argument : l’argument de la fonction a une valeur non conforme. (Par exemple, la valeur 0 est passée à une fonction qui requiert une valeur différente de zéro).|  
|`_TLOSS`|Perte totale de précision survenue.|  
|`_UNDERFLOW`|Le résultat est trop petit pour être représenté.|  
  
## <a name="see-also"></a>Voir aussi  
 [_matherr](../c-runtime-library/reference/matherr.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)
