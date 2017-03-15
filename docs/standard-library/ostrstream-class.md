---
title: "ostrstream, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "std.oststream"
  - "oststream"
  - "std::oststream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ostrstream (classe)"
ms.assetid: e2e34679-b266-4728-a8e1-8eda5d400e46
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# ostrstream, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui contrôle l'insertion d'éléments et d'objets encodés dans une mémoire tampon de flux de classe [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## Syntaxe  
  
```  
  
class ostrstream : public ostream  
  
```  
  
## Notes  
 L'objet stocke un objet de classe `strstreambuf`.  
  
> [!NOTE]
>  Cette classe est déconseillée.  Utilisez plutôt [ostringstream](../Topic/ostringstream.md) ou [wostringstream](../Topic/wostringstream.md).  
  
### Constructeurs  
  
|||  
|-|-|  
|[ostrstream](../Topic/ostrstream::ostrstream.md)|Construit un objet de type `ostrstream`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[freeze](../Topic/ostrstream::freeze.md)|Fait en sorte qu'une mémoire tampon de flux soit indisponible via des opérations de mémoire tampon de flux.|  
|[pcount](../Topic/ostrstream::pcount.md)|Retourne le nombre d'éléments écrits dans la séquence contrôlée.|  
|[rdbuf](../Topic/ostrstream::rdbuf.md)|Retourne un pointeur vers l'objet `strstreambuf` associé au flux.|  
|[str](../Topic/ostrstream::str.md)|Appelle [freeze](../Topic/strstreambuf::freeze.md), puis retourne un pointeur vers le début de la séquence contrôlée.|  
  
## Configuration requise  
 **En\-tête :** \<strstream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [ostream](../Topic/ostream.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)