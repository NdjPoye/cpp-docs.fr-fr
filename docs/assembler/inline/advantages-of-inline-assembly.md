---
title: "Avantages de l&#39;assembly inline | Microsoft Docs"
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
  - "assembleur (C++), avantages"
  - "assembleur inline (C++), à propos de l'assembleur inline"
  - "assembleur inline (C++), utilisation"
ms.assetid: 94364d97-faa7-4bdf-8473-570956986c51
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avantages de l&#39;assembly inline
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

## Section spécifique à Microsoft  
 Étant donné que l'assembleur inline n'a pas besoin de code assembleur ni d'étapes de liaison distinctes, il est plus pratique qu'un assembleur distinct.  Le code assembleur inline peut utiliser tout nom de fonction ou variable C qui est dans la portée. Il est par conséquent facile de l'intégrer au code C de votre programme.  Le code assembleur pouvant être combiné inline avec des instructions C ou C\+\+, il peut exécuter des tâches lourdes ou impossibles en C ou C\+\+.  
  
 Les utilisations de l'assembly inline incluent :  
  
-   Fonctions d'écriture en langage assembleur.  
  
-   Sections vitesse\-critique optimisation\-projecteur du code.  
  
-   Rendre l'accès matériel direct pour les pilotes de périphérique.  
  
-   Prolog d'écriture et code d'épilogue pour les appels « naked ».  
  
 L'assembleur inline est un outil spécialisé.  Si vous prévoyez de déplacer une application vers différents ordinateurs, vous souhaiterez probablement placer le code propre à l'ordinateur dans un module séparé.  Comme l'assembleur inline ne prend pas en charge toutes les directives de données et de macros de l'assembleur de macros Microsoft \(MASM\), vous pouvez trouver plus pratique d'utiliser MASM pour ces modules.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Assembleur inline](../../assembler/inline/inline-assembler.md)