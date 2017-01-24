---
title: "Expressions constantes C++ | Microsoft Docs"
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
  - "expressions constantes"
  - "expressions constantes, syntaxe"
  - "expressions (C++), constante"
ms.assetid: b07245a5-4c21-4589-b503-e6ffd631996f
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Expressions constantes C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une valeur de *constante* est une valeur qui ne change pas.  C\+\+ fournit deux mots clés qui vous permettent d'exprimer l'intention qu'un objet n'est pas destiné à être modifié, et d'appliquer cette intention.  
  
 C\+\+ requiert des expressions constantes \(expressions qui ont pour valeur une constante\) pour les déclarations des éléments suivants :  
  
-   Limites d'index de tableau  
  
-   Sélecteurs dans les instructions case  
  
-   Spécification de longueur de champ de bits  
  
-   Initialiseurs d'énumération  
  
 Les seuls opérandes autorisés dans les expressions constantes sont :  
  
-   Littéraux  
  
-   Constantes d'énumération  
  
-   Valeurs déclarées comme const qui sont initialisées avec des expressions constantes  
  
-   Expressions `sizeof`  
  
 Les constantes non intégrales doivent être converties \(explicitement ou implicitement\) en types intégraux pour être autorisées dans une expression constante.  Par conséquent, le code suivant est conforme :  
  
```  
const double Size = 11.0;  
char chArray[(int)Size];  
```  
  
 Les conversions explicites en types intégraux sont autorisées dans les expressions constantes ; tous les autres types et types dérivés ne sont pas autorisés, sauf quand ils sont utilisés en tant qu'opérandes par rapport à l'opérateur `sizeof`.  
  
 L'opérateur virgule et les opérateurs d'assignation de virgule ne peuvent pas être utilisés dans les expressions constantes.  
  
## Voir aussi  
 [Types d'expressions](../cpp/types-of-expressions.md)