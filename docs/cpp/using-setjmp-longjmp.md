---
title: "Utilisation de setjmp/longjmp | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "longjmp"
  - "setjmp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion d'exceptions C++, setjmp/longjmp (fonctions)"
  - "fonction longjmp dans les programmes C++"
  - "setjmp (fonction)"
  - "setjmp (fonction), programmes C++"
  - "SETJMP.H"
  - "SETJMPEX.H"
ms.assetid: 96be8816-f6f4-4567-9a9c-0c3c720e37c5
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Utilisation de setjmp/longjmp
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Lorsque [setjmp](../c-runtime-library/reference/setjmp.md) et [longjmp](../c-runtime-library/reference/longjmp.md) sont utilisés conjointement, ils fournissent un moyen d'exécuter un `goto` non local.  Ils sont généralement utilisés pour passer le contrôle d'exécution au code de gestion des erreurs ou le code récupération dans une routine appelée précédemment sans utiliser l'appel standard ou les conventions de retour.  
  
> [!CAUTION]
>  Toutefois, étant donné que `setjmp` et `longjmp` ne prennent pas en charge la sémantique d'objet C\+\+, et qu'ils peuvent diminuer les performances en empêchant l'optimisation sur les variables locales, nous vous recommandons de ne pas les utiliser dans les programmes C\+\+.  Il est recommandé de les utiliser à la place des constructions `try`\/`catch`.  
  
 Si vous décidez d'utiliser `setjmp`\/`longjmp` dans un programme C\+\+, incluez également SETJMP.H ou SETJMPEX.H pour assurer une bonne interaction entre les fonctions et la gestion des exceptions C\+\+.  Si vous utilisez [\/EH](../build/reference/eh-exception-handling-model.md) pour compiler, les destructeurs des objets locaux sont appelés durant le désempilage.  Si vous utilisez **\/EHs** pour compiler, et l'une de vos fonctions appelle une fonction qui utilise [nothrow](../cpp/nothrow-cpp.md) et la fonction qui utilise `longjmp` appelle `nothrow`, le déroulement du destructeur risque de ne pas se produire, selon l'optimiseur.  
  
 Dans le code portable, lorsqu'un `goto` non local qui appelle `longjmp` est exécuté, la destruction correcte des objets basés sur des trames peut s'avérer peu fiable.  
  
## Voir aussi  
 [Mélange d'exceptions C \(structurées\) et d'exceptions C\+\+](../cpp/mixing-c-structured-and-cpp-exceptions.md)