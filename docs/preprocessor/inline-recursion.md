---
title: inline_recursion | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
dev_langs: C++
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d749753e7eaf81284de72314f5f940fd2790962c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="inlinerecursion"></a>inline_recursion
Contrôle l’expansion inline des appels de fonction directe ou mutuellement récursive.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
#pragma inline_recursion( [{on | off}] )  
```  
  
## <a name="remarks"></a>Notes  
 Utilisez ce pragma pour contrôler les fonctions marqué comme [inline](../cpp/inline-functions-cpp.md) et [__inline](../cpp/inline-functions-cpp.md) ou fonctions que le compilateur développe automatiquement sous l’option/Ob2. Utilisation de ce pragma requiert un [/Ob](../build/reference/ob-inline-function-expansion.md) paramètre de l’option du compilateur de 1 ou 2. L'état par défaut pour `inline_recursion` est désactivé. Ce pragma entre en vigueur au premier appel de fonction après sa détection et n'a aucune incidence sur la définition de la fonction.  
  
 Le pragma `inline_recursion` contrôle le développement des fonctions récursives. Si `inline_recursion` est désactivé, et si une fonction inline s'appelle elle-même (directement ou indirectement), elle est développée une seule fois. Si `inline_recursion` est activé, la fonction est développée plusieurs fois jusqu'à ce qu’il atteigne la valeur définie avec la [inline_depth](../preprocessor/inline-depth.md) pragma, la valeur par défaut pour les fonctions récursives qui est définie par le `inline_depth` pragma, ou une limite de capacité .  
  
## <a name="see-also"></a>Voir aussi  
 [Directives pragma et mot clé _pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline_depth](../preprocessor/inline-depth.md)   
 [/OB (Expansion des fonctions Inline)](../build/reference/ob-inline-function-expansion.md)