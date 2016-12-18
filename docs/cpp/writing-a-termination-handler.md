---
title: "&#201;criture d&#39;un gestionnaire des terminaisons | Microsoft Docs"
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
  - "gestion des exceptions, gestionnaires de terminaisons"
  - "exceptions, terminer"
  - "gestionnaires"
  - "gestionnaires, arrêt"
  - "gestion structurée des exceptions, gestionnaires de terminaisons"
  - "gestionnaires de terminaisons"
  - "gestionnaires de terminaisons, écrire"
  - "try-catch (mot clé) (C++), gestionnaires de terminaisons"
ms.assetid: 52aa1f8f-f8dd-44b8-be94-5e2fc88d44fb
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# &#201;criture d&#39;un gestionnaire des terminaisons
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Contrairement à un gestionnaire d'exceptions, un gestionnaire de terminaisons est toujours exécuté, que le bloc de code protégé soit terminé normalement ou non.  L'objectif unique du gestionnaire de terminaisons doit être de garantir que les ressources, telles que la mémoire, les handles et les fichiers, sont fermées correctement indépendamment de la façon dont se termine l'exécution d'une section de code.  
  
 Les gestionnaires de terminaisons utilisent l'instruction try\-finally.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [L'instruction try\-finally](../cpp/try-finally-statement.md)  
  
-   [Nettoyage des ressources](../cpp/cleaning-up-resources.md)  
  
-   [Minutage des actions dans la gestion des exceptions](../cpp/timing-of-exception-handling-a-summary.md)  
  
-   [Restrictions applicables aux gestionnaires de terminaisons](../cpp/restrictions-on-termination-handlers.md)  
  
## Voir aussi  
 [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md)