---
title: "&lt;typeindex&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "<typeindex>"
dev_langs: 
  - "C++"
ms.assetid: a9551137-f74b-4f02-af64-ff00214cea1f
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# &lt;typeindex&gt;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Incluez le typeindex standard \<d'en\-tête\> pour définir une classe et à exécuter qui prennent en charge l'indexation des objets de la classe [type\_information](../cpp/type-info-class.md).  
  
## Syntaxe  
  
```cpp  
#include <typeindex>  
```  
  
## Notes  
 [hash, structure](../standard-library/hash-structure.md) définit `hash function` qui est appropriée pour mapper les valeurs de type [type\_index](../standard-library/type-index-class.md) à une distribution de valeurs d'index.  
  
 La classe d'`type_index` encapsule un pointeur vers un objet d'`type_info` à l'aide de l'indexation.  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [Sécurité des threads dans la bibliothèque standard C\+\+](../standard-library/thread-safety-in-the-cpp-standard-library.md)   
 [Bibliothèque STL \(Standard Template Library\)](../misc/standard-template-library.md)