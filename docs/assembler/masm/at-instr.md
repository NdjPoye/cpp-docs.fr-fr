---
title: "@InStr | Microsoft Docs"
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
  - "@InStr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "@InStr symbol"
ms.assetid: 980d5b9f-2b88-4306-8955-df6cd2133e68
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# @InStr
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fonction macro qui recherche la première occurrence *de string2* dans *string1*, *à partir de la position* dans *string1*.  si la *position* n'apparaît pas, la recherche commence au début de *string1*.  Retourne un entier ou un 0 de position si *string2* est introuvable.  
  
## Syntaxe  
  
```  
  
@InStr( [[position]], string1, string2 )  
```  
  
## Voir aussi  
 [Symbols Reference](../../assembler/masm/symbols-reference.md)