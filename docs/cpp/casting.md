---
title: "Effectuer un cast | Microsoft Docs"
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
  - "effectuer un cast"
  - "classes (C++), polymorphisme"
  - "contrainte"
  - "opérateur de cast dynamique"
  - "classes polymorphes"
  - "opérateur de cast statique"
  - "fonctions virtuelles, dans des classes dérivées"
ms.assetid: 3dbeb06e-2f4b-4693-832d-624bc8ec95de
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Effectuer un cast
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le langage C\+\+ prévoit que si une classe est dérivée d'une classe de base contenant des fonctions virtuelles, un pointeur vers ce type de classe de base peut être utilisé pour appeler les implémentations des fonctions virtuelles résidant dans l'objet classe dérivé.  Une classe contenant des fonctions virtuelles est parfois appelée une classe polymorphe.  
  
 Étant donné qu'une classe dérivée contient les définitions de toutes les classes de base dont elle est dérivée, il est possible de convertir un pointeur qui va jusqu'en haut de la hiérarchie de classes en l'une de ces classes de base.  S'il existe un pointeur vers une classe de base, il est possible de le convertit jusqu'en bas de la hiérarchie.  Cela est possible si l'objet qui est pointé est réellement d'un type dérivé de la classe de base.  Dans ce cas, l'objet lui\-même est appelé l'objet complet. On dit que le pointeur vers la classe de base pointe vers un sous\-objet de l'objet complet.  Considérons, par exemple, la hiérarchie de classe représentée dans l'illustration ci\-dessous.  
  
 ![Hiérarchie de classes](../cpp/media/vc38zz1.png "vc38ZZ1")  
Hiérarchie de classes  
  
 Un objet de type `C` peut être visualisé comme indiqué dans l'illustration ci\-dessous.  
  
 ![Classe C avec les sous&#45;objets B et A](../cpp/media/vc38zz2.png "vc38ZZ2")  
Class C avec sous\-objet B et sous\-objet A  
  
 Avec une instance de classe `C`, il y a un sous\-objet `B` et un sous\-objet `A`.  L'instance de `C`, avec les sous\-objets `A` et `B` forme l'objet complet.  
  
 En utilisant les informations de type au moment de l'exécution, il est possible de vérifier si un pointeur pointe réellement vers un objet complet et peut être casté sans risque vers un autre objet de sa hiérarchie.  L'opérateur [dynamic\_cast](../cpp/dynamic-cast-operator.md) peut servir à créer ces types de casts.  Il exécute également le contrôle à l'exécution nécessaire pour sécuriser l'opération.  
  
 Pour la conversion des types non polymorphes, vous pouvez utiliser l'opérateur [static\_cast](../cpp/static-cast-operator.md) \(cette rubrique explique la différence entre les conversions de casting statiques et dynamiques et quand il convient de les utiliser\).  
  
 Cette section couvre les rubriques suivantes :  
  
-   [Opérateurs de casting](../cpp/casting-operators.md)  
  
-   [Informations de type au moment de l'exécution](../cpp/run-time-type-information.md)  
  
## Voir aussi  
 [Expressions](../cpp/expressions-cpp.md)