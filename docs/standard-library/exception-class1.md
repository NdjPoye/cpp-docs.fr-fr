---
title: "exception, classe | Microsoft Docs"
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
  - "std.exception"
  - "exception"
  - "std::exception"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "exception (classe)"
ms.assetid: 4f181f67-5888-4b50-89a6-745091ffb2fe
caps.latest.revision: 19
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# exception, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La classe sert de classe de base pour toutes les exceptions levées par certaines expressions et par la bibliothèque C\+\+ standard.  
  
## Syntaxe  
  
```  
class exception {  
public:  
    exception();  
    exception(const char * const &message);  
    exception(const char * const &message, int);  
    exception(const exception &right);  
    exception& operator=(const exception &right);  
    virtual ~exception();  
    virtual const char *what() const;  
};  
```  
  
## Notes  
 En particulier, la classe de base est la racine des classes standard d'exception définies dans [\<stdexcept\>](../standard-library/stdexcept.md).  La valeur de chaîne C retournée par `what` reste non spécifiée par le constructeur par défaut, mais peut être définie par les constructeurs pour certaines classes dérivées en tant qu'implémentation de chaîne C.  Aucune des fonctions membres ne lève une exception.  
  
 Le paramètre `int` vous permet de spécifier qu'aucune mémoire ne doit être allouée.  La valeur de `int` est ignorée.  
  
> [!NOTE]
>  Les constructeurs `exception(const char * const &message)` et `exception(const char * const &message, int)` sont des extensions Microsoft de la bibliothèque C\+\+ standard.  
  
## Exemple  
 Pour obtenir des exemples de l'utilisation de classes standard d'exception qui héritent de la classe `exception`, consultez l'une des classes définies dans [\<stdexcept\>](../standard-library/stdexcept.md).  
  
## Configuration requise  
 **En\-Tête** \<exception\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)