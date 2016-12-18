---
title: "inline_recursion | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "inline_recursion_CPP"
  - "vc-pragma.inline_recursion"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "inline_recursion (pragma)"
  - "pragmas, inline_recursion"
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# inline_recursion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Contrôle l'expansion inline des appels de fonction directe ou mutuellement récursive.  
  
## Syntaxe  
  
```  
  
#pragma inline_recursion( [{on | off}] )  
```  
  
## Notes  
 Utilisez ce pragma pour contrôler les fonctions marquées comme [inline](../misc/inline-inline-forceinline.md) et [\_\_inline](../misc/inline-inline-forceinline.md) ou les fonctions que le compilateur développe automatiquement sous l'option \/Ob2.  L'utilisation de ce pragma requiert une définition de l'option de compilateur [\/Ob](../build/reference/ob-inline-function-expansion.md) avec la valeur 1 ou 2.  L'état par défaut pour `inline_recursion` est désactivé.  Ce pragma entre en vigueur au premier appel de fonction après sa détection et n'a aucune incidence sur la définition de la fonction.  
  
 Le pragma `inline_recursion` contrôle le développement des fonctions récursives.  Si `inline_recursion` est désactivé, et si une fonction inline s'appelle elle\-même \(directement ou indirectement\), elle est développée une seule fois.  Si `inline_recursion` est activé, la fonction est développée plusieurs fois jusqu'à ce qu'elle atteigne la valeur définie avec le pragma [inline\_depth](../preprocessor/inline-depth.md), la valeur par défaut pour les fonctions récursives qui est définie par le pragma `inline_depth`, ou une limite de capacité.  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline\_depth](../preprocessor/inline-depth.md)   
 [\/Ob \(Expansion des fonctions Inline\)](../build/reference/ob-inline-function-expansion.md)