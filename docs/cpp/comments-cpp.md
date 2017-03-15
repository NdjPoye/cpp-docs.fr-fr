---
title: "Commentaires en C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "commentaires de code, C++"
  - "commentaires, code C++"
  - "commentaires, documenter le code"
  - "espace blanc, Commentaires en C++"
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Commentaires en C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un commentaire est un texte que le compilateur ignore mais qui est utile pour les programmeurs.  Les commentaires sont normalement utilisés pour annoter le code pour vous y référer ultérieurement.  Le compilateur les traite comme un espace blanc.  Vous pouvez utiliser des commentaires dans le test pour fournir des lignes de code inactives ; Toutefois les directives de préprocesseur `#if`\/`#endif` fonctionneront mieux pour ce test car vous pouvez comprendre code contenant des commentaires mais vous ne pouvez pas imbriquer des commentaires.  
  
 Le commentaire C\+\+ est écrit d'une des façons suivantes :  
  
-   Les caractères `/*` \(barre oblique, astérisque\), suivis d'une séquence de caractères \(lignes\), suivie des caractères `*/`.  La syntaxe est la même que pour ANSI C.  
  
-   Les caractères `//` \(deux barres obliques\), suivis d'une séquence de caractères.  Une nouvelle ligne non immédiatement précédée d'une barre oblique inverse termine cette forme de commentaire.  Par conséquent, il est généralement appelé « commentaire sur une ligne ».  
  
 Les caractères de commentaire \(`/*`, `*/`, et `//`\) n'ont aucune signification particulière dans une constante caractère, un littéral de chaîne, ou un commentaire.  Les commentaires utilisant la première syntaxe ne peuvent pas, par conséquent, être imbriqués.  
  
## Voir aussi  
 [Conventions lexicales](../cpp/lexical-conventions.md)