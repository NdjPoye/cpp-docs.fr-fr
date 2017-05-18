---
title: '&lt;iomanip&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- iomanip/std::<iomanip>
- std::<iomanip>
- <iomanip>
- std.<iomanip>
dev_langs:
- C++
helpviewer_keywords:
- iomanip header
ms.assetid: 3681c346-4763-4037-bba4-cf0dc3447974
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 753e2a5bab18a3643456504bda2ab84df530754e
ms.contentlocale: fr-fr
ms.lasthandoff: 04/29/2017

---
# <a name="ltiomanipgt"></a>&lt;iomanip&gt;
Incluez l'en-tête standard `iostreams` `<iomanip>` pour définir plusieurs manipulateurs qui acceptent chacun un argument unique.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <iomanip>  
  
```  
  
## <a name="remarks"></a>Notes  
 Chacun de ces manipulateurs retourne un type non spécifié, appelé **T1** à **T10**, qui surcharge à la fois `basic_istream`\<**Elem**, **Tr**>`::`[operator>>](../standard-library/istream-operators.md#op_gt_gt) et `basic_ostream`\<**Elem**, **Tr**>`::`[operator<<](../standard-library/ostream-operators.md#op_lt_lt).  
  
### <a name="manipulators"></a>Manipulateurs  
  
|||  
|-|-|  
|[get_money](../standard-library/iomanip-functions.md#iomanip_get_money)|Obtient une valeur monétaire, éventuellement au format international.|  
|[get_time](../standard-library/iomanip-functions.md#iomanip_get_time)|Obtient une heure dans une structure d'heure à l'aide d'un format spécifié.|  
|[put_money](../standard-library/iomanip-functions.md#iomanip_put_money)|Fournit une valeur monétaire, éventuellement au format international.|  
|[put_time](../standard-library/iomanip-functions.md#iomanip_put_time)|Fournit une heure dans une structure d'heure et une chaîne de format à utiliser.|  
|[quoted](../standard-library/iomanip-functions.md#quoted)|Autorise un aller-retour pratique des chaînes avec des opérateurs d'insertion et d'extraction.|  
|[resetiosflags](../standard-library/iomanip-functions.md#resetiosflags)|Efface les indicateurs spécifiés.|  
|[setbase](../standard-library/iomanip-functions.md#setbase)|Définir la base pour les entiers.|  
|[setfill](../standard-library/iomanip-functions.md#setfill)|Définit le caractère qui sera utilisé pour remplir les espaces dans un affichage aligné à droite.|  
|[setiosflags](../standard-library/iomanip-functions.md#setiosflags)|Définit les indicateurs spécifiés.|  
|[setprecision](../standard-library/iomanip-functions.md#setprecision)|Définit la précision des valeurs à virgule flottante.|  
|[setw](../standard-library/iomanip-functions.md#setw)|Spécifie la largeur de la zone d'affichage.|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)




