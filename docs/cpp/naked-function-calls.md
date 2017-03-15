---
title: "Appels de fonction naked | Microsoft Docs"
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
  - "code d'épilogue"
  - "naked (fonctions)"
  - "naked (mot clé) (C++)"
  - "naked (mot clé) (C++), attribut de classe de stockage"
  - "code du prologue"
  - "pilotes de périphériques virtuels"
  - "pilotes de périphériques virtuels, appels de fonction naked"
  - "pilotes de périphériques virtuels VXD"
ms.assetid: 2a66847a-a43f-4541-a7be-c9f5f29b5fdb
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Appels de fonction naked
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Les fonctions déclarées avec l'attribut `naked` sont émises sans code de prologue ni d'épilogue, ce qui vous permet d'écrire vos propres séquences personnalisées de prologue\/épilogue à l'aide de l'[assembleur inline](../assembler/inline/inline-assembler.md).  Les fonctions naked sont fournies en tant que fonctionnalité avancée.  Elles vous permettent de déclarer une fonction appelée à partir d'un contexte autre que C\/C\+\+, et ainsi de faire des hypothèses différentes quant à l'emplacement où se trouvent les paramètres ou sur les registres qui sont conservés.  Il s'agit par exemple de routines telles que les gestionnaires d'interruptions.  Cette fonctionnalité est particulièrement utile pour les rédacteurs de pilotes de périphériques virtuels \(VxDs\).  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [naked](../cpp/naked-cpp.md)  
  
-   [Règles et limitations concernant les fonctions naked](../cpp/rules-and-limitations-for-naked-functions.md)  
  
-   [Considérations sur l'écriture de code de prologue\/épilogue](../cpp/considerations-for-writing-prolog-epilog-code.md)  
  
### FIN de la section spécifique à Microsoft  
  
## Voir aussi  
 [Conventions d'appel](../cpp/calling-conventions.md)