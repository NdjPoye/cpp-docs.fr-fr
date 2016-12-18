---
title: "Op&#233;rateurs suffix&#233;s d&#39;incr&#233;mentation et de d&#233;cr&#233;mentation C | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "opérateur d'incrémentation, syntaxe"
  - "opérateurs scalaires"
  - "types (C), scalaires"
ms.assetid: 56ba218d-65f9-405f-8684-caccc0ca33aa
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs suffix&#233;s d&#39;incr&#233;mentation et de d&#233;cr&#233;mentation C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérandes des opérateurs d'incrémentation et de décrémentation sont des types scalaires qui sont des valeurs lvalue modifiables.  
  
## Syntaxe  
 *postfix\-expression* :  
 *postfix\-expression*  **\+\+**  
  
 *postfix\-expression*  **––**  
  
 Le résultat de l'opération d'incrémentation ou de décrémentation suffixée est la valeur de l'opérande.  Une fois le résultat obtenu, la valeur de l'opérande est incrémentée \(ou décrémentée\).  Le code suivant illustre l'opérateur d'incrémentation suffixée.  
  
```  
if( var++ > 0 )  
    *p++ = *q++;  
```  
  
 Dans cet exemple, la variable `var` est comparée à 0, puis incrémentée.  Si `var` avait une valeur positive avant d'être incrémentée, l'instruction suivante est exécutée.  D'abord, la valeur de l'objet pointé par `q`est assignée à l'objet pointé par `p`.  Ensuite, `q` et `p` sont incrémentés.  
  
## Voir aussi  
 [Opérateurs suffixés d'incrémentation et de décrémentation : \+\+ et \-\-](../cpp/postfix-increment-and-decrement-operators-increment-and-decrement.md)