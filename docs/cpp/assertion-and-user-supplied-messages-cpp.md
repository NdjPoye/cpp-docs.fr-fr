---
title: "Assertion et messages fournis par l&#39;utilisateur (C++) | Microsoft Docs"
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
  - "#error%2C assert%2C static_assert (C++)"
  - "messages fournis par l'utilisateur (C++), au moment de la compilation"
  - "messages fournis par l'utilisateur (C++), au moment du préprocesseur"
  - "messages fournis par l'utilisateur (C++), au moment de l'exécution"
ms.assetid: ebf7d885-61c8-4233-b0ae-1c9a38e0f385
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Assertion et messages fournis par l&#39;utilisateur (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le langage C\+\+ prend en charge trois mécanismes de gestion des erreurs qui vous aident à déboguer votre application : la [directive \#error](../preprocessor/hash-error-directive-c-cpp.md), le mot clé [static\_assert](../cpp/static-assert.md) et la macro [assert \(macro\), \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md).  Ces trois mécanismes génèrent des messages d'erreur et deux d'entre eux testent également les assertions logicielles.  Une assertion logicielle spécifie une condition supposée être vraie en un point particulier de votre programme.  Si une assertion au moment de la compilation échoue, le compilateur génère un message de diagnostic et une erreur de compilation.  Si une assertion d'exécution échoue, le système d'exploitation génère un message de diagnostic et ferme votre application.  
  
## Notes  
 La durée de vie de votre application se compose d'une phase de prétraitement, de compilation et d'exécution.  Chaque mécanisme de gestion des erreurs accède aux informations de débogage disponibles pendant l'une de ces phases.  Pour déboguer efficacement, sélectionnez le mécanisme qui fournit des informations pertinentes concernant cette phase :  
  
-   La [directive \#error](../preprocessor/hash-error-directive-c-cpp.md) est appliquée au moment du prétraitement.  Elle génère sans condition un message spécifié par l'utilisateur et provoque l'échec de la compilation avec une erreur.  Le message peut contenir du texte manipulé par des directives de préprocesseur, mais aucune expression obtenue n'est évaluée.  
  
-   La déclaration [static\_assert](../cpp/static-assert.md) est appliquée au moment de la compilation.  Elle teste une assertion logicielle représentée par une expression intégrale spécifiée par l'utilisateur qui peut être convertie en valeur booléenne.  Si l'expression est évaluée à la valeur zéro \(false\), le compilateur génère le message spécifié par l'utilisateur et la compilation échoue avec une erreur.  
  
     La déclaration `static_assert` est particulièrement utile pour le débogage des modèles, car des arguments template peuvent être inclus dans l'expression spécifiée par l'utilisateur.  
  
-   La macro [assert \(macro\), \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md) est appliquée au moment de l'exécution.  Elle évalue une expression spécifiée par l'utilisateur, et si le résultat est zéro, le système génère un message de diagnostic et ferme votre application.  De nombreuses autres macros, telles que[\_ASSERT](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) et `_ASSERTE`, ressemblent à cette macro mais génèrent des messages de diagnostic définis par le système ou définis par l'utilisateur différents.  
  
## Voir aussi  
 [\#error, directive](../preprocessor/hash-error-directive-c-cpp.md)   
 [assert \(macro\), \_assert, \_wassert](../c-runtime-library/reference/assert-macro-assert-wassert.md)   
 [\_ASSERT, \_ASSERTE, \_ASSERT\_EXPR \(macros\)](../c-runtime-library/reference/assert-asserte-assert-expr-macros.md)   
 [static\_assert](../cpp/static-assert.md)   
 [\_STATIC\_ASSERT, macro](../c-runtime-library/reference/static-assert-macro.md)   
 [Modèles](../cpp/templates-cpp.md)