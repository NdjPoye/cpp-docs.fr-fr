---
title: Commentaires (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- code comments, C++
- comments, documenting code
- comments, C++ code
- white space, C++ comments
ms.assetid: 6fcb906c-c264-4083-84bc-373800b2e514
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 482b9f2f3d9917466becff3f2c9bf9fea6f599f6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="comments-c"></a>Commentaires (C++)
Un commentaire est le texte que le compilateur ignore, mais qui est utile pour les programmeurs. Commentaires sont normalement utilisés pour annoter le code pour référence ultérieure. Le compilateur les traite comme un espace blanc. Vous pouvez utiliser des commentaires dans le test pour rendre certaines lignes de code inactif ; Toutefois, `#if` / `#endif` fonctionnent mieux les directives de préprocesseur pour cela, car vous pouvez entourer le code qui contient des commentaires, mais vous ne pouvez pas imbriquer les commentaires.  
  
 Un commentaire de C++ est écrit dans une des manières suivantes :  
  
-   Le `/*` (barre oblique, l’astérisque) caractères, suivi d’une séquence de caractères (y compris les nouvelles lignes), suivie par le `*/` caractères. Cette syntaxe est identique à ANSI C.  
  
-   Le `//` caractères (deux barres obliques), suivies de n’importe quelle séquence de caractères. Une nouvelle ligne non précédée d’une barre oblique inverse met fin à cette forme de commentaire. Par conséquent, il est généralement appelé un « commentaire de ligne simple ».  
  
 Les caractères de commentaire (`/*`, `*/`, et `//`) n’ont aucune signification particulière dans une constante caractère littéral de chaîne ou de commentaire. Commentaires à l’aide de la première syntaxe, par conséquent, ne peut pas être imbriquées.  
  
## <a name="see-also"></a>Voir aussi  
 [Conventions lexicales](../cpp/lexical-conventions.md)