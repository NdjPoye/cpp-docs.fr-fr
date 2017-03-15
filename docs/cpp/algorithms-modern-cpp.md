---
title: "Algorithmes (Modern C++) | Microsoft Docs"
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
ms.assetid: 6f758d3c-a7c7-4a50-92bb-97b2f6d4ab27
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Algorithmes (Modern C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour la programmation C\+\+ moderne, nous vous recommandons d'utiliser les algorithmes de la [bibliothèque de modèles standard](../standard-library/cpp-standard-library-reference.md) \(STL\).  En voici quelques exemples importants :  
  
-   `for_each`, qui est l'algorithme de traversée par défaut. \(Également `transform` pour les éléments sémantiques qui ne sont pas à leur place.\)  
  
-   `find_if`, qui est l'algorithme de recherche par défaut.  
  
-   `sort`, `lower_bound` et les autres algorithmes de tri et de recherche par défaut.  
  
 Pour écrire un comparateur, utilisez `<` strict et utilisez des *expressions lambda nommés* lorsque vous le pouvez.  
  
```cpp  
  
auto comp = [](const widget& w1, const widget& w2)  
      { return w1.weight() < w2.weight(); }  
  
sort( v.begin(), v.end(), comp );  
  
auto i = lower_bound( v.begin(), v.end(), comp );  
  
```  
  
## Boucles  
 Si possible, utilisez des appels d'algorithme ou des boucles `for` basés sur une plage , ou les deux, au lieu de boucles écrites à la main.  `copy`, `transform`, `count_if`, `remove_if` et d'autres du même type sont préférables aux boucles manuscrites car leur intention est évident et ils facilitent l'écriture de code exempt d'erreurs.  En outre, plusieurs algorithmes STL ont des optimisations d'implémentation qui les rendent plus efficaces.  
  
 Au lieu de l'ancien C\+\+ suivant :  
  
```cpp  
  
for( auto i = strings.begin(); i != strings.end(); ++i ) {  
  :::  
  :::  
}  
  
auto i = v.begin();  
  
for( ; i != v.end(); ++i ) {  
  if (*i > x && *i < y) break;  
}  
  
```  
  
 Utilisez le C\+\+ moderne comme suit :  
  
```cpp  
  
for_each( begin(strings), end(strings), [](string& s) {  
  :::  
  :::  
} );  
auto i = find_if( begin(v), end(v),  [=](int i) { return i > x && i < y; }  );  
  
```  
  
### basée sur une plage pour les boucles  
 La boucle basée sur une plage `for` est une fonctionnalité de langage C\/C\+\+ \+\+11, pas un algorithme STL.  Mais il mérite d'être mentionné dans cette discussion sur les boucles.  Les boucles `for` basées sur une plage sont une extension du mot clé `for` et fournissent un moyen pratique et efficace d'écrire des boucles qui itèrent au sein d'une plage de valeurs.  Les conteneurs, chaînes et tableaux STL sont prêts à l'emploi pour les boucles `for` basées sur une plage.  Pour activer cette nouvelle syntaxe d'itération pour votre type défini par l'utilisateur, ajoutez la prise en charge suivante :  
  
-   Une méthode `begin` qui retourne un itérateur au début de la structure et une méthode `end` qui retourne un itérateur à la fin de la structure.  
  
-   Prise en charge dans l'itérateur des méthodes suivantes : `operator*`, `operator!=` et `operator++` \(version préfixée\).  
  
 Ces méthodes peuvent être des membres ou des fonctions autonomes.  
  
## Nombres aléatoires  
 Nul n'ignore que l'ancienne fonction CRT `rand()` présente de nombreux défauts, qui ont été abordés en détail dans la communauté C\+\+.  En C\+\+ moderne, vous n'avez pas besoin de gérer ces problèmes, ni d'inventer votre propre générateur de nombres aléatoires distribués de manière uniforme, car les outils permettant de les créer rapidement et facilement sont disponibles dans la bibliothèque STL, comme indiqué dans [\<random\>](../standard-library/random.md).  
  
## Voir aussi  
 [Bienvenue dans C\+\+](../cpp/welcome-back-to-cpp-modern-cpp.md)   
 [Référence du langage C\+\+](../cpp/cpp-language-reference.md)   
 [Bibliothèque standard C\+\+](../standard-library/cpp-standard-library-reference.md)