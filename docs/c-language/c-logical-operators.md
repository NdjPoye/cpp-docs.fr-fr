---
title: "Op&#233;rateurs logiques C | Microsoft Docs"
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
  - "&& (opérateur)"
  - "|| (opérateur)"
  - "opérateur logique AND"
  - "opérateurs logiques, C"
  - "opérateurs logiques, points de séquence d'expression"
  - "opérateur logique OR"
  - "opérateurs (C), logique"
  - "évaluation de court-circuit"
ms.assetid: c0a4e766-ad56-4300-bf76-b28dc0e19b43
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs logiques C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs logiques effectuent les opérations logiques AND \(**&&**\) et OR \( `||` \).  
  
 **Syntaxe**  
  
 *expression logique AND* :  
 *expression OU\-inclusif*  
  
 *expression logique ET* **&&**  *expression OU inclusif*  
  
 *expression logique ET*:  
 *Expression logique ET*  
  
 *expression logique OU*  **&#124;&#124;**  *expression logique ET*  
  
 Les opérateurs logiques n'exécutent pas les conversions arithmétiques classiques.  À la place, ils évaluent chaque opérande en termes de son équivalence à 0.  Le résultat d'une opération logique est soit 0 ou 1.  Sinon, le type du résultat est `int`.  
  
 Les opérateurs logiques C sont décrits ci\-dessous :  
  
|Opérateur|Description|  
|---------------|-----------------|  
|**&&**|L'opérateur logique ET produit la valeur 1 si les deux opérandes ont des valeurs différentes de zéro.  Si l'un des opérandes est égal à 0, le résultat est 0.  Si le premier opérande d'une opération ET est égal à 0, le second opérande n'est pas évaluée.|  
|`&#124;&#124;`|L'opérateur logique OU exécute un opération OU inclusif sur ses opérandes.  Le résultat est 0 si les deux opérandes ont pour valeurs 0.  Si l'un ou l'autre opérande a une valeur différente de zéro, le résultat est 1.  Si le premier opérande d'une opération logique OU a une valeur différente de zéro, le second opérande n'est pas évalué.|  
  
 Les opérandes des expressions logiques ET et OU sont évalués de gauche à droite.  Si la valeur du premier opérande est suffisante pour déterminer le résultat de l'opération, le second opérande n'est pas évaluée.  Cela est appelée « évaluation court\-circuitée ». Il existe un point de séquence après le premier opérande.  Consultez [Points de Séquence](../c-language/c-sequence-points.md) pour plus d'informations.  
  
## Exemples  
 L'exemple suivant illustre les opérateurs logiques :  
  
```  
int w, x, y, z;  
  
if ( x < y && y < z )  
    printf( "x is less than z\n" );  
```  
  
 Dans cet exemple, la fonction `printf` est appelée pour imprimer un message si `x` est moins que `y` et `y` est moins que `z`.  Si `x` est supérieur à `y`, le second opérande \(`y < z`\) n'est pas évalué et rien est imprimé.  Notez que cela peut provoquer des problèmes lorsque le second opérande a des effets secondaires qui sont pris en compte pour une autre raison.  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 Dans cet exemple, si `x` est égal à `w`, `y`, ou `z`, le deuxième argument à la fonction d'`printf` a pour valeur true et la valeur 1 est imprimée.  Sinon, elle a pour valeur false et la valeur 0 est imprimée.  Dès que l'une des conditions évaluera True, l'évaluation s'arrêtera.  
  
## Voir aussi  
 [Opérateur AND logique : &&](../cpp/logical-and-operator-amp-amp.md)   
 [Opérateur OR logique : &#124;&#124;](../cpp/logical-or-operator-pipe-pipe.md)