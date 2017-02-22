---
title: "money_base, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "locale/std::money_base"
  - "money_base"
  - "std::money_base"
  - "std.money_base"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "money_base (classe)"
ms.assetid: 1a303c15-9272-4f26-ae16-dcf43a0fd38a
caps.latest.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 19
---
# money_base, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe décrit une énumération et une structure commun à toutes les spécialisations de classe de modèle [moneypunct](../standard-library/moneypunct-class.md).  
  
## Syntaxe  
  
```  
struct money_base : public locale::facet  
{  
    enum  
    {  
        symbol = '$',  
        sign = '+',  
        space = ' ',  
        value = 'v',  
        none = 'x'  
    };  
    typedef int part;  
    struct pattern  
    {  
        char field[_PATTERN_FIELD_SIZE];  
    };  
    money_base(  
        size_t _Refs = 0  
    );  
    ~money_base();  
};  
```  
  
## Notes  
 L'énumération **part** décrit les valeurs possibles dans les éléments du champ de table du modèle de structure.  Les valeurs de **part** sont:  
  
-   **none** pour associer zéro ou plus d'espace ou ne génère rien.  
  
-   **sign** pour aossicier ou générer un signe positif ou négatif.  
  
-   **space** pour associer zéro ou plus d'espace ou ne génère rien.  
  
-   **symbole** pour associer ou générer un symbole monétaire.  
  
-   **valeur** pour associer ou générer une valeur monétaire.  
  
## Configuration requise  
 **En\-tête:** \<paramètres régionaux\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)