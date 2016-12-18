---
title: "Assignation simple (C) | Microsoft Docs"
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
  - "opérateurs d'assignation (C++), simples"
  - "conversion de type de données (C++), assignation simple"
  - "signe égal"
  - "opérateurs (C), assignation simple"
  - "opérateur d'assignation simple"
  - "conversion de type (C++), assignation simple"
ms.assetid: e7140a0a-7104-4b3a-b293-7adcc1fdd52b
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assignation simple (C)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'opérateur d'assignation simple assigne son opérande droit à son opérande gauche.  La valeur de l'opérande droit est convertie dans le type de l'expression d'assignation et remplace la valeur stockée dans l'objet désigné par l'opérande gauche.  Les règles de conversion relatives à l'assignation sont applicables \(consultez [Conversions d'assignation](../c-language/assignment-conversions.md)\).  
  
```  
double x;  
int y;  
  
x = y;  
```  
  
 Dans cet exemple, la valeur de `y` est convertie en type **double** et assignée à `x`.  
  
## Voir aussi  
 [Opérateurs d'assignation C](../c-language/c-assignment-operators.md)