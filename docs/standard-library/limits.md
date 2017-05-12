---
title: '&lt;limits&gt; | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- std.<limits>
- std::<limits>
- limits/std::<limits>
- <limits>
dev_langs:
- C++
helpviewer_keywords:
- limits header
ms.assetid: e07d6379-5b00-4a3d-a789-40d41538b59e
caps.latest.revision: 18
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
ms.sourcegitcommit: 86978cd4549f0672dac7cad0e4713380ea189c27
ms.openlocfilehash: bd4d0e1dbc7b350cd0683fdd5e6ad3fc1dc1f781
ms.contentlocale: fr-fr
ms.lasthandoff: 04/18/2017

---
# <a name="ltlimitsgt"></a>&lt;limits&gt;
Définit la classe de modèle `numeric_limits` et deux énumérations concernant les représentations et l'arrondi des valeurs à virgule flottante.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#include <limits>  
  
```  
  
## <a name="remarks"></a>Remarques  
 Les spécialisations explicites de la classe `numeric_limits` décrivent de nombreuses propriétés des types fondamentaux, y compris les types à virgule flottante, caractère, entier et `bool` qui sont définis par l'implémentation plutôt que fixés par les règles du langage C++. Les propriétés décrites dans \<limits> incluent la précision, les représentations de taille minimale et maximale, l’arrondi et le signalement des erreurs de type.  
  
### <a name="enumerations"></a>Énumérations  
  
|||  
|-|-|  
|[float_denorm_style](../standard-library/limits-enums.md#float_denorm_style)|L'énumération décrit les différentes méthodes qu'une implémentation peut choisir pour représenter une valeur à virgule flottante dénormalisée (trop petite pour être représentée comme valeur normalisée) :|  
|[float_round_style](../standard-library/limits-enums.md#float_round_style)|L'énumération décrit les différentes méthodes qu'une implémentation peut choisir pour arrondir une valeur à virgule flottante en une valeur entière.|  
  
### <a name="classes"></a>Classes  
  
|||  
|-|-|  
|[numeric_limits, classe](../standard-library/numeric-limits-class.md)|La classe de modèle décrit les propriétés arithmétiques des types numériques intégrés.|  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C++](../standard-library/thread-safety-in-the-cpp-standard-library.md)




