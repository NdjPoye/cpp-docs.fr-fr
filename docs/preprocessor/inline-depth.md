---
title: "inline_depth | Microsoft Docs"
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
  - "inline_depth_CPP"
  - "vc-pragma.inline_depth"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "inline_depth (pragma)"
  - "pragmas, inline_depth"
ms.assetid: 2bba60fe-43ea-4d09-90f7-aafaba3bad07
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# inline_depth
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Spécifie la profondeur de recherche heuristique inline, telle qu'aucune fonction ne sera incorporée à une profondeur \(dans le graphique des appels\) supérieure à `n`.  
  
## Syntaxe  
  
```  
  
#pragma inline_depth( [n] )  
```  
  
## Notes  
 Ce pragma contrôle l'incorporation des fonctions marquées [inline](../misc/inline-inline-forceinline.md) et [\_\_inline](../misc/inline-inline-forceinline.md) ou incorporées automatiquement sous l'option \/Ob2.  
  
 `n` peut être une valeur comprise entre 0 et 255, 255 correspondant à une profondeur illimitée dans le graphique des appels et zéro inhibant l'expansion inline.  Lorsque `n` n'est pas spécifié, la valeur par défaut \(254\) est utilisée.  
  
 Le pragma **inline\_depth** contrôle le nombre de fois qu'une série d'appels de fonction peut être développée.  Par exemple, avec une profondeur inline égale à quatre, si A appelle B et B appelle C, les trois appels sont développés inline.  Toutefois, si l'expansion inline la plus proche est deux, seuls A et B sont développés, et C demeure comme un appel de fonction.  
  
 Pour utiliser ce pragma, vous devez définir l'option \/Ob du compilateur sur 1 ou 2.  La profondeur définie à l'aide de ce pragma entre en vigueur au premier appel de fonction après le pragma.  
  
 La profondeur inline peut être réduite pendant l'expansion, mais pas augmentée.  Si la profondeur inline est égale à six et que pendant l'expansion le préprocesseur rencontre un pragma **inline\_depth** ayant pour valeur huit, la profondeur demeure égale à six.  
  
 Le pragma **inline\_depth** n'a aucun effet sur les fonctions marquées avec `__forceinline`.  
  
> [!NOTE]
>  Les fonctions récursives peuvent être substituées inline à une profondeur maximale de 16 appels.  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)   
 [inline\_recursion](../preprocessor/inline-recursion.md)