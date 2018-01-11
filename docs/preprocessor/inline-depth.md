---
title: inline_depth | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- inline_depth_CPP
- vc-pragma.inline_depth
dev_langs: C++
helpviewer_keywords:
- pragmas, inline_depth
- inline_depth pragma
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f105512910658603139105ecf1cf1d5b7030ad00
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="inlinedepth"></a>inline_depth
Spécifie la profondeur de recherche heuristique inline, telle qu'aucune fonction ne sera incorporée à une profondeur (dans le graphique des appels) supérieure à `n`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
#pragma inline_depth( [n] )  
```  
  
## <a name="remarks"></a>Notes  
 Ce pragma contrôle l’incorporation des fonctions marquées [inline](../cpp/inline-functions-cpp.md) et [__inline](../cpp/inline-functions-cpp.md) ou incorporées automatiquement sous l’option/Ob2.  
  
 `n` peut être une valeur comprise entre 0 et 255, 255 correspondant à une profondeur illimitée dans le graphique des appels et zéro inhibant l'expansion inline.  Lorsque `n` n'est pas spécifié, la valeur par défaut (254) est utilisée.  
  
 Le **inline_depth** pragma contrôle le nombre de fois qu’une série d’appels de fonction peut être développée. Par exemple, avec une profondeur inline égale à quatre, si A appelle B et B appelle C, les trois appels sont développés inline. Toutefois, si l'expansion inline la plus proche est deux, seuls A et B sont développés, et C demeure comme un appel de fonction.  
  
 Pour utiliser ce pragma, vous devez définir l'option /Ob du compilateur sur 1 ou 2. La profondeur définie à l'aide de ce pragma entre en vigueur au premier appel de fonction après le pragma.  
  
 La profondeur inline peut être réduite pendant l'expansion, mais pas augmentée. Si la profondeur inline est égale à six et pendant l’expansion le préprocesseur rencontre un **inline_depth** pragma avec une valeur de huit, la profondeur demeure égale à six.  
  
 Le **inline_depth** pragma n’a aucun effet sur les fonctions marquées avec `__forceinline`.  
  
> [!NOTE]
>  Les fonctions récursives peuvent être substituées inline à une profondeur maximale de 16 appels.  
  
## <a name="see-also"></a>Voir aussi  
 [Directives pragma et mot clé _pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_recursion](../preprocessor/inline-recursion.md)