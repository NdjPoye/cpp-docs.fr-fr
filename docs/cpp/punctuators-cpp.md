---
title: "Signes de ponctuation C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - ";"
  - ","
  - "{"
  - "}"
  - "("
  - ")"
  - "["
  - "]"
  - "!"
  - "%"
  - "^"
  - "*"
  - """
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "signes de ponctuation"
ms.assetid: 1521564c-a977-488a-9490-068079897592
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Signes de ponctuation C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les signes de ponctuation en langage C\+\+ ont une signification syntaxique et sémantique pour le compilateur mais ne spécifient pas d'eux\-mêmes une opération qui produit une valeur.  Certains signes de ponctuation, seuls ou combinés, peuvent également être des opérateurs C\+\+ ou être significatifs pour le préprocesseur.  
  
 Tous les caractères suivants sont considérés comme des signes de ponctuation :  
  
```  
! % ^ & * ( ) – + = { } | ~  
[ ] \ ; ' : " < > ? , . / #  
```  
  
 Les signes de ponctuation **\[ \]**, **\( \)** et **{ }** doivent figurer par paires après la [phase de traduction](../preprocessor/phases-of-translation.md) 4.  
  
## Voir aussi  
 [Conventions lexicales](../cpp/lexical-conventions.md)