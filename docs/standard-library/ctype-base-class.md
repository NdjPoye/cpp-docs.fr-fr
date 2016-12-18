---
title: "ctype_base, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "locale/std::ctype_base"
  - "std.ctype_base"
  - "ctype_base"
  - "std::ctype_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ctype_base (classe)"
ms.assetid: ccffe891-d7ab-4d22-baf8-8eb6d438a96d
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ctype_base, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe sert de classe de base pour les facettes de la classe de modèle [C](../standard-library/ctype-class.md).  Une classe de base pour la classe C utilisée pour définir des types énumération utilisés pour définir ou tester les caractères individuellement ou dans des limites entières.  
  
## Syntaxe  
  
```  
struct ctype_base : public locale::facet  
{  
    enum  
    {  
        alnum, alpha, cntrl, digit, graph,  
        lower, print, punct, space, upper,  
        xdigit  
    };  
    typedef short mask;  
    ctype_base(  
        size_t _Refs = 0  
    );  
    ~ctype_base();  
};  
```  
  
## Notes  
 Elle définit un masque d'énumération.  Chaque constant d'énumération comprend une manière différente de classement des caractères, comme défini par les fonctions avec des noms semblables déclarés dans l'en\-tête \<ctype.h.\>  Les constantes sont :  
  
-   **space** \(fonction [isspace](../Topic/isspace.md)\)  
  
-   **print** \(fonction [isprint](../Topic/isprint.md)\)  
  
-   **cntrl** \(fonction [iscntrl](../Topic/iscntrl.md)\)  
  
-   **upper** \(fonction [isupper](../Topic/isupper.md)\)  
  
-   **lower** \(fonction [islower](../Topic/islower.md)\)  
  
-   **digit** \(fonction [isdigit](../Topic/isdigit.md)\)  
  
-   **punct** \(fonction [ispunct](../Topic/ispunct.md)\)  
  
-   **xdigit** \(fonction [isxdigit](../Topic/isxdigit.md)\)  
  
-   **alpha** \(fonction [isalpha](../Topic/isalpha.md)\)  
  
-   **alnum** \(fonction [isalnum](../Topic/isalnum.md)\)  
  
-   **graph** \(fonction [isgraph](../Topic/isgraph.md)\)  
  
 Vous pouvez fonctionnalités à une combinaison de classifications par la réunion logique ces constantes.  En particulier, il est toujours la valeur true que \=\= d'**alnum** \(**alpha** ``&#124; **digit**\=\=\) et de **graph** \(**alnum**``&#124; **punct**\).  
  
## Configuration requise  
 paramètres régionaux \<de**En\-tête :** \>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)