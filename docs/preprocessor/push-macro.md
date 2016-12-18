---
title: "push_macro | Microsoft Docs"
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
  - "vc-pragma.push_macro"
  - "push_macro_CPP"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "pragmas, push_macro"
  - "push_macro (pragma)"
ms.assetid: ac89efc9-afd1-4dfe-bfd1-497229b3e81d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# push_macro
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Enregistre la valeur de la macro *macro\_name* en haut de la pile correspondant à cette macro.  
  
## Syntaxe  
  
```  
  
#pragma push_macro("  
macro_name  
")  
  
```  
  
## Notes  
 Vous pouvez récupérer la valeur de *macro\_name* à l'aide de **pop\_macro**.  
  
 Consultez [pop\_macro](../preprocessor/pop-macro.md) pour obtenir un exemple.  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)