---
title: "Objets temporaires | Microsoft Docs"
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
  - "objets (C++), temporaires"
  - "objets temporaires"
ms.assetid: 4c8cec02-391e-4225-9bc6-06d150201412
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Objets temporaires
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans certains cas, le compilateur a besoin de créer des objets temporaires.  Ces objets temporaires peuvent être créés pour les raisons suivantes :  
  
-   pour initialiser une référence `const` avec un initialiseur d'un type différent de celui du type sous\-jacent de la référence initialisée ;  
  
-   pour stocker la valeur de retour d'une fonction qui retourne un type défini par l'utilisateur.  Ces objets temporaires sont créés uniquement si votre programme ne copie pas la valeur de retour passée à un objet.  Par exemple :  
  
    ```  
    UDT Func1();    //  Declare a function that returns a user-defined  
                    //   type.  
  
    ...  
  
    Func1();        //  Call Func1, but discard return value.  
                    //  A temporary object is created to store the return  
                    //   value.  
    ```  
  
     La valeur de retour n'étant pas copiée dans un autre objet, un objet temporaire est créé.  Un des cas les plus courants où des objets temporaires sont créés est l'évaluation d'une expression où des fonctions surchargées d'opérateur doivent être appelées.  Ces fonctions d'opérateur surchargées retournent un type défini par l'utilisateur qui n'est souvent pas copié dans un autre objet.  
  
     Prenons l'exemple de l'expression `ComplexResult = Complex1 + Complex2 + Complex3`.  L'expression `Complex1 + Complex2` est évaluée, et le résultat est stocké dans un objet temporaire.  Ensuite, l'expression *temporary* `+ Complex3` est évaluée et le résultat est copié dans `ComplexResult` \(en supposant que l'opérateur d'assignation n'est pas surchargé\).  
  
-   Pour stocker le résultat d'un cast en un type défini par l'utilisateur.  Lorsqu'un objet d'un type donné est converti explicitement en un type défini par l'utilisateur, ce nouvel objet est construit sous la forme d'un objet temporaire.  
  
 Les objets temporaires ont une durée de vie définie par leur point de conception et le point auquel ils sont détruits.  Toute expression qui crée plusieurs objet temporaire finalement les détruit dans l'ordre inverse dans lequel ils ont été créés.  Les points auxquels la destruction se produit sont présentés dans le tableau suivant.  
  
### Points de destruction des objets temporaires  
  
|Motif de création de l'objet temporaire|Point de destruction|  
|---------------------------------------------|--------------------------|  
|Résultat de l'évaluation de l'expression|Tous les objets temporaires créés à la suite de l'évaluation d'une expression sont détruits à la fin de l'instruction d'expression \(c'est\-à\-dire au point\-virgule\) ou à la fin des expressions de contrôle pour `for`, `if`, `while`, `do` et `switch`.|  
|Initialisation des références `const`|Si un initialiseur n'est pas une l\-value du même type que la référence initialisée, un objet temporaire du type d'objet sous\-jacent est créé et initialisé avec l'expression d'initialisation.  Cet objet temporaire est détruit juste après la destruction de l'objet de référence auquel il est lié.|  
  
## Voir aussi  
 [Fonctions membres spéciales](../misc/special-member-functions-cpp.md)