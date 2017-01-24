---
title: "Liaison des noms avec la port&#233;e de classe | Microsoft Docs"
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
  - "noms de classes (C++), liaison"
  - "portée de classe (C++), liaison des noms avec"
  - "classes (C++), noms"
  - "classes (C++), portée"
  - "liaison externe, règles de liaison de portée"
  - "liaison (C++), règles de liaison de portée"
  - "noms (C++), règles de liaison de portée"
  - "portée (C++), noms de classes"
  - "portée (C++), règles de liaison"
ms.assetid: 45275ff3-6e94-4967-82c8-ba540ef4da28
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Liaison des noms avec la port&#233;e de classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les règles de liaison suivantes s'appliquent aux noms avec la portée de classe :  
  
-   Les membres de classe statique ont une liaison externe.  
  
-   Les fonctions membres de classe ont une liaison externe.  
  
-   Les noms d'énumérateur et les noms `typedef` n'ont aucune liaison.  
  
 **Section spécifique à Microsoft**  
  
-   Les fonctions déclarées comme fonctions `friend` doivent avoir une liaison externe.  La déclaration d'une fonction statique comme `friend` génère une erreur.  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [Programme et liaison](../cpp/program-and-linkage-cpp.md)