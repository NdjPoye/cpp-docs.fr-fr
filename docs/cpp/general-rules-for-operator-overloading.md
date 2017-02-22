---
title: "R&#232;gles g&#233;n&#233;rales de surcharge d&#39;op&#233;rateur | Microsoft Docs"
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
  - "surcharge d'opérateur, règles"
ms.assetid: eb2b3754-35f7-4832-b1da-c502893dc0c7
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# R&#232;gles g&#233;n&#233;rales de surcharge d&#39;op&#233;rateur
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les règles suivantes limitent le mode d'implémentation des opérateurs surchargés.  Toutefois, ils ne s'appliquent pas aux opérateurs [new](../cpp/new-operator-cpp.md) et [delete](../cpp/delete-operator-cpp.md), qui bénéficient d'un traitement distinct.  
  
-   Vous ne pouvez pas définir de nouveaux opérateurs tels que \*\*.  
  
-   Vous ne pouvez pas redéfinir la signification d'opérateurs lorsqu'ils sont appliqués à des types de données intégrés.  
  
-   Les opérateurs surchargés doivent être soit une fonction de membre de classe non statique, soit une fonction globale.  Une fonction globale qui nécessite un accès à des membres de classe privés ou protégés doit être déclarée comme amie de cette classe.  Une fonction globale doit prendre au moins un argument qui est de type classe ou énuméré ou qui est une référence à un type énuméré ou classe.  Par exemple :  
  
    ```  
    // rules_for_operator_overloading.cpp  
    class Point  
    {  
    public:  
        Point operator<( Point & );  // Declare a member operator   
                                     //  overload.  
        // Declare addition operators.  
        friend Point operator+( Point&, int );  
        friend Point operator+( int, Point& );  
    };  
  
    int main()  
    {  
    }  
    ```  
  
     L'exemple de code précédent déclare l'opérateur Inférieur à comme fonction membre ; toutefois, les opérateurs d'addition sont déclarés comme fonctions globales qui ont un accès ami.  Notez que plusieurs implémentations peuvent être fournies pour un opérateur donné.  Dans le cas de l'opérateur d'addition précédent, les deux implémentations sont fournies pour faciliter la commutativité.  Il est tout aussi probable que des opérateurs qui ajoutent un `Point` à un `Point`, `int` à un `Point`, et ainsi de suite, soient implémentés.  
  
-   Les opérateurs obéissent aux règles de priorité, de regroupement et de nombre d'opérandes dictées par leur utilisation classique avec les types intégrés.  Par conséquent, il est impossible d'exprimer le concept « additionner 2 et 3 à un objet de type `Point` » et de s'attendre à ce que 2 soit ajouté à la coordonnée *x* et 3 à la coordonnée *y*.  
  
-   Les opérateurs unaires déclarés comme fonctions membres n'acceptent pas d'argument ; s'ils sont déclarés comme fonctions globales, ils en prennent un.  
  
-   Les opérateurs binaires déclarés comme fonctions membres acceptent un argument ; s'ils sont déclarés comme fonctions globales, ils en prennent deux.  
  
-   Si un opérateur peut être utilisé comme un opérateur unaire ou binaire \(**&**, **\***, **\+** et **\-**\), vous pouvez surcharger chaque utilisation séparément.  
  
-   Les opérateurs surchargés ne peuvent pas avoir d'arguments par défaut.  
  
-   Tous les opérateurs surchargés à l'exception de l'assignation \(`operator=`\) sont hérités par des classes dérivées.  
  
-   Le premier argument pour les opérateurs surchargés déclarés comme fonctions membres est toujours le type de classe de l'objet pour lequel l'opérateur est appelé \(la classe dans laquelle l'opérateur est déclaré ou une classe dérivée de cette classe\).  Aucune conversion n'est fournie pour le premier argument.  
  
 Notez que la signification de n'importe quel opérateur peut être modifiée complètement.  Cela comprend la signification des opérateurs d'adresses \(**&**\), d'assignation \(**\=**\) et d'appel de fonction.  En outre, les identités sur lesquelles on peut se reposer pour les types intégrés peuvent être modifiées à l'aide de la surcharge d'opérateur.  Par exemple, les quatre instructions suivantes sont généralement équivalentes une fois leur évaluation terminée :  
  
```  
var = var + 1;  
var += 1;  
var++;  
++var;  
```  
  
 On ne peut pas se reposer sur cette identité pour les types de classe qui surchargent des opérateurs.  De plus, certaines des spécifications implicites dans l'utilisation de ces opérateurs pour les types de base sont allégées pour les opérateurs surchargés.  Par exemple, l'opérateur d'addition\/assignation, `+=`, requiert que l'opérande gauche soit une l\-value en cas d'application à des types de base ; il n'existe aucune spécification de ce genre lorsque l'opérateur est surchargé.  
  
> [!NOTE]
>  Pour des raisons de cohérence, il est souvent préférable de suivre le modèle des types intégrés lors de la définition des opérateurs surchargés.  Si la sémantique d'un opérateur surchargé diffère sensiblement de sa signification dans d'autres contextes, il peut être plus perturbant qu'utile.  
  
## Voir aussi  
 [Surcharge d'opérateur](../cpp/operator-overloading.md)