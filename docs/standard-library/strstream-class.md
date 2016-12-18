---
title: "strstream, classe | Microsoft Docs"
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
  - "std::strstream"
  - "strstream"
  - "std.strstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstream (classe)"
ms.assetid: 63f3be31-9e36-42b1-9715-a474a5997e2a
caps.latest.revision: 21
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# strstream, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui contrôle l'insertion et l'extraction d'éléments et d'objets encodés à l'aide d'une mémoire tampon de flux de classe [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## Syntaxe  
  
```  
  
class strstream : public iostream  
  
```  
  
## Notes  
 L'objet stocke un objet de classe `strstreambuf`.  
  
> [!NOTE]
>  Cette classe est déconseillée.  Utilisez plutôt [stringstream](../Topic/stringstream.md) ou [wstringstream](../Topic/wstringstream.md).  
  
### Constructeurs  
  
|||  
|-|-|  
|[strstream](../Topic/strstream::strstream.md)|Construit un objet de type `strstream`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[freeze](../Topic/strstream::freeze.md)|Fait en sorte qu'une mémoire tampon de flux soit indisponible via des opérations de mémoire tampon de flux.|  
|[pcount](../Topic/strstream::pcount.md)|Retourne le nombre d'éléments écrits dans la séquence contrôlée.|  
|[rdbuf](../Topic/strstream::rdbuf.md)|Retourne un pointeur vers l'objet `strstreambuf` associé au flux.|  
|[str](../Topic/strstream::str.md)|Appelle [freeze](../Topic/strstreambuf::freeze.md), puis retourne un pointeur vers le début de la séquence contrôlée.|  
  
## Configuration requise  
 **En\-tête :** \<strstream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [iostream](../Topic/iostream.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)