---
title: "time_base, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.time_base"
  - "std::time_base"
  - "time_base"
  - "locale/std::time_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "time_base (classe)"
ms.assetid: 9ae37f0b-9a42-496e-9870-3d9b71bab8fb
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# time_base, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe sert de classe de base pour les facettes du time\_get de classe du modèle, la définition de type énuméré **dateorder** et plusieurs constantes de ce type.  
  
## Syntaxe  
  
```  
class time_base : public locale::facet {  
public:  
    enum dateorder {no_order, dmy, mdy, ymd, ydm};  
    time_base(  
        size_t _Refs = 0  
    )  
    ~time_base();  
};  
```  
  
## Notes  
 Chaque constant propose une manière différente pour classer les composants d'une date.  Les constantes sont :  
  
-   **no\_order** ne spécifie aucun ordre particulier.  
  
-   **dmy** spécifie le jour de commande, mois, puis par année, comme dans le 2 décembre 1979.  
  
-   **mdy** spécifie le mois de commande, jour, puis année, comme dans le 2 décembre 1979.  
  
-   **ymd** spécifie l'année de commande, le mois, le jour, comme le en 1979 \/12. \/2.  
  
-   **ydm** spécifie l'année de commande, le jour, le mois, comme le en 1979 : 2 décembre  
  
## Configuration requise  
 paramètres régionaux \<de**En\-tête :** \>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)