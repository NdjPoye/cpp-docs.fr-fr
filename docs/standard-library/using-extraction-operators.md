---
title: "Utilisation d&#39;op&#233;rateurs d&#39;extraction | Microsoft Docs"
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
  - ">> (opérateur), opérateurs d'extraction"
  - "opérateurs d'extraction"
  - "opérateurs (C++), extraction"
ms.assetid: a961e1a9-4897-41de-b210-89d5b2d051ae
caps.latest.revision: 8
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Utilisation d&#39;op&#233;rateurs d&#39;extraction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'opérateur d'extraction \(`>>`\), qui est préprogrammé pour tous les types de données standard C\+\+, est la méthode la plus simple d'obtenir les octets d'un objet de flux d'entrée.  
  
 Les opérateurs d'extraction d'entrée de texte mis en forme dépend des espaces pour séparer les valeurs de données entrantes.  Il s'agit incommode lorsqu'un champ de texte contient plusieurs mots ou lorsque des virgules séparent les nombres.  Dans ce cas, une alternative consiste à utiliser la fonction non formatée [istream::getline](../Topic/basic_istream::getline.md) de membre d'entrée pour lire un bloc de texte comportant l'espace fourni, puis analyse le bloc avec des fonctions spéciales.  Une autre méthode consiste à partir une classe de flux d'entrée à une fonction membre par exemple `GetNextToken`, qui peut appeler des membres d'istream pour extraire et de caractères de format.  
  
## Voir aussi  
 [Flux d'entrée](../standard-library/input-streams.md)