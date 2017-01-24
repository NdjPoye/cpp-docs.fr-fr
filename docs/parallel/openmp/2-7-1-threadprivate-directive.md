---
title: "2.7.1 threadprivate Directive | Microsoft Docs"
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
ms.assetid: 08e0b70f-5359-4607-b0ca-38c2d570d7b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.7.1 threadprivate Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive d' `threadprivate` fait la portée du fichier nommée, la portée de l'espace de noms, ou les variables statiques de portée de bloc spécifiées dans *la variable\-liste* privée à un thread.  *la variable\-liste* est une liste avec la virgule comme séparateur des variables qui n'ont pas de type incomplet.  La syntaxe de la directive d' `threadprivate` est la suivante :  
  
```  
#pragma omp threadprivate(variable-list) new-line  
```  
  
 Chaque copie d'une variable d' `threadprivate` est initialisée une fois, à un point non spécifié dans le programme avant la première référence à cette copie, et de la façon habituelle. \(c. \- à\-d., car la copie principale est initialisée dans une série exécution du programme\).  Notez que si un objet est référencé dans un initialiseur explicite d'une variable d' `threadprivate` , et la valeur de l'objet est modifiée avant la première référence à une copie de la variable, le comportement est pas spécifié.  
  
 Comme avec aucune variable privée, un thread ne doit pas nécessairement référencer la copie d'un autre thread d'un objet d' `threadprivate` .  Pendant les régions séries et les principales parties du programme, les références seront à la principale copie du thread de l'objet.  
  
 Après que la première zone parallèle exécute, les données des objets d' `threadprivate` est garantie rendre uniquement si le mécanisme de thread dynamique a été désactivé et si le nombre de threads restent inchangées pour toutes les régions parallèles.  
  
 Les restrictions à la directive d' `threadprivate` sont les suivantes :  
  
-   Une directive d' `threadprivate` pour les variables de portée du fichier ou de la portée de l'espace de noms doit apparaître à l'extérieur de toute définition ou déclaration, et doit lexicale précéder toutes les références aux variables l'appropriées dans sa liste.  
  
-   Chaque variable dans *la variable\-liste* d'une directive d' `threadprivate` au fichier ou dans la portée de l'espace de noms doit faire référence à une déclaration de variable au fichier ou dans la portée de l'espace de noms qui précèdent lexicale la directive.  
  
-   Une directive d' `threadprivate` pour les variables statiques de portée de bloc doit apparaître dans la portée de la variable et non dans une portée imbriquée.  La directive doit lexicale précéder toutes les références aux variables l'appropriées dans sa liste.  
  
-   Chaque variable dans *la variable\-liste* d'une directive d' `threadprivate` dans la portée de bloc doit faire référence à une déclaration de variable dans la même portée qui précède lexicale la directive.  La déclaration de variable doit utiliser le spécificateur statique de classe de stockage.  
  
-   Si une variable est spécifiée dans une directive d' `threadprivate` dans une unité de traduction, elle doit être spécifiée dans une directive d' `threadprivate` dans chaque unité de traduction dans laquelle il est déclaré.  
  
-   Une variable d' `threadprivate` ne doit pas apparaître dans une clause sauf `copyin`, `copyprivate`, `schedule`, `num_threads`, ou la clause d' **if** .  
  
-   l'adresse d'une variable d' `threadprivate` n'est pas une adresse de base.  
  
-   Une variable d' `threadprivate` ne doit pas avoir un type incomplet ou un type référence.  
  
-   Une variable d' `threadprivate` avec le type de classe de non\-COSSE doit avoir un constructeur de copie accessible et pas ambigu si elle est déclarée avec un initialiseur explicite.  
  
 L'exemple suivant montre comment modifier une variable qui s'affiche dans un initialiseur peut provoquer un comportement non spécifié, et également comment éviter ce problème à l'aide d'un objet auxiliaire et d'un constructeur de copie.  
  
```  
int x = 1;  
T a(x);  
const T b_aux(x); /* Capture value of x = 1 */  
T b(b_aux);  
#pragma omp threadprivate(a, b)  
  
void f(int n) {  
   x++;  
   #pragma omp parallel for  
   /* In each thread:  
   * Object a is constructed from x (with value 1 or 2?)  
   * Object b is copy-constructed from b_aux  
   */  
   for (int i=0; i<n; i++) {  
      g(a, b); /* Value of a is unspecified. */  
   }  
}  
```  
  
## Références croisées :  
  
-   Les threads dynamiques, consultez [section 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) à la page 39.  
  
-   la variable d'environnement`OMP_DYNAMIC` , consultez [section 4,3](../../parallel/openmp/4-3-omp-dynamic.md) à la page 49.