---
title: "Op&#233;rateurs de multiplication C | Microsoft Docs"
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
  - "% (opérateur)"
  - "/ (opérateur)"
  - "/ (opérateur), opérateurs de multiplication"
  - "opérateurs arithmétiques (C++), opérateurs de multiplication"
  - "opérateur de multiplication (C++), opérateurs de multiplication"
  - "opérateurs (C), multiplication"
  - "reste (opérateur) (%)"
  - "/ (opérateur)"
ms.assetid: 495471c9-319b-4eb4-bd97-039a025fd3a9
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Op&#233;rateurs de multiplication C
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les opérateurs de multiplication exécutent la multiplication \(**\***\), la division \(**\/**\) et les opérations de reste \(`%`\).  
  
 **Syntaxe**  
  
 *multiplicative\-expression* :  
 *cast\-expression*  
  
 *multiplicative\-expression*  **\***  *cast\-expression*  
  
 *multiplicative\-expression*  **\/**  *cast\-expression*  
  
 *multiplicative\-expression*  **%**  *cast\-expression*  
  
 Les opérandes de l'opérateur de reste \(`%`\) doivent être intégraux.  Les opérateurs de multiplication \(**\***\) et de division \(**\/**\) peuvent prendre des opérandes de type entier ou virgule flottante. Les types des opérandes peuvent être différents.  
  
 Les opérateurs de multiplication exécutent les conversions arithmétiques courantes sur les opérandes.  Le type du résultat est le type des opérandes après conversion.  
  
> [!NOTE]
>  Étant donné que les conversions exécutées par les opérateurs de multiplication ne fournissent pas de conditions de dépassement de capacité positif ou de dépassement de capacité négatif, les informations peuvent être perdues si le résultat d'une opération de multiplication ne peut pas être représenté dans le type des opérandes après conversion.  
  
 Les opérateurs de multiplication C sont décrits ci\-dessous :  
  
|Opérateur|Description|  
|---------------|-----------------|  
|**\***|L'opérateur de multiplication provoque la multiplication de ces deux opérandes.|  
|**\/**|L'opérateur de division provoque la division de la première opérande par la deuxième.  Si deux opérandes entiers sont divisés et que le résultat n'est pas un entier, il est tronqué selon les règles suivantes :|  
||-   Le résultat de la division par 0 est indéfini selon la norme C ANSI.  Le compilateur Microsoft C génère une erreur au moment de la compilation ou de l'exécution.|  
||-   Si les deux opérandes sont positifs ou non signés, le résultat est tronqué vers 0.|  
||-   Si l'un des opérandes est négatif, si le résultat de l'opération est le plus grand entier inférieur ou égal au quotient algébrique ou le plus petit entier supérieur ou égal au quotient algébrique, l'implémentation est définie. \(Consultez la section spécifique à Microsoft ci\-dessous.\)|  
|`%`|Le résultat de l'opérateur de reste est le reste lorsque le premier opérande est divisé par le deuxième.  Lorsque la division est incorrecte, le résultat est déterminé par les règles suivantes :|  
||-   Si l'opérande de droite est zéro, le résultat est non défini.|  
||-   Si les deux opérandes sont positifs ou non signés, le résultat est positif.|  
||-   Si l'un des opérandes est négatif et que le résultat est incorrect, le résultat est que l'implémentation est définie. \(Consultez la section spécifique à Microsoft ci\-dessous.\)|  
  
 **Section spécifique à Microsoft**  
  
 Dans la division où l'un des opérandes est négatif, la direction de la troncation est vers 0.  
  
 Si l'une ou l'autre opération est négative dans la division avec l'opérateur de reste, le résultat a la même signature que le dividende \(le premier opérande de l'expression\).  
  
 **FIN de la section spécifique à Microsoft**  
  
## Exemples  
 Les déclarations illustrées ci\-dessous sont utilisées pour les exemples suivants :  
  
```  
int i = 10, j = 3, n;  
double x = 2.0, y;  
```  
  
 Cette instruction utilise l'opérateur de multiplication :  
  
```  
y = x * i;  
```  
  
 Dans ce cas, `x` est multiplié par `i` pour donner la valeur 20,0.  Le résultat a le type **double**.  
  
```  
n = i / j;  
```  
  
 Dans cet exemple, 10 est divisé par 3.  Le résultat est tronqué vers 0, ce qui produit la valeur entière 3.  
  
```  
n = i % j;  
```  
  
 Cette instruction assigne le reste entier `n` lorsque 10 est divisé par 3.  
  
 **Section spécifique à Microsoft**  
  
 Le signe du reste est identique au signe du dividende.  Par exemple :  
  
```  
50 % -6 = 2  
-50 % 6 = -2  
```  
  
 Dans chaque cas, `50` et `2` ont le même signe.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Opérateurs de multiplication et opérateur modulo](../cpp/multiplicative-operators-and-the-modulus-operator.md)