---
title: "Op&#233;rateurs suffix&#233;s | Microsoft Docs"
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
  - "opérateurs (C), suffixés"
  - "opérateurs suffixés"
ms.assetid: 76260011-1624-484e-8bef-72ae7ab556cc
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs suffix&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs suffixés ont la priorité la plus élevée \(la liaison la plus étroite\) dans l'évaluation de l'expression.  
  
## Syntaxe  
 *postfix\-expression* :  
 *primary\-expression*  
  
 *postfix\-expression*  **\[**  *expression*  **\]**  
  
 *postfix\-expression*  **\(**  *argument\-expression\-list*  opt **\)**  
  
 *postfix\-expression*  **.**  *identifier*  
  
 *postfix\-expression*  **–\>**  *identifier*  
  
 *postfix\-expression*  **\+\+**  
  
 *postfix\-expression*  **––**  
  
 Dans ce niveau de priorité, les opérateurs sont les indices de tableau, les appels de fonction, les membres de structure et d'union, et les opérateurs d'incrémentation et de décrémentation suffixés.  
  
## Voir aussi  
 [Opérateurs C](../c-language/c-operators.md)