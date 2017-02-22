---
title: "Algorithmes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "algorithme (fonction avec modèle) (conventions de bibliothèque C++)"
  - "algorithmes (C++), C++"
  - "conventions (C++), C++ (algorithme)"
  - "bibliothèques (C++), C++ (algorithm) (conventions)"
  - "bibliothèque C++ standard, algorithmes"
ms.assetid: dec9b373-7d5c-46cc-b7d2-21a938ecd0a6
caps.latest.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Algorithmes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les algorithmes sont un élément fondamental de la Bibliothèque STL \(Standard Template Library\).  Ils ne fonctionnent pas avec des conteneurs proprement dits, mais plutôt avec des itérateurs.  Ainsi, le même algorithme peut être utilisé par la plupart des conteneurs STL \(voire tous\).  Cette section traite des conventions et de la terminologie des algorithmes STL.  
  
## Notes  
 Les descriptions des fonctions de modèle d'algorithme emploient plusieurs expressions raccourcies :  
  
-   L'expression « dans la plage \[*A*, *B*\) » signifie la séquence de zéro, une ou plusieurs valeurs discrètes commençant à *A* et allant jusqu'à *B* non compris.  Une plage est valide uniquement si *B* est accessible à partir de *A* ; vous pouvez stocker *A* dans un objet *N* \(*N* \= *A*\), incrémenter l'objet zéro, une ou plusieurs fois \(\+\+*N*\) et comparer l'égalité de l'objet à *B* après un nombre fini d'incréments \(N \=\= B*\).*  
  
-   L'expression « chaque *N* dans la plage \[*A*, *B*\) » signifie que *N* commence à la valeur *A* et est incrémenté zéro, une ou plusieurs fois jusqu'à être égal à la valeur *B*.  Le cas *N* \=\= *B* n'est pas dans la plage.  
  
-   La phrase « la valeur la plus faible de *N* dans la plage \[*A*, *B*\) telle que *X* » signifie que la condition *X* est déterminée pour chaque *N* dans la plage \[*A*, *B*\) jusqu'à ce que la condition *X* soit remplie.  
  
-   La phrase « la valeur la plus élevée de *N* dans la plage \[*A*, *B*\) telle que *X* » signifie que *X* est déterminée pour chaque *N* dans la plage \[*A*, *B*\).  La fonction stocke dans `K` une copie de *N* chaque fois que la condition *X* est remplie.  Si ce stockage se produit, la fonction remplace la valeur finale de *N*, qui est égale à *B*, par la valeur de `K`.  Pour un itérateur bidirectionnel ou à accès aléatoire, toutefois, cela peut également signifier que *N* commence à la valeur la plus élevée dans la plage et est décrémenté sur la plage jusqu'à ce que la condition *X* soit remplie.  
  
-   Des expressions telles que *X* \- *Y*, où *X* et *Y* peuvent être des itérateurs autres que des itérateurs à accès aléatoire, doivent être prises au sens mathématique.  La fonction n'évalue pas nécessairement l'opérateur**\-** si elle doit déterminer une telle valeur.  Cela vaut également pour les expressions telles que *X* \+ *N* et *X* \- *N*, où *N* est de type entier.  
  
 Plusieurs algorithmes utilisent un prédicat qui effectue une comparaison par paire, par exemple avec `operator==`, pour générer un résultat `bool`.  La fonction de prédicat `operator==`, ou tout remplacement, ne doit pas modifier l'un de ses opérandes.  Elle doit générer le même résultat `bool` chaque fois qu'elle est évaluée et doit générer le même résultat si l'opérande est remplacé par une copie de l'un ou l'autre opérande.  
  
 Plusieurs algorithmes utilisent un prédicat qui doit imposer un classement faible strict sur des paires d'éléments d'une séquence.  Pour le prédicat `pr`\(*X*, *Y*\) :  
  
-   Strict signifie que `pr`\(*X*, *X*\) a la valeur false.  
  
-   Faible signifie que *X* et *Y* ont un classement équivalent si \!`pr`\(*X*, *Y*\) && \!`pr`\(*Y*, *X*\) \(*X* \=\= *Y* ne doit pas obligatoirement être défini\).  
  
-   Classement signifie que `pr`\(*X*, *Y*\) && `pr`\(*Y*, Z\) implique `pr`\(*X*, Z\).  
  
 Certains de ces algorithmes utilisent implicitement le prédicat *X* \< *Y*.  *X* \> *Y*, **less**\(*X*, *Y*\) et `greater`\(*X*, *Y*\) sont d'autres prédicats qui répondent en général à l'impératif de classement faible strict.  Notez cependant que des prédicats tels que *X* \<\= *Y* et *X* \>\= *Y* ne répondent pas à cet impératif.  
  
 Une séquence d'éléments désignée par des itérateurs dans la plage \[`First`, `Last`\) est une séquence ordonnée par l'opérateur**\<** si, pour chaque *N* dans la plage \[0, `Last` \- `First`\) et pour chaque *M* dans la plage \(N, `Last` \- `First`\) le prédicat \!\(\*\(`First` \+ *M*\) \< \*\(*First* \+ *N*\)\) a la valeur true.  \(Notez que les éléments sont triés par ordre croissant\). La fonction de prédicat **operator\<**, ou tout remplacement, ne doit pas modifier l'un de ses opérandes.  Elle doit générer le même résultat `bool` chaque fois qu'elle est évaluée et doit générer le même résultat si l'opérande est remplacé par une copie de l'un ou l'autre opérande.  En outre, elle doit imposer un classement faible strict sur les opérandes qu'elle compare.  
  
 Une séquence d'éléments désignée par des itérateurs dans la plage \[`First`, `Last`\) est un tas ordonné par l'opérateur**\<** si, pour chaque *N* dans la plage \[1, `Last` \- `First`\) le prédicat \!\(\*`First` \< \*\(`First` \+ *N*\)\) a la valeur true.  \(Le premier élément est le plus grand.\) Sa structure interne est autrement connue uniquement des fonctions de modèle [make\_heap](../Topic/make_heap.md), [pop\_heap](../Topic/pop_heap.md) et [push\_heap](../Topic/push_heap.md).  Comme avec une séquence ordonnée, la fonction de prédicat **operator\<**, ou tout remplacement, ne doit pas modifier l'un de ses opérandes et elle doit imposer un classement faible strict sur les opérandes qu'elle compare.  Elle doit générer le même résultat `bool` chaque fois qu'elle est évaluée et doit générer le même résultat si l'opérande est remplacé par une copie de l'un ou l'autre opérande.  
  
 Les algorithmes STL se trouvent dans les fichiers d'en\-tête [\<algorithm\>](../standard-library/algorithm.md) et [\<numeric\>](../standard-library/numeric.md).  
  
## Voir aussi  
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)