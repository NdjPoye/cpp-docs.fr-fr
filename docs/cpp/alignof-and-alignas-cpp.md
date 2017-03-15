---
title: "alignof et alignas (C++) | Microsoft Docs"
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
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# alignof et alignas (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le spécificateur de type `alignas` est un élément standard C\+\+ portable qui permet de spécifier un alignement personnalisé des variables et des types définis par l'utilisateur.  L'opérateur `alignof` est également un élément standard portable permettant d'obtenir l'alignement d'une variable ou d'un type spécifié.  
  
## Exemple  
 Vous pouvez utiliser `alignas` sur une classe, un struck ou une union, ou sur des membres individuels.  Quand plusieurs spécificateurs `alignas` sont utilisés, le compilateur choisit celui qui est le plus strict \(celui ayant la plus grande valeur\).  
  
```  
struct alignas(16) Bar  
{      
    int i;       // 4 bytes  
    int n;      // 4 bytes  
    alignas(4) char arr[3];  
    short s;          // 2 bytes  
};  
…  
cout << alignof(Bar) << endl; // output: 16  
  
```  
  
## Voir aussi  
 [Alignement](../cpp/alignment-cpp-declarations.md)