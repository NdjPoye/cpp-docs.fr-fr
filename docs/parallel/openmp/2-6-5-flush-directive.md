---
title: "2.6.5 flush Directive | Microsoft Docs"
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
ms.assetid: a2ec5f74-9c37-424a-8376-47ab4a5829a2
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 2.6.5 flush Directive
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La directive de **vide** , si explicite ou implicite, spécifie un point de séquence « inter\-threads » auquel l'implémentation est requise pour garantir que tous les threads dans une équipe ont un point de vue cohérent de certains objets \(spécifiés ci\-dessous\) dans la mémoire.  Cela signifie que les estimations précédentes des expressions qui référencent ces objets sont des estimations terminées et suivantes n'ont pas encore démarré.  Par exemple, les compilateurs doivent restaurer les valeurs des objets à partir de les registres à la mémoire, et le matériel peut avoir à purger les mémoires tampons d'écriture vers la mémoire et recharger les valeurs des objets de la mémoire.  
  
 La syntaxe de la directive de **vide** est la suivante :  
  
```  
#pragma omp flush [(variable-list)]  new-line  
```  
  
 Si les objets qui nécessitent la synchronisation peuvent tous être lus par des variables, ces variables peuvent être spécifiées dans *la variable\-liste*facultative.  Si un pointeur est présent dans *la variable\-liste*, le pointeur lui\-même n'est vidé, et non l'objet que le pointeur se rapporte.  
  
 Une directive de **vide** sans *variable\-liste* synchronise tous les objets partagés à l'exception de les objets inaccessibles avec la durée automatique de stockage.  \(C'est susceptible de contenir plus de charge que **vide** avec *une variable\-liste*.\) une directive de **vide** sans variable\- *liste* est implicite pour les directives suivantes :  
  
-   `barrier`  
  
-   À l'entrée et à la sortie de **critique**  
  
-   À l'entrée et à la sortie d' `ordered`  
  
-   À l'entrée et à la sortie de **parallèle**  
  
-   Dans la sortie de **pour**  
  
-   Dans la sortie de **sections**  
  
-   à la sortie d' **unique**  
  
-   À l'entrée et à la sortie de **parallèle pour**  
  
-   À l'entrée et à la sortie de **mettez en parallèle les sections**  
  
 La directive n'est pas implicite lorsqu'une clause d' `nowait` est présente.  Il faut noter que la directive de **vide** n'est pas implicite pour l'un des éléments suivants :  
  
-   à l'entrée à **pour**  
  
-   à l'entrée à ou à la sortie de **page maître**  
  
-   à l'entrée à **sections**  
  
-   à l'entrée à **unique**  
  
 Une référence qui accède à la valeur d'un objet avec un type volatil\-qualifié se comporte comme s'il y avait **vide** directive spécification de cet objet au point de séquence précédent.  Une référence qui modifie la valeur d'un objet avec un type volatil\-qualifié se comporte comme s'il y avait **vide** directive spécification de cet objet au point de séquence suivant.  
  
 Étant donné que la directive de **vide** n'a pas d'instructions de langage c dans le cadre de sa syntaxe, il existe des limites à son positionnement à l'intérieur d'un programme.  Consultez l' [annexe C](../../parallel/openmp/c-openmp-c-and-cpp-grammar.md) pour la grammaire formels.  L'exemple suivant illustre ces restrictions.  
  
```  
/* ERROR - The flush directive cannot be the immediate  
*          substatement of an if statement.  
*/  
if (x!=0)  
   #pragma omp flush (x)  
...  
  
/* OK - The flush directive is enclosed in a  
*      compound statement  
*/  
if (x!=0) {  
   #pragma omp flush (x)  
}  
```  
  
 Les restrictions à la directive de **vide** sont les suivantes :  
  
-   une variable spécifiée dans une directive de **vide** ne doit pas avoir un type référence.