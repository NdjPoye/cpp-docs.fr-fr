---
title: "once_flag, structure | Microsoft Docs"
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
  - "mutex/std::once_flag"
dev_langs: 
  - "C++"
ms.assetid: 71bfb88d-ca8c-4082-a6e1-ff52151e8629
caps.latest.revision: 13
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# once_flag, structure
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Représente un `struct` utilisé avec la fonction de modèle [call\_once](../Topic/call_once%20Function.md) pour garantir que le code d'initialisation est appelé une seule fois, même en présence de plusieurs threads d'exécution.  
  
## Syntaxe  
  
```cpp  
struct once_flag  
{  
   constexpr once_flag() noexcept;  
   once_flag(const once_flag&);  
   once_flag& operator=(const once_flag&);  
};  
```  
  
## Notes  
 La classe `once_flag` `struct` a un seul constructeur par défaut.  
  
 Les objets de type `once_flag` peuvent être créés, mais ils ne peuvent pas être copiés.  
  
## Configuration requise  
 **En\-tête :** mutex  
  
 **Espace de noms :** std  
  
## Voir aussi  
 [Référence de fichiers d'en\-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\<mutex\>](../standard-library/mutex.md)