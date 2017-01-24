---
title: "Mod&#232;les et r&#233;solution de noms | Microsoft Docs"
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
ms.assetid: 519ba7b5-cd25-4549-865a-9a7b9dffdc28
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mod&#232;les et r&#233;solution de noms
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans les définitions de modèle, il existe trois types de noms :  
  
-   les noms déclarés localement, notamment le nom du modèle lui\-même et tous les noms déclarés dans la définition de modèle ;  
  
-   les noms provenant de la portée englobante située en dehors de la définition de modèle ;  
  
-   les noms qui dépendent d'une certaine façon des arguments template, appelés noms dépendants.  
  
 Alors que les deux premiers noms concernent aussi des portées de classe et de fonction, des règles spécifiques de résolution de noms sont requises dans les définitions de modèle pour gérer la complexité ajouté des noms dépendants.  Cela provient du fait que le compilateur connaît peu ces noms avant que le modèle ne soit instancié car il peut s'agir de types complètement différents selon les arguments template utilisés.  Les noms non dépendants sont recherchés selon les règles classiques et au point de définition du modèle.  Ces noms, qui sont indépendants des arguments template, sont recherchés une fois pour toutes les spécialisations de modèle.  Les noms dépendants ne sont pas recherchés tant que le modèle n'est pas instancié et sont recherchés séparément pour chaque spécialisation.  
  
 Un type est dépendant s'il dépend des arguments template.  En particulier un type est dépendant s'il s'agit :  
  
-   de l'argument template lui\-même ;  
  
    ```  
    T  
    ```  
  
-   d'un nom complet avec une qualification comprenant un type dépendant ;  
  
    ```  
    T::myType  
    ```  
  
-   d'un nom complet si la partie non qualifiée identifie un type dépendant ;  
  
    ```  
    N::T  
    ```  
  
-   d'un type const ou volatile pour lequel le type de base est un type dépendant ;  
  
    ```  
    const T  
    ```  
  
-   d'un type pointeur, référence, tableau ou pointeur de fonction basé sur un type dépendant :  
  
    ```  
    T *, T &, T [10], T (*)()  
    ```  
  
-   d'un tableau dont la taille est basée sur un paramètre de modèle :  
  
    ```  
    template <int arg> class X {  
    int x[arg] ; // dependent type  
    }  
    ```  
  
-   d'un type modèle construit à partir d'un modèle de paramètre :  
  
    ```  
    T<int>, MyTemplate<T>  
    ```  
  
## Dépendance de type et dépendance de valeur  
 Les noms et les expressions dépendants d'un paramètre de modèle sont classés comme dépendant de type ou dépendant de valeur selon que le paramètre de modèle est un paramètre de type ou un paramètre de valeur.  En outre, tous les identificateurs déclarés dans un modèle avec un type dépendant de l'argument template sont considérés comme dépendants de valeur, étant donné qu'un type intégral ou énumération est initialisé avec une expression dépendante de valeur.  
  
 Les expressions dépendantes de type et de valeur sont des expressions qui impliquent des variables qui dépendent de type ou de valeur.  Ces expressions peuvent avoir une sémantique qui diffère selon les paramètres utilisés pour le modèle.  
  
## Voir aussi  
 [Modèles](../cpp/templates-cpp.md)