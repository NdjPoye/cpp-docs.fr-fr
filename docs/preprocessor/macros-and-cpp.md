---
title: "Macros et C++ | Microsoft Docs"
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
  - "C"
helpviewer_keywords: 
  - "macros"
  - "macros, C++"
ms.assetid: 83a344c1-73c9-4ace-8b93-cccfb62c6133
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Macros et C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

C\+\+ offre de nouvelles fonctionnalités, dont certaines supplantent celles proposés par le préprocesseur ANSI C.  Ces nouvelles fonctionnalités améliorent la sécurité et la prévisibilité des types du langage :  
  
-   En C\+\+, les objets déclarés comme **const** peuvent être utilisés dans les expressions constantes.  Cela permet aux programmes de déclarer des constantes comportant des informations de type et de valeur, et des énumérations qui peuvent être affichées symboliquement avec le débogueur.  Utiliser la directive `#define` du préprocesseur pour définir des constantes n'est pas aussi précis.  Aucun stockage n'est alloué à un objet **const**, à moins qu'une expression prenant son adresse soit trouvée dans le programme.  
  
-   La fonctionnalité de la fonction inline C\+\+ supplante les macros de type fonction.  Voici les avantages que présente l'utilisation des fonctions inline par rapport aux macros :  
  
    -   Sécurité de type.  Les fonctions inline sont soumises à la même vérification du type que les fonctions normales.  Les macros ne sont pas de type sécurisé.  
  
    -   Gestion correcte des arguments présentant des effets secondaires.  Les fonctions inline évaluent les expressions fournies comme arguments avant l'accès au corps de la fonction.  Par conséquent, il n'y a aucun risque qu'une expression avec effets secondaires présente un risque.  
  
 Pour plus d'informations sur les fonctions inline, consultez [inline, \_\_inline, \_\_forceinline](../misc/inline-inline-forceinline.md).  
  
 À des fins de compatibilité descendante, toutes les fonctions de préprocesseur qui existaient dans les spécifications C ANSI et C \+\+ antérieures sont conservés pour Microsoft C\+\+.  
  
## Voir aussi  
 [Macros prédéfinies](../preprocessor/predefined-macros.md)   
 [Macros](../preprocessor/macros-c-cpp.md)