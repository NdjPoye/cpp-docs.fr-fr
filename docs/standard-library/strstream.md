---
title: "&lt;strstream&gt; | Microsoft Docs"
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
  - "std.<strstream>"
  - "std::<strstream>"
  - "<strstream>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "strstream (en-tête)"
ms.assetid: eaa9d0d4-d217-4f28-8a68-9b9ad7b1c0f5
caps.latest.revision: 20
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# &lt;strstream&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit plusieurs classes qui prennent en charge les opérations iostreams sur les séquences stockées dans un tableau d'objets `char` alloué.  Ces séquences sont facilement converties vers et à partir de chaînes C.  
  
## Syntaxe  
  
```  
  
#include <strstream>  
  
```  
  
## Notes  
 Les objets de type `strstream` fonctionnent avec `char` \*, qui sont des chaînes C.  Utilisez [\<sstream\>](../standard-library/sstream.md) pour les objets de type [basic\_string](../standard-library/basic-string-class.md).  
  
> [!NOTE]
>  Les classes dans `<strstream>` sont déconseillées.  Utilisez plutôt les classes dans `<sstream>`.  
  
### Classes  
  
|||  
|-|-|  
|[strstreambuf, classe](../standard-library/strstreambuf-class.md)|Cette classe décrit une mémoire tampon de flux qui contrôle la transmission d'éléments vers et à partir d'une séquence d'éléments stockée dans un objet de tableau `char`.|  
|[istrstream, classe](../standard-library/istrstream-class.md)|La classe décrit un objet qui contrôle l'extraction d'éléments et d'objets encodés à partir d'une mémoire tampon de flux de classe [strstreambuf](../standard-library/strstreambuf-class.md).|  
|[ostrstream, classe](../standard-library/ostrstream-class.md)|La classe décrit un objet qui contrôle l'insertion d'éléments et d'objets encodés dans une mémoire tampon de flux de classe [strstreambuf](../standard-library/strstreambuf-class.md).|  
|[strstream, classe](../standard-library/strstream-class.md)|La classe décrit un objet qui contrôle l'insertion et l'extraction d'éléments et d'objets encodés à l'aide d'une mémoire tampon de flux de classe [strstreambuf](../standard-library/strstreambuf-class.md).|  
  
## Voir aussi  
 [\<strstream\>](../standard-library/strstream.md)   
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [iostream, programmation](../standard-library/iostream-programming.md)   
 [iostreams, conventions](../standard-library/iostreams-conventions.md)