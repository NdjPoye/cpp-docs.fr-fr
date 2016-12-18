---
title: "hash, structure (STL) | Microsoft Docs"
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
  - "thread/std::hash"
dev_langs: 
  - "C++"
ms.assetid: 4a8bf5bc-4334-4070-936b-98585f8a073b
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# hash, structure (STL)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit une fonction membre qui retourne une valeur qui est déterminée de manière unique par `Val`. La fonction membre définit un [hachage](hash%20Class.md) (fonction) qui est appropriée pour les valeurs de mappage de type `thread::id` pour une distribution de valeurs d’index.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <>  
struct hash<thread::id> :   
    public unary_function<thread::id, size_t>  
{  
    size_t operator()(thread::id Val) const;

 
};  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** thread  
  
 **Namespace :** std  
  
## <a name="see-also"></a>Voir aussi  
 [Référence de fichiers d’en-tête](../standard-library/cpp-standard-library-header-files.md)   
 [\< thread>](../standard-library/thread.md)   
 [unary_function, structure](../standard-library/unary-function-struct.md)
