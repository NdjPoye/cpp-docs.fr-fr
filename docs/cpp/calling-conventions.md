---
title: "Conventions d&#39;appel | Microsoft Docs"
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
  - "conventions d'appel"
ms.assetid: 11b1e45c-8fd1-420b-bca0-a19e294c1d85
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Conventions d&#39;appel
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le compilateur Visual C\/C\+\+ fournit diverses conventions pour appeler des fonctions internes et externes.  La compréhension de ces différentes approches peut vous aider à déboguer votre programme et à lier votre code avec des routines en langage assembleur.  
  
 Les rubriques se rapportant à ce sujet expliquent les différences entre les conventions d'appel, la façon dont les arguments sont passés et la manière dont les valeurs sont retournées par les fonctions.  Elles présentent également les appels de fonction naked, une fonctionnalité avancée qui vous permet d'écrire votre propre code de prologue et d'épilogue.  
  
 Pour plus d'informations sur les conventions d'appel pour les processeurs x64, consultez [Convention d'appel](../build/calling-convention.md).  
  
## Rubriques de cette section  
  
-   [Conventions d'affectation de noms et de transmission d'arguments](../cpp/argument-passing-and-naming-conventions.md) \(\_\_`cdecl`, \_\_**stdcall**, \_\_**fastcall** et autres\)  
  
-   [Exemple d'appel : Prototype et appel de fonction](../cpp/calling-example-function-prototype-and-call.md)  
  
-   [Utilisation d'appels de fonction naked pour écrire du code personnalisé de prologue\/épilogue](../cpp/naked-function-calls.md)  
  
-   [Coprocesseur à virgule flottante et conventions d'appel](../cpp/floating-point-coprocessor-and-calling-conventions.md)  
  
-   [Conventions d'appel obsolètes](../cpp/obsolete-calling-conventions.md)  
  
## Voir aussi  
 [Modificateurs spécifiques Microsoft](../cpp/microsoft-specific-modifiers.md)