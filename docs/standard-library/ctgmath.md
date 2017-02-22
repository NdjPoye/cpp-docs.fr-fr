---
title: "&lt;ctgmath&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: ff521893-f445-4dc8-a2f6-699185bb7024
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# &lt;ctgmath&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En pratique, inclut les en\-têtes \<ccomplex\> et \<cmath\> de la bibliothèque C\+\+ standard, qui fournissent des macros mathématiques de type générique équivalentes à \<tgmath.h\>.  
  
## Syntaxe  
  
```  
  
#include <ctgmath>  
  
```  
  
## Notes  
 La fonctionnalité de l'en\-tête \<tgmath.h\> de la bibliothèque C standard est fournie par les surcharges dans \<ccomplex\> et \<cmath\>.  
  
 L'inclusion de cet en\-tête garantit également que les noms déclarés à l'aide d'une liaison externe dans l'en\-tête de la bibliothèque C standard soient déclarés dans l'espace de noms `std`.  
  
## Voir aussi  
 [\<ccomplex\>](../standard-library/ccomplex.md)   
 [\<cmath\>](../standard-library/cmath.md)   
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Vue d'ensemble de la bibliothèque STL](../standard-library/cpp-standard-library-overview.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)