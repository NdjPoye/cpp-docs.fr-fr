---
title: "R&#232;gles d&#39;inf&#233;rence | Microsoft Docs"
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
  - "règles d'inférence dans NMAKE"
  - "programme NMAKE, règles d'inférence"
  - "règles, inférence"
ms.assetid: caff320f-fb07-4eea-80c3-a6a2133a8492
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# R&#232;gles d&#39;inf&#233;rence
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les règles d'inférence fournissent des commandes permettant de mettre à jour des commandes et de déduire des dépendants pour les cibles.  Dans une règle d'inférence, les extensions correspondent à une cible et à un dépendant uniques qui ont le même nom de base.  Les règles d'inférence sont définies par l'utilisateur ou prédéfinies ; les règles prédéfinies sont redéfinissables.  
  
 Si une dépendance obsolète n'a pas de commandes, et si [.SUFFIXES](../build/dot-directives.md) contient l'extension du dépendant, NMAKE utilise une règle dont les extensions correspondent à la cible et à un fichier existant dans le répertoire en cours ou spécifié.  Si plusieurs règles correspondent à des fichiers existants, la liste **.SUFFIXES** détermine laquelle utiliser ; la priorité de la liste va de gauche à droite.  Si un fichier dépendant n'existe pas et n'est pas listé en tant que cible dans un autre bloc de description, une règle d'inférence peut créer le dépendant manquant à partir d'un autre fichier portant le même nom de base.  Si la cible d'un bloc de description n'a ni dépendants ni commandes, une règle d'inférence peut mettre à jour la cible.  Les règles d'inférence peuvent générer une cible de ligne de commande même en l'absence de tout bloc de description.  NMAKE peut appeler une règle pour un dépendant déduit même si un dépendant explicite est spécifié.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
 [Définition d'une règle](../build/defining-a-rule.md)  
  
 [Règles en mode batch](../build/batch-mode-rules.md)  
  
 [Règles prédéfinies](../build/predefined-rules.md)  
  
 [Règles et dépendants déduits](../build/inferred-dependents-and-rules.md)  
  
 [Préséance dans les règles d'inférence](../build/precedence-in-inference-rules.md)  
  
## Voir aussi  
 [Référence NMAKE](../build/nmake-reference.md)