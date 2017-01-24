---
title: "2.6.4 Construction atomic | Microsoft Docs"
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
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.4 Construction atomic
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La `atomic` directive garantit qu’un emplacement mémoire spécifique est mis à jour atomiquement, plutôt que d’exposer à la possibilité de plusieurs simultanées d’écriture de threads. La syntaxe de la `atomic` directive se présente comme suit :  
  
```  
#pragma omp atomic new-lineexpression-stmt  
```  
  
 L’instruction d’expression doit avoir une des formes suivantes :  
  
 *x binop*= *expr*  
  
 x ++  
  
 ++ x  
  
 x :  
  
 x :  
  
 Dans les expressions précédentes :  
  
-   *x* est une expression lvalue avec type scalaire.  
  
-   *Expr* est une expression de type scalaire, et il ne fait pas référence à l’objet désigné par *x*.  
  
-   `binop` n’est pas un opérateur surchargé et fait partie de +, *, -, /, &, ^, &#124 ; <\<, ou >>.  
  
 Bien qu’il soit défini par l’implémentation si une implémentation remplace tous les `atomic` directives avec **critique** directives qui ont le même unique *nom*, le `atomic` permet une meilleure optimisation de la directive. Fréquence à laquelle les instructions de matériel sont disponibles qui peuvent effectuer la mise à jour atomique avec le moins de surcharge.  
  
 Uniquement la charge et le magasin de l’objet désigné par *x* sont atomique ; la version d’évaluation de *expr* n’est pas atomique. Pour éviter des conditions de concurrence, les mises à jour de l’emplacement en parallèle doivent être protégées par la `atomic` directive, sauf ceux qui sont connus pour être des conditions de concurrence.  
  
 Restrictions à le `atomic` la directive sont les suivantes :  
  
-   Toutes les références atomique à l’emplacement de stockage x dans tout le programme doit être un type compatible.  
  
## <a name="examples"></a>Exemples :  
  
```  
extern float a[], *p = a, b;  
/* Protect against races among multiple updates. */  
#pragma omp atomic  
a[index[i]] += b;  
/* Protect against races with updates through a. */  
#pragma omp atomic  
p[i] -= 1.0f;  
  
extern union {int n; float x;} u;  
/* ERROR - References through incompatible types. */  
#pragma omp atomic  
u.n++;  
#pragma omp atomic  
u.x -= 1.0f;  
```