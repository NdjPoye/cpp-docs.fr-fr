---
title: "auto_inline | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "auto_inline_CPP"
  - "vc-pragma.auto_inline"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "auto_inline (pragma)"
  - "pragmas, auto_inline"
ms.assetid: f7624cd1-be76-429a-881c-65c9040acf43
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# auto_inline
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fait en sorte que toute fonction définie dans la plage où **off** est spécifié ne soit pas considérée comme candidat pour l'expansion inline automatique.  
  
## Syntaxe  
  
```  
  
#pragma auto_inline( [{on | off}] )  
```  
  
## Notes  
 Pour utiliser le pragma **auto\_inline**, placez\-le avant et juste après une définition de fonction \(et non à l'intérieur\).  Le pragma est appliqué à la première définition de fonction après détection du pragma.  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)