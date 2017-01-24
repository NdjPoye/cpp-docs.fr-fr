---
title: "Stockage des unions | Microsoft Docs"
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
  - "stockage, union"
  - "union (mot clé) (C)"
  - "union (mot clé) (C), stockage"
ms.assetid: b33d246a-8d20-41c4-89b2-ab05f1428792
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Stockage des unions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le stockage associé à une variable d'union est le stockage requis pour le plus grand membre de l'union.  Lorsqu'un membre plus petit est stocké, la variable d'union peut contenir l'espace mémoire non utilisé.  Tous les membres sont stockés dans le même espace mémoire et démarrent à la même adresse.  La valeur stockée est remplacée chaque fois qu'une valeur est assignée à un autre membre.  Par exemple :  
  
```  
union         /* Defines a union named x */  
{  
    char *a, b;  
    float f[20];  
} x;  
```  
  
 Les membres de l'union `x` sont, dans l'ordre de leur déclaration, un pointeur vers une valeur `char`, une valeur `char` et un tableau de valeurs **float**.  Le stockage alloué pour `x` est le stockage requis pour le tableau `f`de 20 éléments, car `f` est le membre le plus long de l'union.  Étant donné qu'aucune balise n'est associée à l'union, son type est sans nom ou « anonyme ».  
  
## Voir aussi  
 [Déclarations d'union](../c-language/union-declarations.md)