---
title: "Recommandations relatives au choix entre une fonction et une macro | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "c.functions"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fonctions (CRT), différences par rapport aux macros"
  - "macros, différences par rapport aux fonctions"
ms.assetid: 18a633d6-cf1c-470c-a649-fa7677473e2b
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Recommandations relatives au choix entre une fonction et une macro
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La plupart des paramètres de la bibliothèque Runtime Microsoft sont compilées ou des fonctions assemblys, mais certaines routines sont implémentées en tant que macros.  Lorsqu'un fichier d'en\-tête indique une fonction et une macro version d'une routine, la définition de la macro est prioritaire, car il continue d'apparaître après la déclaration de fonction.  Lorsque vous appelez une routine qui est implémentée comme fonction et macro, vous pouvez forcer le compilateur pour utiliser la version de la fonction des deux manières suivantes :  
  
-   Placez le nom entre parenthèses actuel.  
  
    ```  
    #include <ctype.h>  
    a = _toupper(a);    // Use macro version of toupper.  
    a = (_toupper)(a);  // Force compiler to use   
                        // function version of toupper.  
    ```  
  
-   « Éliminer » la définition de macro avec la directive d'`#undef` :  
  
    ```  
    #include <ctype.h>  
    #undef _toupper  
    ```  
  
 Si vous devez choisir entre une fonction et une macro implémentation d'une routine de bibliothèque, considérez les avantages et inconvénients suivants :  
  
-   **Speed versus size** le principal avantage de l'utilisation de macros est une durée d'exécution plus rapide.  Pendant le prétraitement, une macro est \(remplacée par sa définition\) incluse développé chaque fois qu'elle est utilisée.  Une définition de la fonction intervient seulement une fois que le nombre de fois elle est appelée.  Les macros peuvent augmenter le nombre d'instructions mais n'ont pas la surcharge associée aux appels de fonction.  
  
-   La fonction de**Function evaluation** A pour résultat une adresse ; une macro contraire.  Vous ne pouvez pas utiliser le nom d'une macro dans les contextes qui requièrent un pointeur.  Par exemple, vous pouvez déclarer un pointeur à une fonction, mais pas un pointeur vers une macro.  
  
-   **Type\-checking** lorsque vous déclarez une fonction, le compilateur peut activer les types d'arguments.  Étant donné que vous ne pouvez pas déclarer une macro, le compilateur ne peut pas activer de macro types d'argument ; bien qu'il peut vérifier le nombre d'arguments pour passer à une macro.  
  
## Voir aussi  
 [Fonctions de bibliothèque CRT](../c-runtime-library/crt-library-features.md)