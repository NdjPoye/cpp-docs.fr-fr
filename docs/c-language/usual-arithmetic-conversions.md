---
title: "Conversions arithm&#233;tiques courantes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conversions arithmétiques (C++)"
  - "opérateurs arithmétiques (C++), conversions de types"
  - "conversions (C++), arithmétiques"
  - "conversion de type de données (C++), arithmétiques"
  - "opérateurs (C), conversions arithmétiques"
  - "conversion de type (C++), arithmétiques"
ms.assetid: bfa49803-0efd-45d0-b987-111412a140d7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Conversions arithm&#233;tiques courantes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La plupart des opérateurs C effectuent des conversions de type pour faire des opérandes d'une expression un type commun ou pour étendre les valeurs courtes à la taille d'entier utilisée dans les opérations d'ordinateur.  Les conversions exécutées par les opérateurs C dépendent de l'opérateur spécifique et du type de l'opérande ou des opérandes.  Toutefois, de nombreux opérateurs exécutent des conversions similaires sur les opérandes de types intégraux et flottants.  Ces conversions sont appelées « conversions arithmétiques ». La conversion d'une valeur d'opérande en un type compatible n'entraîne aucune modification de sa valeur.  
  
 Les conversions arithmétiques résumées ci\-dessous sont appelées « conversions arithmétiques habituelles ». La procédure ci\-dessous est appliquée uniquement pour les opérateurs binaires qui nécessitent un type arithmétique.  L'objectif est de retourner un type commun qui est également le type du résultat.  Pour déterminer quelles conversions ont effectivement lieu, le compilateur applique l'algorithme suivant aux opérations binaires dans l'expression.  Les étapes ci\-dessous ne constituent pas un ordre de priorité.  
  
1.  Si l'un des opérandes est de type `long double`, l'autre opérande est converti en type `long double`.  
  
2.  Si la condition ci\-dessus n'est pas remplie et que l'un des opérandes est de type **double**, l'autre opérande est converti en type **double**.  
  
3.  Si les deux conditions ci\-dessus ne sont pas remplies et que l'un des opérandes est de type **flottant**, l'autre opérande est converti en type **flottant**.  
  
4.  Si les trois conditions ci\-dessus ne sont pas remplies \(aucun des opérandes n'est de type flottant\), des conversions de type intégral sont exécutées sur les opérandes, comme suit :  
  
    -   Si l'un des opérandes est de type `unsigned long`, l'autre opérande est converti en type `unsigned long`.  
  
    -   Si la condition ci\-dessus n'est pas remplie et que l'un des opérandes est de type **long** et l'autre de type `unsigned int`, les deux opérandes sont convertis en type `unsigned long`.  
  
    -   Si les deux conditions ci\-dessus ne sont pas remplies et que l'un des opérandes est de type **long**, l'autre opérande est converti en type **long**.  
  
    -   Si les trois conditions ci\-dessus ne sont pas réunies et que l'un des opérandes est de type `unsigned int`, l'autre opérande est converti en type `unsigned int`.  
  
    -   Si aucune des conditions ci\-dessus n'est remplie, les deux opérandes sont convertis en type `int`.  
  
 Le code suivant illustre ces règles de conversion :  
  
```  
float   fVal;  
double  dVal;  
int   iVal;  
unsigned long ulVal;  
  
dVal = iVal * ulVal; /* iVal converted to unsigned long  
                      * Uses step 4.  
                      * Result of multiplication converted to double   
                      */  
dVal = ulVal + fVal; /* ulVal converted to float  
                      * Uses step 3.  
                      * Result of addition converted to double   
                      */   
```  
  
## Voir aussi  
 [Opérateurs C](../c-language/c-operators.md)