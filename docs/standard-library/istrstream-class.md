---
title: "istrstream, classe | Microsoft Docs"
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
  - "istrstream"
  - "std::istrstream"
  - "std.istrstream"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "istrstream (classe)"
ms.assetid: c2d41c75-bd2c-4437-bd77-5939ce1b97af
caps.latest.revision: 20
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# istrstream, classe
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Décrit un objet qui contrôle l'extraction d'éléments et d'objets encodés à partir d'une mémoire tampon de flux de classe [strstreambuf](../standard-library/strstreambuf-class.md).  
  
## Syntaxe  
  
```  
  
class istrstream : public istream  
  
```  
  
## Notes  
 L'objet stocke un objet de classe `strstreambuf`.  
  
> [!NOTE]
>  Cette classe est déconseillée. Envisagez d’utiliser [istringstream](../Topic/istringstream.md) ou [wistringstream](../Topic/wistringstream.md) à la place.  
  
### Constructeurs  
  
|||  
|-|-|  
|[istrstream](../Topic/istrstream::istrstream.md)|Construit un objet de type `istrstream`.|  
  
### Fonctions membres  
  
|||  
|-|-|  
|[rdbuf](../Topic/istrstream::rdbuf.md)|Retourne un pointeur vers l'objet `strstreambuf` associé au flux.|  
|[str](../Topic/istrstream::str.md)|Appelle [freeze](../Topic/strstreambuf::freeze.md), puis retourne un pointeur vers le début de la séquence contrôlée.|  
  
## Configuration requise  
 **En\-tête :** \<strstream\>  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [istream](../Topic/istream.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)