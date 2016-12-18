---
title: "result_of, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "cpp"
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "result_of"
  - "std.result_of"
  - "std::result_of"
  - "type_traits/std::result_of"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "result_of"
ms.assetid: 5374a096-4b4a-4712-aa97-6852c5cdd6be
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# result_of, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Détermine le type de retour de type peut être appelé qui accepte les types d’arguments spécifiés.  
  
## Syntaxe  
  
```  
template <class Fn, class... ArgTypes>  
    struct result_of<Fn(ArgTypes...)>;  
```  
  
#### Paramètres  
 `Fn`  
 Le type peut être appelé à interroger.  
  
 `ArgTypes`  
 Les types de la liste d’arguments de type peut être appelé à interroger.  
  
## Notes  
 Utilisez ce modèle pour déterminer, au moment de la compilation, le type de résultat de `Fn`\(`ArgTypes`\), où `Fn` est un type peut être appelé appelé avec une liste d’arguments de types dans `ArgTypes`. Le `type` noms de membres de la classe de modèle du type de résultat de `decltype(INVOKE(declval<Fn>(), declval<ArgTypes>()...))` Si l’expression non évaluée `INVOKE(declval<Fn>(), declval<ArgTypes>()...)` est bien formé. Sinon, la classe de modèle n’a aucun membre `type`. Le type `Fn` et tous les types dans le pack de paramètre `ArgTypes` doivent être des types complets, `void`, ou les tableaux de la limite est inconnue.  
  
## Configuration requise  
 **En\-tête :** \<type\_traits\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [\<type\_traits\>](../standard-library/type-traits.md)