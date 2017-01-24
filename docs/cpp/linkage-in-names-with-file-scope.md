---
title: "Liaison des noms avec la port&#233;e du fichier | Microsoft Docs"
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
  - "déclarations (C++), externes"
  - "liaison externe, règles de liaison de portée"
  - "portée du fichier (C++)"
  - "liaison (C++), règles de liaison de portée"
  - "noms (C++), règles de liaison de portée"
  - "portée (C++), règles de liaison"
  - "static (modificateur), portée du fichier"
  - "noms statiques et portée du fichier"
  - "variables static, déclarations externes"
ms.assetid: 38d3fa5e-1861-466e-a590-84b86f7b184e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Liaison des noms avec la port&#233;e du fichier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les règles suivantes de liaison s'appliquent aux noms \(autres que les noms de `typedef` et les noms d'énumérateur\) avec la portée de fichier :  
  
-   Si un nom est déclaré explicitement comme **static**, il a une liaison interne et identifie un élément de programme dans sa propre unité de traduction.  
  
-   Les noms d'énumérateur et les noms de `typedef` n'ont aucune liaison.  
  
-   Tous les autres noms avec la portée de fichier ont une liaison externe.  
  
 **Section spécifique à Microsoft**  
  
-   Si un nom de fonction avec la portée de fichier est déclaré explicitement comme **inline**, il a une liaison externe s'il est instancié ou que son adresse est référencée.  Par conséquent, une fonction avec la portée de fichier peut avoir une liaison interne ou externe.  
  
 **FIN de la section spécifique à Microsoft**  
  
 Une classe a une liaison interne si elle :  
  
-   N'utilise pas de fonctionnalité C\+\+ \(par exemple, contrôle d'accès de membre, fonctions membres, constructeurs, destructeurs, etc.\).  
  
-   N'est pas utilisée dans la déclaration d'un autre nom qui a une liaison externe.  Cette contrainte signifie que les objets d'un type classe qui sont passés aux fonctions avec une liaison externe attribuent une liaison externe à cette classe.  
  
## Voir aussi  
 [Programme et liaison](../cpp/program-and-linkage-cpp.md)