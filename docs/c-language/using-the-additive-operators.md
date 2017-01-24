---
title: "Utilisation des op&#233;rateurs additifs | Microsoft Docs"
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
  - "opérateurs additifs"
  - "opérateurs (C++), addition"
ms.assetid: 7d54841e-436d-4ae8-9865-1ac1829e6f22
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Utilisation des op&#233;rateurs additifs
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les exemples suivants, qui illustrent les opérateurs d'addition et de soustraction, utilisent ces déclarations :  
  
```  
int i = 4, j;  
float x[10];  
float *px;  
```  
  
 Ces instructions sont équivalentes :  
  
```  
px = &x[4 + i];  
px = &x[4] + i;    
```  
  
 La valeur de `i` est multipliée par la longueur d'un **float** et ajoutée à `&x[4]`.  La valeur de pointeur résultante est l'adresse de `x[8]`.  
  
```  
j = &x[i] - &x[i-2];  
```  
  
 Dans cet exemple, l'adresse du troisième élément de `x` \(donné par `x[i–2]`\) est ensuite soustraite dans l'adresse du cinquième élément de `x` \(donné par `x[i]`\).  La différence est divisée par la longueur d'un **float** ; le résultat est la valeur entière 2.  
  
## Voir aussi  
 [Opérateurs additifs C](../c-language/c-additive-operators.md)