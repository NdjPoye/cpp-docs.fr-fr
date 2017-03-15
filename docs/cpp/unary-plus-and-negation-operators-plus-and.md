---
title: "Op&#233;rateurs plus et de n&#233;gation unaires&#160;: +&#160;et&#160;- | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "+"
  - "-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "- (opérateur)"
  - "+ (opérateur)"
  - "+ (opérateur), opérateurs unaires"
  - "négation (opérateur)"
  - "opérateurs unaires, plus"
ms.assetid: 2c58c4f4-0d92-4ae3-9d0c-1a6157875cc1
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs plus et de n&#233;gation unaires&#160;: +&#160;et&#160;-
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
  
+ cast-expression  
```  
  
```  
  
- cast-expression  
  
```  
  
## \+ \(opérateur\)  
 Le résultat de l'opérateur plus unaire \(**\+**\) est la valeur de son opérande.  L'opérande de l'opérateur plus unaire doit être d'un type arithmétique.  
  
 La promotion d'un intégral est exécutée sur des opérandes intégraux.  Le type résultant est le type vers lequel l'opérande est promu.  Ainsi, l'expression `+ch`, où `ch` est de type `char`, produit un résultat de type `int` ; la valeur est inchangée.  Pour plus d'informations sur la réalisation de la promotion, consultez [Promotions intégrales](../misc/integral-promotions.md).  
  
## \- \(opérateur\)  
 L'opérateur de négation unaire \(**–**\) produit la valeur négative de son opérande.  L'opérande de l'opérateur de négation unaire doit être un type arithmétique.  
  
 La promotion intégrale est exécutée sur les opérandes intégraux et le type résultant est le type vers lequel l'opérande est promu.  Consultez [Promotions intégrales](../misc/integral-promotions.md) pour plus d'informations sur l'exécution de la promotion.  
  
## Section spécifique à Microsoft  
 La négation unaire des quantités non signées est exécutée en soustrayant la valeur de l'opérande de 2^n, n correspondant au nombre de bits dans un objet du type non signé donné.  \(Microsoft C\+\+ s'exécute sur les processeurs qui utilisent l'arithmétique de type complément à deux.  Sur les autres processeurs, l'algorithme pour la négation peut être différent.\)  
  
## Voir aussi  
 [Expressions avec opérateurs unaires](../cpp/expressions-with-unary-operators.md)   
 [Opérateurs C\+\+](../misc/cpp-operators.md)   
 [Opérateurs, priorité et associativité C\+\+](../cpp/cpp-built-in-operators-precedence-and-associativity.md)