---
title: "D&#233;finition d&#39;un flux | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "données (C++), lire"
  - "lire des données (C++), iostream (programmation)"
  - "flux (C++)"
  - "flux (C++), dans les classes iostream"
ms.assetid: a7e661e9-6cd1-4543-a9a4-c58ee9fd32f3
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# D&#233;finition d&#39;un flux
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

À l'instar de l'Assistant De c, C\+\+ n'a pas de fonction intégrée d'entrée\/sortie.  Tous les compilateurs C\+\+, toutefois, issus regroupé avec un package systématique et orienté objet d'E\/S, appelés classes iostream.  Le flux de données est le concept de les classes iostream.  Vous pouvez considérer un objet de flux en tant que fichier intelligent qui sert de source et destination pour les octets.  Les caractéristiques d'un flux de données sont déterminées par la classe et par la mise en place personnalisée et opérateurs d'extraction.  
  
 Par le biais de pilote de périphérique, le système d'exploitation MS\-DOS traite le clavier, l'écran, l'imprimante, et le port de communication en tant que fichiers étendus.  Les classes iostream interagissent avec ces fichiers étendus.  Les classes intégrées prennent en charge la lire et écrire dans la mémoire avec la syntaxe identique à celle de l'E\/S disque, qui facilite de dériver les classes de flux de données.  
  
## Dans cette section  
 [Alternatives d'entrée\/sortie](../standard-library/input-output-alternatives.md)  
  
## Voir aussi  
 [iostream, programmation](../standard-library/iostream-programming.md)