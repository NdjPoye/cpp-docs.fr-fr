---
title: "S&#233;mantique des expressions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "évaluation d'expression"
  - "évaluation d'expression, à propos de l'évaluation d'expression"
  - "expressions (C++), sémantique"
  - "grammaire, expressions"
ms.assetid: 4a792154-533b-48b9-8709-31bfc170f0a7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# S&#233;mantique des expressions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les expressions sont évaluées selon la priorité et le regroupement de leurs opérateurs.  \([Priorité des opérateurs C\+\+ et associativité](../cpp/cpp-built-in-operators-precedence-and-associativity.md) dans [Conventions lexicales](../cpp/lexical-conventions.md) indique les relations que les opérateurs C\+\+ appliquent aux expressions.\)  
  
## Ordre d'évaluation  
 Considérez cet exemple :  
  
```  
// expre_pluslang__pluslang_Order_of_Evaluation.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
int main()  
{  
    int a = 2, b = 4, c = 9;  
  
    cout << a + b * c << "\n";  
    cout << a + (b * c) << "\n";  
    cout << (a + b) * c << "\n";  
}  
//Output:  
38  
38  
54  
```  
  
 ![Ordre d'évaluation dans une expression](../cpp/media/vc38zv1.png "vc38ZV1")  
Ordre Expression\-Évaluation  
  
 L'ordre dans lequel l'expression affichée dans l'illustration ci\-dessus est évaluée est déterminé par la priorité et l'associativité des opérateurs :  
  
1.  La multiplication \(\*\) a la priorité la plus élevée dans cette expression. Donc, la sous\-expression `b * c` est évaluée en premier.  
  
2.  L'ajout \(\+\) a la priorité la plus élevée suivante, donc `a` est ajouté au produit de `b` et `c`.  
  
3.  Le décalage vers la gauche \(\<\<\) a la plus faible priorité dans l'expression mais il existe deux occurrences.  Étant donné que l'opérateur de décalage vers la gauche groupe de gauche à droite, la sous\-expression gauche est évaluée en premier avant la sous\-expression droite.  
  
 Lorsque les parenthèses sont utilisées pour grouper les sous\-expressions, elles modifient la priorité et également l'ordre dans lequel l'expression est évaluée, comme indiqué dans l'illustration suivante.  
  
 ![Ordre d'évaluation d'une expression avec parenthèses](../cpp/media/vc38zv2.png "vc38ZV2")  
Ordre Expression\-Évaluation avec parenthèses  
  
 Les expressions telles qu'elles existent dans l'illustration ci\-dessus sont purement évaluées pour leurs effets secondaires, dans ce cas pour transférer des informations au périphérique de sortie standard.  
  
## Notation dans les expressions  
 Le langage C\+\+ spécifie certaines compatibilités lors de la spécification des opérandes.  Le tableau ci\-dessous indique les types d'opérandes acceptables pour les opérateurs qui nécessitent des opérandes de type `type`.  
  
### Types d'opérande acceptables pour les opérateurs  
  
|Type attendu|Types autorisés|  
|------------------|---------------------|  
|`type`|**const** *type*<br /><br /> `volatile` *type*<br /><br /> `type`&<br /><br /> **const** `type`&<br /><br /> `volatile` `type`&<br /><br /> **volatile const** *type*<br /><br /> **volatile const** `type`&|  
|*type\**|`type`\* **const**`type`\* `volatile``type`\* **volatile const**|  
|**const** `type`|`type` **const** `type`**const** `type`&|  
|`volatile` `type`|`type` `volatile` `type``volatile` `type`&|  
  
 Comme les règles précédentes peuvent toujours être utilisées de manière combinée, un pointeur const vers un objet volatile peut être fourni là où un pointeur est attendu.  
  
## Expressions ambiguës  
 La signification de certaines expressions est ambiguë.  Ces expressions se rencontrent généralement lorsque la valeur d'un objet change plusieurs fois dans la même expression.  Elles reposent sur un ordre particulier d'évaluation lorsque le langage n'en définit aucun.  Prenons l'exemple suivant :  
  
```  
int i = 7;  
  
func( i, ++i );  
```  
  
 Le langage C\+\+ ne garantit pas l'ordre dans lequel les arguments d'un appel de fonction sont évalués.  Par conséquent, dans l'exemple précédent, `func` peut recevoir comme paramètres les valeurs 7 et 8, ou 8 et 8, selon que les paramètres sont évalués de gauche à droite ou de droite à gauche.  
  
## Points de séquence C\+\+ \(section spécifique à Microsoft\)  
 Une expression peut modifier la valeur d'un objet une seule fois entre des points de séquence consécutifs.  
  
 La définition de langage C\+\+ ne spécifie pas actuellement les points de séquence.  Microsoft C\+\+ utilise les mêmes points de séquence que C ANSI pour toute expression utilisant des opérateurs C et n'impliquent pas les opérateurs surchargés.  Lorsque des opérateurs sont surchargés, la sémantique passe de la séquence par l'opérateur à la séquence par l'appel de fonction.  Microsoft C\+\+ utilise les points de séquence ci\-dessous.  
  
-   Opérande de gauche de l'opérateur AND logique \(&&\).  L'opérande gauche de l'opérateur AND logique est complètement évalué et tous les effets secondaires sont terminés avant de continuer.  Il n'existe aucune garantie que l'opérande droite de l'opérateur AND logique sera évalué.  
  
-   Opérande de gauche de l'opérateur OR logique \(&#124;&#124;\).  L'opérande gauche de l'opérateur OR logique est complètement évalué et tous les effets secondaires sont terminés avant de continuer.  Il n'existe aucune garantie que l'opérande droite de l'opérateur OR logique sera évalué.  
  
-   Opérande gauche de l'opérateur virgule.  L'opérande gauche de l'opérateur virgule est complètement évalué et tous les effets secondaires sont terminés avant de continuer.  Les deux opérandes de l'opérateur virgule sont toujours évalués.  
  
-   Opérateur d'appel de fonction.  L'expression appel\-fonction et tous les arguments d'une fonction, notamment les arguments par défaut, sont évalués et tous les effets secondaires sont terminés avant l'entrée dans la fonction.  Il n'y a aucun ordre spécifié d'évaluation entre les arguments ou l'expression appel\-fonction.  
  
-   Premier opérande de l'opérateur conditionnel.  Le premier opérande de l'opérateur conditionnel est complètement évalué et tous les effets secondaires sont terminés avant de continuer.  
  
-   La fin d'une expression complète d'initialisation, comme la fin d'une initialisation dans une instruction de déclaration.  
  
-   L'expression dans une instruction d'expression.  Les instructions Expression sont composées d'une expression facultative suivie d'un point\-virgule \(;\).  L'expression est complètement évaluée pour ses effets secondaires.  
  
-   L'expression de contrôle d'une instruction de sélection \(if ou switch\).  L'expression est complètement évaluée et tous les effets secondaires sont terminés avant que le code dépendant de la sélection soit exécuté.  
  
-   Expression de contrôle d'une instruction while ou do.  L'expression est complètement évaluée et tous les effets secondaires sont terminés avant que toutes les instructions de l'itération suivante de la boucle while ne soient exécutées.  
  
-   Chacune des trois expressions d'une instruction for.  Chaque expression est complètement évaluée et tous les effets secondaires sont terminés avant de passer à l'expression suivante.  
  
-   Expression dans une instruction return.  L'expression est complètement évaluée et tous les effets secondaires sont terminés avant que le contrôle ne retourne à la fonction appelante.  
  
## Voir aussi  
 [Expressions](../cpp/expressions-cpp.md)